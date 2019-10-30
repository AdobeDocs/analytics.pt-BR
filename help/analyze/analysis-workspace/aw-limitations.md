---
description: 'null'
seo-description: 'null'
seo-title: Limitações do espaço de trabalho, limitações conhecidas na Analysis Workspace
title: Limitações conhecidas na Analysis Workspace
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Limitações conhecidas na Analysis Workspace

Esta é uma lista de limitações conhecidas na Analysis Workspace e seus componentes relacionados:

## Tabela

* Colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usadas como linhas de uma tabela.
* Criar métrica a partir da seleção é desativada quando os segmentos são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas à data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* O total de linhas da tabela não pode ter tendência quando Calcular totais resumindo a configuração de valores de linhas (normalmente usada com itens de linhas estáticas).
* [!UICONTROL A Análise] de contribuição pode ser executada [!UICONTROL somente] na granularidade _diária_. Não pode ser executado em relação aos dados por [!UICONTROL hora], [!UICONTROL semana]etc.

## Visualizações

* As visualizações que aproveitam a segmentação, como [!UICONTROL Fallout], [!UICONTROL Fluxo], [!UICONTROL Coorte]e [!UICONTROL Histograma], não podem aceitar métricas calculadas como entradas.
* [!UICONTROL Fluxo]: As dimensões de entrada/saída, por exemplo, página de entrada, não podem ser usadas em Fluxo.
* [!UICONTROL Coorte]: Não é possível usar números inteiros como critérios de coorte.

## Painéis

* Comparação de segmentos: O segmento [!UICONTROL Todos os outros] não será criado se um modelo de segmento for usado na zona inicial.

## Componentes &gt; Segmentos

* Determinadas métricas e dimensões não são segmentáveis, como [!UICONTROL Ocorrências], Visitantes únicos etc.
* Determinados componentes e operadores não estarão disponíveis se um segmento for criado a partir do Workspace (em vez de ser criado a partir de [!UICONTROL Componentes &gt; Segmentos]). Por exemplo, Endereço IP.

## Componentes &gt; Métricas calculadas

* Métricas calculadas não podem ser usadas em determinadas visualizações. Consulte 'Visualizações' acima.
* Métricas calculadas não podem ser usadas no painel [!UICONTROL Atribuição] , já que as próprias métricas calculadas podem incluir modelos de atribuição separados.
* Determinados componentes e operadores não estarão disponíveis se uma métrica calculada for criada a partir do Workspace (em vez de ser criada a partir de [!UICONTROL Componentes &gt; Segmentos]). Por exemplo, Endereço IP.

## Componentes &gt; Intervalos de datas

* Os intervalos de datas personalizados não são compatíveis com [!UICONTROL Este dia do ano]passado, [!UICONTROL Este dia do mês]passado etc.

## Componentes &gt; Conjuntos de relatórios virtuais

* Quando o processamento de tempo do relatório está ativado, determinados componentes não são suportados. Para obter uma lista completa, consulte Processamento [de tempo do](/help/components/vrs/vrs-report-time-processing.md)relatório.

## Componentes &gt; Configurações de relatório

* Algumas das configurações na página Configurações [!UICONTROL do] relatório não se aplicam. A Analysis Workspace usa somente as configurações [!UICONTROL Idioma/Moeda/Codificação] na parte inferior: Separador [!UICONTROL de]milhares, Codificação [!UICONTROL de relatório]agendada e Caractere [!UICONTROL separador]CSV.

## Attribution IQ

* Um subconjunto de métricas não é suportado no QI [!UICONTROL de atribuição]. Para obter uma lista completa, consulte as Perguntas frequentes sobre [IQ de](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md)atribuição.