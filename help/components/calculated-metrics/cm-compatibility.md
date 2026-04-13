---
description: Explica as três opções de Compatibilidade do produto.
title: Compatibilidade de métrica
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 57%

---

# Compatibilidade de métrica {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilidade do produto"
>abstract="Uma pequena quantidade de critérios de métrica disponíveis não é compatível com todas as ferramentas do Adobe Analytics. As ferramentas compatíveis com a métrica estão indicadas nesta lista. Para tornar uma métrica compatível com todas as ferramentas do Adobe Analytics, tente editar os critérios."

This article explains the three product compatibility options.

When you create calculated metrics in the calculated metric builder, your metric will show as compatible with one or more tools within Adobe Analytics.


| Compatible with | Descrição |
| --- | --- |
| **[!UICONTROL Dados atuais]** | A opção [!UICONTROL Incluir dados atuais] no Adobe Analytics permite visualizar os dados mais recentes do Analytics, geralmente antes que os dados sejam totalmente processados e finalizados. [!UICONTROL Os dados atuais] exibem a maioria das métricas em minutos, fornecendo dados acionáveis para tomada de decisão rápida. [!UICONTROL Current Data] supports calculated metrics only (those that include multiplication, division, addition, and subtraction.) [!UICONTROL Current Data] does not support advanced calculated metrics (that contain segments or functions). |
| **[!UICONTROL Fully Processed Data]** | Data that is fully processed and includes segments and classifications. Se você preferir exibir todas as métricas depois que os dados forem processados, será possível desativar os [!UICONTROL Dados atuais] removendo usuários do grupo Usuários de dados atuais. |
| **[!UICONTROL Marketing Channel Reports]** | Metrics with first-touch allocation are compatible only with Marketing Channel reports. |
