---
description: A detecção de anomalias na Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar se uma observação deve ser considerada anômala ou não.
seo-description: A detecção de anomalias na Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar se uma observação deve ser considerada anômala ou não.
seo-title: Técnicas estatísticas usadas na detecção de anomalias
title: Técnicas estatísticas usadas na detecção de anomalias
uuid: b 6 ef 6 a 2 e -0836-4 c 9 a-bf 7 e -01910199 bb 92
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Técnicas estatísticas usadas na detecção de anomalias

A detecção de anomalias na Analysis Workspace usa uma série de técnicas estatísticas avançadas para determinar se uma observação deve ser considerada anômala ou não.

Dependendo da granularidade de data usada no relatório, 3 diferentes técnicas estatísticas são usadas - especificamente para detecção de anomalias por hora, dia, semana/mês. Cada técnica estatística está descrita abaixo.

## Anomaly detection for daily granularity {#section_758ACA3C0A6B4D399563ECABFB8316FA}

Para os relatórios de granularidade diária, o algoritmo considera vários fatores importantes para fornecer os resultados mais precisos possíveis. Primeiro, o algoritmo determina o tipo de modelo a ser aplicado com base nos dados disponíveis que selecionamos entre uma de duas classes - um modelo com base em séries de tempo ou um modelo de detecção de valores atípicos (chamado de filtragem funcional).

A seleção do modelo da série de tempo se baseia nas seguintes combinações para tipo de erro, tendência e sazonalidade (ETS), conforme descrito por [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168). Especificamente, o algoritmo tenta as seguintes combinações:

1. ANA (erro aditivo, nenhuma tendência, sazonalidade aditiva)
1. AAA (erro aditivo, tendência aditiva, sazonalidade aditiva)
1. MNM (erro multiplicativo, nenhuma tendência, sazonalidade multiplicativa)
1. MNA (erro multiplicativo, nenhuma tendência, sazonalidade aditiva)
1. AAN (erro aditivo, tendência aditiva, nenhuma sazonalidade)

O algoritmo testa a adequação de cada uma dessas combinações, selecionando aquela com o melhor erro percentual médio absoluto (MAPE). Contudo, se o MAPE do modelo de série de tempo for maior que 15%, a filtragem funcional é aplicada. Geralmente, os dados com um grau maior de repetição (por exemplo, semana após semana ou mês após mês) são mais adequados para um modelo de série de tempo.

Após a seleção do modelo, o algoritmo ajusta os resultados com base em feriados e sazonalidade ano a ano. Para feriados, o algoritmo verifica se os seguintes feriados estão presentes no intervalo de datas do relatório:

* Memorial Day (somente EUA)
* 4 de julho (somente EUA)
* Dia de Ação de Graças (somente EUA)
* Black Friday (somente EUA)
* Cyber Monday (somente EUA)
* 24-26 de dezembro
* 1º de janeiro
* 31 de dezembro

Esses feriados foram selecionados com base em análises estatísticas extensivas em vários pontos de dados do cliente para identificar os feriados mais significativos para o maior número de tendências dos clientes. Embora a lista não seja exaustiva para todos os clientes ou ciclos comerciais, descobrimos que aplicar esses feriados melhorou significativamente o desempenho geral do algoritmo para praticamente todos os conjuntos de dados dos clientes.

Assim que o modelo tiver sido selecionado e os feriados tiverem sido identificados no intervalo de datas do relatório, o algoritmo procede da seguinte maneira:

1. Construir o período de referência da anomalia - isso inclui até 35 dias antes do intervalo de datas do relatório e um intervalo de datas correspondente 1 ano antes (contabilidade por dias de salto quando necessário e inclusivo de quaisquer feriados aplicáveis que podem ter ocorrido em um dia de calendário diferente do ano anterior).
1. Teste se os feriados no período atual (exceto o ano anterior) são anômalos com base nos dados mais recentes.
1. Se o feriado no intervalo de datas atual for anômalo, ajuste o valor esperado e o intervalo de confiança do feriado atual, dado o feriado do ano anterior (considerando 2 dias antes e depois). A correção para o feriado atual se baseia no menor erro percentual médio absoluto de:

   1. Efeitos aditivos
   1. Efeitos multiplicativos
   1. Diferença YoY

Observe a melhoria significativa no desempenho do Dia de Natal e no Dia de Ano Novo no seguinte exemplo:

![](assets/anomaly_statistics.png)

## Anomaly detection for hourly granularity {#section_014C9E9209AF43F8A03D5D46E3B3AEE7}

Os dados horários utilizam a mesma abordagem de algoritmo de séries de tempo que o algoritmo com granularidade diária. Contudo, depende muito de dois padrões de tendências: o ciclo de 24 horas, bem como o ciclo de final de semana/dia da semana. Para capturar esses dois efeitos sazonais, o algoritmo horário constrói dois modelos separados para uma semana e um dia da semana usando a mesma abordagem descrita anteriormente.

A janela de treinamento para tendências horárias depende de uma janela de retrospectiva de 336 horas.

## Anomaly detection for weekly and monthly granularities {#section_5D421576BFBC4B24A58DFCC0A6407545}

As tendências semanais e mensais não exibem as mesmas tendências semanais ou diárias encontradas nas granularidades diária ou horária, portanto, um algoritmo separado é usado. Para semanal e mensal, uma abordagem de detecção de valor atípicos de duas etapas é usada, conhecida como teste de GESD (Generalized Extreme Studentized Deviate). Este teste considera o número máximo de anomalias esperadas combinado com a abordagem de box plot ajustada (um método não paramétrico para a descoberta de valores atípicos) para determinar o número máximo de valores atípicos. As duas etapas são:

1. Função de box plot ajustado: esta função determina o número máximo de anomalias nos dados inseridos.
1. Função GESD: aplicada aos dados de entrada com a saída da etapa 1.

A etapa de detecção de anomalias na sazonalidade YoY e em feriados subtrai os dados do ano anterior dos dados do ano atual e reitera os dados usando o processo de duas etapas acima para verificar se as anomalias são sazonalmente apropriadas. Cada uma dessas granularidades de dados usa uma retrospectiva de 15 períodos, incluindo o intervalo de dados de relatório selecionado (15 meses ou 15 semanas) e um intervalo de dados correspondente há um ano para treinamento.
