---
description: Saiba quais técnicas estatísticas são usadas para identificar anomalias.
title: Técnicas Estatísticas Usadas Na Detecção De Anomalias
feature: Anomaly Detection
role: User, Admin
exl-id: e9868296-e453-45ec-b874-b2aa1b37a1bf
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 70%

---

# Técnicas estatísticas

A detecção de anomalias no Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar se uma observação deve ser considerada anômala ou não.

Dependendo da granularidade de data usada no relatório, três diferentes técnicas estatísticas são usadas, especificamente para a detecção de anomalias por hora, dia e semana/mês. Cada técnica estatística está descrita abaixo.

## Detecção de anomalias para granularidade diária

Para os relatórios de granularidade diária, o algoritmo considera vários fatores importantes para fornecer os resultados mais precisos possíveis. Primeiro, o algoritmo determina o tipo de modelo a aplicar com base nos dados disponíveis, dos quais o algoritmo seleciona entre uma de duas classes - um modelo baseado em séries de tempo ou um modelo de detecção de valores anômalos (chamado de filtragem funcional).

A seleção do modelo da série de tempo se baseia nas seguintes combinações para tipo de erro, tendência e sazonalidade (ETS), conforme descrito por [Hyndman et al. (2008)](https://link.springer.com/book/10.1007/978-3-540-71918-2). Especificamente, o algoritmo tenta as seguintes combinações:

1. ANA (erro aditivo, nenhuma tendência, sazonalidade aditiva)
1. AAA (erro aditivo, tendência aditiva, sazonalidade aditiva)
1. MNM (erro multiplicativo, nenhuma tendência, sazonalidade multiplicativa)
1. MNA (erro multiplicativo, nenhuma tendência, sazonalidade aditiva)
1. AAN (erro aditivo, tendência aditiva, nenhuma sazonalidade)

O algoritmo testa a adequação de cada uma das combinações selecionando aquela com o melhor erro percentual absoluto médio (MAPE). Contudo, se o MAPE do modelo de série de tempo for maior que 15%, a filtragem funcional é aplicada. Normalmente, dados com um alto grau de repetição (por exemplo, semana sobre semana ou mês sobre mês) são os mais adequados com um modelo de série temporal.

Após a seleção do modelo, o algoritmo ajusta os resultados com base em feriados e sazonalidade ano a ano. Para feriados, o algoritmo verifica se os seguintes feriados estão presentes no intervalo de datas do relatório:

* Memorial Day (somente EUA)
* Julho de 4
* Dia de Ação de Graças (somente EUA)
* Black Friday (somente EUA)
* Cyber Monday (somente EUA)
* 24-26 de dezembro
* Janeiro de 1
* Dezembro de 31

Esses feriados foram selecionados com base em análises estatísticas extensivas em vários pontos de dados do cliente para identificar os feriados mais significativos para o maior número de tendências dos clientes. Embora a lista não seja exaustiva para todos os clientes ou ciclos comerciais, aplicar esses feriados melhora significativamente o desempenho geral do algoritmo para quase todos os conjuntos de dados dos clientes.

Uma vez selecionado o modelo e identificados os feriados no intervalo de datas do relatório, o algoritmo procede da seguinte maneira:

1. Constrói o período de referência da anomalia. Esse período inclui até 35 dias antes do intervalo de datas do relatório e um intervalo de datas correspondente um ano antes. Contabiliza os dias bissextos quando necessário, incluindo quaisquer feriados aplicáveis que tenham ocorrido num dia diferente do ano civil anterior.
1. Testa se os feriados do período atual (exceto o ano anterior) são anômalos com base nos dados mais recentes.
1. Se o feriado no intervalo de datas atual for anômalo, ajusta o valor esperado e o intervalo de confiança do feriado atual, dado o feriado do ano anterior (considerando 2 dias antes e depois). A correção para o feriado atual se baseia no menor erro percentual médio absoluto de:

   1. Efeitos aditivos
   1. Efeitos multiplicativos
   1. Diferença YoY

Observe a melhoria significativa no desempenho do Natal e do Ano Novo no seguinte exemplo:

![](assets/anomaly_statistics.png)

## Detecção de anomalias para granularidade horária

Os dados horários utilizam a mesma abordagem de algoritmo de séries de tempo que o algoritmo com granularidade diária. Contudo, depende muito de dois padrões de tendências: o ciclo de 24 horas, bem como o ciclo de final de semana/dia da semana. Para capturar esses dois efeitos sazonais, o algoritmo horário constrói dois modelos separados para uma semana e um dia da semana usando a mesma abordagem descrita anteriormente.

A janela de treinamento para tendências horárias depende de uma janela de retrospectiva de 336 horas.

## Detecção de anomalias para granularidades semanais e mensais

As tendências semanais e mensais não exibem as mesmas tendências semanais ou diárias encontradas nas granularidades diária ou horária, portanto, um algoritmo separado é usado. Para semanais e mensais, uma abordagem de detecção de valores atípicos em duas etapas é conhecida como o teste de desvio estendido generalizado (GESD). Este teste considera o número máximo de anomalias esperadas combinado com a abordagem de box plot ajustada (um método não paramétrico para a descoberta de outliers) para determinar o número máximo de outliers. As duas etapas são:

1. Função de box plot ajustado: esta função determina o número máximo de anomalias nos dados inseridos.
1. Função GESD: aplicada aos dados de entrada com a saída da etapa 1.

A etapa de detecção de anomalias na sazonalidade YoY e em feriados subtrai os dados do ano passado dos dados deste ano. E então repete os dados usando o processo de duas etapas acima para verificar se as anomalias são sazonalmente apropriadas. Cada uma dessas granularidades de dados usa uma retrospectiva de 15 períodos, incluindo o intervalo de dados de relatório selecionado (15 meses ou 15 semanas) e um intervalo de dados correspondente há um ano para treinamento.

## Técnicas estatísticas usadas na Análise de contribuição

A Análise de contribuição é um processo intensivo de aprendizado de máquina projetado para descobrir contribuintes para uma anomalia observada no Adobe Analytics. O objetivo é auxiliar a encontrar áreas de foco ou oportunidades para análises adicionais de maneira muito mais rápida do que seria possível de outra forma.

A Análise de contribuição executa um algoritmo de duas partes para cada item de dimensão disponível no relatório de Análise de contribuição do usuário. O algoritmo opera nesta ordem:

1. Para cada dimensão, ele calcula a estatística do teste V de Cramer. No seguinte exemplo, considere uma tabela de contingência com exibições de página por país ao longo de dois períodos:

   ![](assets/contingency_table.png)

   Na Tabela 1, o V de Cramer pode ser usado para medir a associação entre as exibições de página por países para o período 1 (por exemplo, histórico) e o período 2 (por exemplo, o dia em que a anomalia ocorre). Um valor baixo do V de Cramer implica um baixo nível de associação. Os intervalos do V de Cramer variam de 0 (nenhuma associação) a 1 (associação completa). A estatística V de Cramer pode ser calculada:

   ![](assets/cramers-v.png)

1. Para cada item de dimensão, o Residual da pessoa (PR) é usado para medir a associação entre a métrica anômala e cada item de dimensão. O PR segue uma distribuição normal padrão, que permite ao algoritmo comparar PRs de duas variáveis aleatórias, mesmo que os desvios não sejam comparáveis. Na prática, o erro não é conhecido e é estimado usando correção de amostra finita.

   No exemplo anterior no quadro 1, a PR, com correção da amostra finita para o país i e o período de tempo 2, é dada por

   ![](assets/persons-residual.png)

   onde

   ![](assets/pr-example.png)

   (Uma fórmula semelhante pode ser obtida para o período de tempo 1.)

   Para os resultados finais, a pontuação para cada item de dimensão é ponderada pela medida V de Cramer e ajustada para um número entre 0 e 1 para fornecer sua pontuação de contribuição.
