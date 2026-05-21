---
description: Os conjuntos de relatórios virtuais podem ser gerenciados para incluir e excluir componentes no Analysis Workspace.
title: Curadoria de componentes do conjunto de relatórios virtual
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
TQID: https://experienceleague.adobe.com/j86dD5Yzd6GIoQOzhHsU8YbShQiODtbU8aCdM3UxRMg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 38%

---

# Curadoria de componentes do conjunto de relatórios virtual

Os conjuntos de relatórios virtuais podem ser gerenciados para incluir e excluir componentes no Analysis Workspace.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Curadoria de componentes](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/virtual-report-suites/component-curation-in-virtual-report-suites){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!NOTE]
>
>As alterações foram feitas nos componentes que são visíveis em projetos preparados do Workspace e em conjuntos de relatórios virtuais preparados. Anteriormente, qualquer pessoa podia ver componentes não preparados ao clicar no botão **[!UICONTROL Mostrar todos os componentes]**. A [experiência atualizada de preparação](/help/analyze/analysis-workspace/curate-share/curate.md) permite um controle mais polido sobre quais componentes ficam visíveis.

Para permitir a curadoria de componentes,

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de relatórios virtuais]** > **[!UICONTROL Criar novo conjunto de relatórios virtual]**.
1. Depois de definir as **[!UICONTROL Configurações]**, clique na guia **[!UICONTROL Componentes]**.

1. Marque a caixa de seleção **[!UICONTROL Habilitar personalização de componentes do conjunto de relatórios virtual]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Se a personalização de componentes estiver habilitada, o conjunto de relatórios virtuais poderá ser acessado **somente na Analysis Workspace** e não em:
   >
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* API em relatórios do Analytics

   Depois de marcado, você pode adicionar os componentes que gostaria de incluir no conjunto de relatórios virtual arrastando os componentes aplicáveis da coluna &quot;componentes excluídos&quot; para a coluna &quot;componentes incluídos&quot;. Os componentes que podem ser incluídos e excluídos são:

   * Dimensões
   * Métricas
   * Segmentos
   * Intervalos de datas

   >[!NOTE]
   >
   >Não há necessidade de *compartilhar* componentes com curadoria (segmentos, métricas calculadas, intervalos de datas). Eles sempre estarão visíveis na Analysis Workspace se tiverem curadoria para o conjunto de relatórios virtual, mesmo se não forem compartilhados.

1. Além disso, você pode filtrar ou pesquisar os componentes e adicionar toda a seleção filtrada à coluna incluída clicando em **[!UICONTROL Adicionar tudo]**.

   ![](assets/vrs-add-all.png)

## Renomear componentes {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Você pode alterar os nomes de exibição dos componentes incluídos específicos do conjunto de relatórios virtual. Por exemplo, se você deseja incluir o Nome da página no conjunto de relatórios virtual, mas deseja renomeá-lo para um contexto mais móvel, é possível alterá-lo para App Screens. O novo nome é exibido no Analysis Workspace sempre que esse conjunto de relatórios virtual é usado.

![](assets/vrs-rename-component.png)

No Analysis Workspace, clique no ícone de informações de qualquer componente incluído para revelar o nome original do componente renomeado:

![](assets/vrs-aw-renamed.png)

## Grupos de componentes {#section_483BEC76F49E46ADAAA03F0A12E48426}

Use grupos de componentes para fazer adições de componentes em massa ao conjunto de relatórios virtual. Por exemplo, se você quiser importar um conjunto padrão de componentes específicos para a análise de aplicativos móveis, selecione o grupo de aplicativos móveis. Um conjunto correspondente de dimensões e métricas (já renomeado) é adicionado automaticamente à lista Incluídos do conjunto de relatórios virtual.

![](assets/vrs-comp-grp.png)

## Comportamento do Workspace {#section_6C32F8B642804C0097FCB14E21028D4A}

Para obter mais informações sobre a preparação na Analysis Workspace, consulte [Preparar e compartilhar um projeto](/help/analyze/analysis-workspace/curate-share/curate.md).
