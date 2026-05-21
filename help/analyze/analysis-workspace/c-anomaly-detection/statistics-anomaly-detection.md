---
description: Saiba quais técnicas estatísticas são usadas para identificar anomalias.
title: Técnicas Estatísticas Usadas Na Detecção De Anomalias
feature: Anomaly Detection
role: User, Admin
exl-id: e9868296-e453-45ec-b874-b2aa1b37a1bf
TQID: https://experienceleague.adobe.com/4DIICc89-1ppuJWmUpJBrDrOU7MH78dYBTCHTqkBE2E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1101
ht-degree: 38%

---

# Técnicas estatísticas

A detecção de anomalias no Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar se uma observação deve ser considerada anômala ou não.

Dependendo da granularidade de data usada no relatório, três diferentes técnicas estatísticas são usadas, especificamente para a detecção de anomalias por hora, dia e semana/mês. Cada técnica estatística está descrita abaixo.

## Detecção de anomalias para granularidade diária

Para os relatórios de granularidade diária, o algoritmo considera vários fatores importantes para fornecer os resultados mais precisos possíveis. Primeiro, o algoritmo determina o tipo de modelo a aplicar com base nos dados disponíveis, dos quais o algoritmo seleciona entre uma de duas classes - um modelo baseado em séries de tempo ou um modelo de detecção de valores anômalos (chamado de filtragem funcional).

A seleção do modelo de série temporal baseia-se nas seguintes combinações para o tipo de erro, tendência e sazonalidade (ETS), conforme descrito por [Hyndman et al. (2008)](https://link.springer.com/book/10.1007/978-3-540-71918-2). Especificamente, o algoritmo tenta as seguintes combinações:

1. ANA (erro aditivo, sem tendência, sazonalidade aditiva)
1. AAA (erro aditivo, tendência aditiva, sazonalidade aditiva)
1. MNM (erro multiplicativo, nenhuma tendência, sazonalidade multiplicativa)
1. MNA (erro multiplicativo, nenhuma tendência, sazonalidade aditiva)
1. AAN (erro aditivo, tendência aditiva, sem sazonalidade)

O algoritmo testa a adequação de cada uma das combinações selecionando aquela com o melhor erro percentual absoluto médio (MAPE). No entanto, se o MAPE do melhor modelo de série temporal for superior a 15%, é aplicada a filtragem funcional. Normalmente, dados com um alto grau de repetição (por exemplo, semana sobre semana ou mês sobre mês) são os mais adequados com um modelo de série temporal.

Após a seleção do modelo, o algoritmo ajusta os resultados com base nos feriados e na sazonalidade ano a ano. Para feriados, o algoritmo verifica se algum dos seguintes feriados está presente no intervalo de datas do relatório:

* Dia da Memória
* Julho de 4
* Ação de Graças
* Black Friday
* Cyber Monday
* 24-26 de dezembro
* Janeiro de 1
* Dezembro de 31

Esses feriados foram selecionados com base em análises estatísticas extensivas em vários pontos de dados do cliente para identificar os feriados mais significativos para o maior número de tendências dos clientes. Embora a lista não seja exaustiva para todos os clientes ou ciclos comerciais, aplicar esses feriados melhora significativamente o desempenho geral do algoritmo para quase todos os conjuntos de dados dos clientes.

Uma vez selecionado o modelo e identificados os feriados no intervalo de datas do relatório, o algoritmo procede da seguinte maneira:

1. Constrói o período de referência da anomalia. Esse período inclui até 35 dias antes do intervalo de datas do relatório e um intervalo de datas correspondente um ano antes. Contabiliza os dias bissextos quando necessário, incluindo quaisquer feriados aplicáveis que tenham ocorrido num dia diferente do ano civil anterior.
1. Testa se os feriados do período atual (exceto o ano anterior) são anômalos com base nos dados mais recentes.
1. Se o feriado no intervalo de datas atual for anômalo, ajusta o valor esperado e o intervalo de confiança do feriado atual, dado o feriado do ano anterior (considerando 2 dias antes e depois). A correção para o feriado atual baseia-se no erro percentual absoluto médio mais baixo de:

   1. Efeitos aditivos
   1. Efeitos multiplicativos
   1. Diferença YoY

Observe a melhoria significativa no desempenho do Natal e do Ano Novo no seguinte exemplo:

![](assets/anomaly_statistics.png)

## Detecção de anomalias para granularidade horária

Os dados por hora dependem da mesma abordagem de algoritmo de série temporal que o algoritmo de granularidade diária. No entanto, ele se baseia fortemente em dois padrões de tendência: o ciclo de 24 horas, bem como o ciclo de fim de semana/dias úteis. Para capturar esses dois efeitos sazonais, o algoritmo por hora constrói dois modelos separados para um fim de semana e um dia da semana usando a mesma abordagem descrita acima.

As janelas de treinamento para tendências por hora dependem de uma janela de retrospectiva de 336 horas.

## Detecção de anomalias para granularidades semanais e mensais

As tendências semanais e mensais não exibem as mesmas tendências semanais ou diárias encontradas em granularidades diárias ou horárias, portanto, um algoritmo separado é usado. Para semanais e mensais, uma abordagem de detecção de valores atípicos em duas etapas é conhecida como o teste de desvio estendido generalizado (GESD). Este teste considera o número máximo de anomalias esperadas combinado com a abordagem de box plot ajustada (um método não paramétrico para a descoberta de outliers) para determinar o número máximo de outliers. As duas etapas são:

1. Função de box plot ajustada: essa função determina o número máximo de anomalias, dados de entrada.
1. Função GESD: aplicada aos dados de entrada com a saída da etapa 1.

A etapa de detecção de anomalias na sazonalidade YoY e em feriados subtrai os dados do ano passado dos dados deste ano. E então repete os dados usando o processo de duas etapas acima para verificar se as anomalias são sazonalmente apropriadas. Cada uma dessas granularidades de dados usa uma retrospectiva de 15 períodos, incluindo o intervalo de dados de relatório selecionado (15 meses ou 15 semanas) e um intervalo de dados correspondente há um ano para treinamento.

## Técnicas estatísticas usadas na Análise de contribuição

A Análise de contribuição é um processo intensivo de aprendizado de máquina criado para descobrir colaboradores de uma anomalia observada no Adobe Analytics. O objetivo é auxiliar a encontrar áreas de foco ou oportunidades para análises adicionais de maneira muito mais rápida do que seria possível de outra forma.

A Análise de contribuição executa um algoritmo de duas partes para cada item de dimensão disponível no relatório de Análise de contribuição do usuário. O algoritmo opera nesta ordem:

1. Para cada dimensão, ele calcula a estatística do teste V de Cramer. No seguinte exemplo, considere uma tabela de contingência com exibições de página por país ao longo de dois períodos:

   ![](assets/contingency_table.png)

   Na Tabela 1, o V de Cramer pode ser usado para medir a associação entre as exibições de página por países para o período 1 (por exemplo, histórico) e o período 2 (por exemplo, o dia em que a anomalia ocorre). Um valor baixo do V de Cramer implica um baixo nível de associação. Os intervalos do V de Cramer variam de 0 (nenhuma associação) a 1 (associação completa). A estatística V de Cramer pode ser calculada:

   ![](assets/cramers-v.png)

1. Para cada item de dimensão, o Residual da pessoa (PR) é usado para medir a associação entre a métrica anômala e cada item de dimensão. PR segue uma distribuição normal padrão, que permite ao algoritmo comparar as PRs de duas variáveis aleatórias mesmo se os desvios não são comparáveis. Na prática, o erro não é conhecido e é estimado usando correção de amostra finita.

   No exemplo anterior no quadro 1, a PR, com correção da amostra finita para o país i e o período de tempo 2, é dada por

   ![](assets/persons-residual.png)

   em que

   ![](assets/pr-example.png)

   (Uma fórmula semelhante pode ser obtida para o período de tempo 1.)

   Para os resultados finais, a pontuação para cada item de dimensão é ponderada pela medida V de Cramer e ajustada para um número entre 0 e 1 para fornecer sua pontuação de contribuição.
