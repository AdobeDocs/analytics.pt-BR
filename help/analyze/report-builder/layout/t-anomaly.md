---
description: Essas etapas descrevem como criar uma solicitação de detecção de anomalias no construtor de relatórios.
title: Configurar uma solicitação de detecção de anomalias
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configurar uma solicitação de detecção de anomalias

Essas etapas descrevem como criar uma solicitação de detecção de anomalias no construtor de relatórios.

1. Selecione um relatório de tendências, como um **relatório deMétricas do site** &gt; **[!UICONTROL Relatório de]** tráfego.
1. No menu [!UICONTROL Aplicar granularidade]**, selecione[!UICONTROL Dia]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. Os 30 dias anteriores de dados são utilizados como dados estatísticos durante o período de treinamento, qualquer que seja o intervalo de datas selecionado.

1. After configuring date ranges, click **[!UICONTROL Next]**.

   Resultado da etapa 1. On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   Resultado da etapa 1. For the added metric, click the **[!UICONTROL None]** link.

   ![Resultado da etapa](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![Informações da etapa](assets/anomaly_visit.png)

   Ao selecionar uma destas opções, o sistema cria cópias da detecção de anomalias da métrica original. Por exemplo, para a métrica Visitas, uma métrica de Visitas de limite inferior é adicionada ao grupo [!UICONTROL Métrica].
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) for definitions.
