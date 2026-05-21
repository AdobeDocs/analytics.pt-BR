---
description: Saiba como criar uma solicitação de detecção de anomalias no Report Builder.
title: Como configurar uma solicitação de detecção de anomalias
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: c67272a6-888e-425e-9e97-a87304637eed
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 54%

---

# Configurar uma solicitação de detecção de anomalias

{{legacy-arb}}

Para criar uma solicitação de detecção de anomalias no Report Builder:

1. Selecione um relatório de tendências, como um **[!UICONTROL relatório de Métricas do site]** > **[!UICONTROL Relatório de]** tráfego.
1. No menu [!UICONTROL Aplicar granularidade], selecione **[!UICONTROL Dia]**.

   >[!NOTE]
   >
   >O menu [!UICONTROL Detecção de anomalias] estará disponível somente após a seleção da granularidade do dia. Os 30 dias anteriores de dados são utilizados como dados estatísticos durante o período de treinamento, qualquer que seja o intervalo de datas selecionado.

1. Após configurar os intervalos de datas, clique em **[!UICONTROL Próximo]**.

   Adicione uma métrica à etapa 2 de 2 do assistente de solicitações, como **[!UICONTROL Visitas]**.

   Para a métrica adicionada, clique no link **[!UICONTROL Nenhum]**.

   ![Captura de tela mostrando a Detecção de Anomalias, depois as opções Inserir e inserir para Limite Inferior e Superior, e as opções esperadas.](assets/anomaly_select.png)

1. Selecione **[!UICONTROL Detecção de anomalias]** > **[!UICONTROL `<selection>`]**.

   ![Captura de tela mostrando a Etapa 2 do Assistente de solicitações - Relatório de tráfego.](assets/anomaly_visit.png)

   Ao selecionar uma dessas opções, o sistema cria cópias da Detecção de anomalias da métrica original. Por exemplo, para a métrica Visita, uma métrica Visita de limite inferior é adicionada ao grupo [!UICONTROL Métrica].
1. Clique em **[!UICONTROL Concluir]** e selecione a célula para saída em Excel.

   Consulte [Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) para definições.
