---
description: Saiba como criar uma solicitação de detecção de anomalias no Report Builder.
title: Como configurar uma solicitação de detecção de anomalias
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 72%

---

# Configurar uma solicitação de detecção de anomalias

Para criar uma solicitação de detecção de anomalias no Report Builder:

1. Selecione um relatório de tendências, como um **[!UICONTROL relatório de Métricas do site]** > **[!UICONTROL Relatório de]** tráfego.
1. No menu [!UICONTROL Aplicar granularidade], selecione **[!UICONTROL Dia]**.

   >[!NOTE]
   >
   >O menu [!UICONTROL Detecção de anomalias] estará disponível somente após a seleção da granularidade do dia. Os 30 dias anteriores de dados são utilizados como dados estatísticos durante o período de treinamento, qualquer que seja o intervalo de datas selecionado.

1. Após configurar os intervalos de datas, clique em **[!UICONTROL Próximo]**.

   Adicione uma métrica à etapa 2 de 2 do assistente de solicitações, como **[!UICONTROL Visitas]**.

   Para a métrica adicionada, clique no link **[!UICONTROL Nenhum]**.

   ![Captura de tela mostrando a Detecção de anomalias, a opção Inserir e, em seguida, as opções de Inserir para Limite inferior e superior, e as opções esperadas.](assets/anomaly_select.png)

1. Selecione **[!UICONTROL Detecção de anomalias]** > **[!UICONTROL `<selection>`]**.

   ![Captura de tela que mostra a Etapa 2 do assistente de solicitações - Relatório de tráfego.](assets/anomaly_visit.png)

   Ao selecionar uma destas opções, o sistema cria cópias da detecção de anomalias da métrica original. Por exemplo, para a métrica Visitas, uma métrica de Visitas de limite inferior é adicionada ao grupo [!UICONTROL Métrica].
1. Clique em **[!UICONTROL Concluir]** e selecione a célula para saída em Excel.

   Consulte [Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) para definições.
