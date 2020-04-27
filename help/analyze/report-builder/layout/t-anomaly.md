---
description: Essas etapas descrevem como criar uma solicitação de detecção de anomalias no Report Builder.
title: Configurar uma solicitação de detecção de anomalias
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configurar uma solicitação de detecção de anomalias

Essas etapas descrevem como criar uma solicitação de detecção de anomalias no Report Builder.

1. Selecione um relatório de tendências, como um **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** relatório.
1. No [!UICONTROL Apply Granularity] menu, selecione **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. Os 30 dias anteriores de dados são utilizados como dados estatísticos durante o período de treinamento, qualquer que seja o intervalo de datas selecionado.

1. After configuring date ranges, click **[!UICONTROL Next]**.

   Resultado da etapa 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   Resultado da etapa 1. For the added metric, click the **[!UICONTROL None]** link.

   ![Resultado da etapa](assets/anomaly_select.png)

1. Selecionar **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Informações da etapa](assets/anomaly_visit.png)

   Ao selecionar uma destas opções, o sistema cria cópias da detecção de anomalias da métrica original. For example, for the Visit metric, a Lower Bound Visit metric is added to the [!UICONTROL Metric] group.
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   Consulte [Detecção de anomalias](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) para definições.
