---
description: Explica as três opções de Compatibilidade do produto.
title: Compatibilidade de métrica
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: d9f95b12a43305cecff1190e6544334f3b48835d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 68%

---

# Compatibilidade de métrica {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilidade do produto"
>abstract="“Uma pequena quantidade de critérios de métrica disponíveis não é compatível com todas as ferramentas do Adobe Analytics. As ferramentas compatíveis com a métrica estão indicadas nesta lista. Para tornar uma métrica compatível com todas as ferramentas do Adobe Analytics, tente editar os critérios."

Este artigo explica as três opções de compatibilidade de produto.

Ao criar métricas calculadas no construtor de métricas calculadas, sua métrica será exibida como compatível com 1 ou mais ferramentas no Adobe Analytics. Por exemplo, Analysis Workspace, Reports &amp; Analytics, Data Warehouse.


| Compatível com | Descrição |
| --- | --- |
| Dados atuais | A opção [!UICONTROL Incluir dados atuais] no Adobe Analytics permite visualizar os dados mais recentes do Analytics, geralmente antes que os dados sejam totalmente processados e finalizados. [!UICONTROL Os dados atuais] exibem a maioria das métricas em minutos, fornecendo dados acionáveis para tomada de decisão rápida. [!UICONTROL Os Dados Atuais] só dão suporte a métricas calculadas (que incluem multiplicação, divisão, adição e subtração). [!UICONTROL Os Dados Atuais] não dão suporte a métricas calculadas avançadas (que contêm segmentos ou funções). |
| Dados totalmente processados | Dados totalmente processados e que incluem segmentos e classificações. Se você preferir exibir todas as métricas depois que os dados forem processados, será possível desativar os [!UICONTROL Dados atuais] removendo usuários do grupo Usuários de dados atuais. |
| Relatórios de canal de marketing | Métricas com alocação de primeiro contato são compatíveis apenas com os relatórios de Canal de marketing. |
