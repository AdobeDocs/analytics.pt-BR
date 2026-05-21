---
description: Ative dimensões para que o Activity Map possa coletar dados.
title: Relatórios do Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
TQID: https://experienceleague.adobe.com/GiBhdUMAX5P9zxxDAVUZPcaeKpnezKvDn3MB0g95DH0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 31%

---

# Relatórios do Activity Map

Permite que você habilite dimensões para uso com o [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de Relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]**

Esta seção da documentação se concentra em ativar dimensões que o Activity Map usa. Consulte [visão geral do Activity Map](/help/analyze/activity-map/overview.md) para obter mais informações sobre sobreposição, variáveis de implementação e dimensões.

Ao selecionar o botão **[!UICONTROL Habilitar Relatórios do Activity Map]**, as seguintes dimensões são criadas:

* [[!UICONTROL Link do Activity Map]](/help/components/dimensions/activity-map-link.md): o nome do link clicado.
* [[!UICONTROL Região do Activity Map]](/help/components/dimensions/activity-map-region.md): o nome da região clicada.
* [[!UICONTROL Página do Activity Map]](/help/components/dimensions/activity-map-page.md): o nome da página no momento em que o link foi clicado.
* [[!UICONTROL Link do Activity Map por região]](/help/components/dimensions/activity-map-link-by-region.md): um valor concatenado de link do Activity Map e região do Activity Map.

Depois de habilitada, sua implementação pode começar a enviar dados para essas dimensões para uso no [Analysis Workspace](/help/analyze/analysis-workspace/home.md) e na [sobreposição de extensão do navegador](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Quando você ativa o Activity Map para um conjunto de relatórios, ele é ativado permanentemente sem nenhuma maneira de desativá-lo no futuro.
