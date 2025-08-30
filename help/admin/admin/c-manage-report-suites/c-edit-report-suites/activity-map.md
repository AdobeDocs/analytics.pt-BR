---
description: Ative dimensões para que o Activity Map possa coletar dados.
title: Relatórios do Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Relatórios do Activity Map

Permite que você habilite dimensões para uso com o [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de Relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]**

Esta seção da documentação se concentra em ativar dimensões que o Activity Map usa. Consulte [visão geral do Activity Map](/help/analyze/activity-map/overview.md) para obter mais informações sobre sobreposição, variáveis de implementação e dimensões.

Ao selecionar o botão **[!UICONTROL Habilitar Relatórios do Activity Map]**, as seguintes dimensões são criadas:

* [[!UICONTROL Link do Activity Map]](/help/components/dimensions/activity-map-link.md): o nome do link clicado.
* [[!UICONTROL Região do Activity Map]](/help/components/dimensions/activity-map-region.md): o nome da região clicada.
* [[!UICONTROL Página do Activity Map]](/help/components/dimensions/activity-map-page.md): o nome da página no momento em que o link foi clicado.
* [[!UICONTROL Link do Activity Map por Região]](/help/components/dimensions/activity-map-link-by-region.md): um valor concatenado de Link do Activity Map e Região do Activity Map.

Depois de habilitada, sua implementação pode começar a enviar dados para essas dimensões para uso no [Analysis Workspace](/help/analyze/analysis-workspace/home.md) e na [sobreposição de extensão do navegador](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Quando você ativa o Activity Map para um conjunto de relatórios, ele é ativado permanentemente sem nenhuma maneira de desativá-lo no futuro.
