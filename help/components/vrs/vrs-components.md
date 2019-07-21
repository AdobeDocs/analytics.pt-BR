---
description: Conjuntos de relatórios virtuais podem ser curados para incluir e excluir componentes na Analysis Workspace.
seo-description: Conjuntos de relatórios virtuais podem ser curados para incluir e excluir componentes na Analysis Workspace.
seo-title: Curadoria do componente de conjunto de relatórios virtual
title: Curadoria do componente de conjunto de relatórios virtual
uuid: 6 c 6 a 4071-22 ad -4 e 8 c-b 1 ed -140 b 2 aa 04 f 76
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Curadoria do componente de conjunto de relatórios virtual

Conjuntos de relatórios virtuais podem ser curados para incluir e excluir componentes na Analysis Workspace.

>[!NOTE]
>
>As alterações foram feitas aos componentes que são visíveis por administradores e não administradores em projetos preparados da Workspace e em conjuntos de relatórios virtuais preparados (VRSs). Anteriormente, qualquer pessoa podia ver componentes não preparados ao clicar no botão **[!UICONTROL Mostrar todos os componentes]**. A [experiência atualizada de preparação](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate-projects-vrs.html) permite um controle mais polido sobre quais componentes ficam visíveis.

Para permitir a curadoria de componentes,

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]** &gt; **[!UICONTROL Create new virtual report suite]**.
1. Depois de definir as **[!UICONTROL Configurações]**, clique na guia **Componentes[!UICONTROL .]**

1. Marque a caixa de seleção **[!UICONTROL Habilitar personalização de componentes de conjuntos de relatórios virtuais]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >If component customization is enabled, the virtual report suite is accessible **only in Analysis Workspace** and is not accessible in the following:

   * [!UICONTROL Reports &amp; Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * API em relatórios do Analytics
   Uma vez verificado, você pode adicionar os componentes que deseja incluir no conjunto de relatórios virtual, arrastando os componentes aplicáveis da coluna “componentes excluídos” para a coluna “componentes incluídos”. Os componentes que podem ser incluídos e excluídos são:

   * Dimensões
   * Métricas
   * Segmentos
   * Intervalos de datas
   >[!NOTE]
   >
   >There is no need to *share* curated components (segments, calculated metrics, date ranges). Eles sempre estarão visíveis na Analysis Workspace se tiverem curadoria para o conjunto de relatórios virtual, mesmo se não forem compartilhados.

1. Além disso, você pode filtrar ou pesquisar os componentes e adicionar toda a seleção filtrada à coluna incluída clicando em **[!UICONTROL Adicionar tudo]**.

   ![](assets/vrs-add-all.png)

## Renomear componentes {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Você pode alterar os nomes de exibição dos componentes incluídos especificamente para o conjunto de relatórios virtual. Por exemplo, se você quiser incluir o Nome da página no conjunto de relatórios virtual, mas quiser renomeá-lo para algo no contexto dos dispositivos móveis, poderá fazer isso nas Telas do aplicativo. O novo nome é exibido na Analysis Workspace sempre que este conjunto de relatórios virtual é usado.

![](assets/vrs-rename-component.png)

Na Analysis Workspace, clique no ícone de informações de qualquer componente incluído para revelar o nome original do componente renomeado:

![](assets/vrs-aw-renamed.png)

## Grupos de componentes {#section_483BEC76F49E46ADAAA03F0A12E48426}

Use grupos de componentes para criar adições de componentes em massa ao seu conjunto de relatórios virtual. Por exemplo, se você quiser importar um conjunto padrão de componentes específicos da análise de aplicativos móveis, selecione o grupo de aplicativos móveis. Um conjunto correspondente de dimensões e métricas (já renomeadas) é adicionado automaticamente à lista de Incluídos do conjunto de relatórios virtual.

![](assets/vrs-comp-grp.png)

## Comportamento do espaço de trabalho {#section_6C32F8B642804C0097FCB14E21028D4A}

Para obter mais informações sobre a preparação na Analysis Workspace, consulte [Preparar e compartilhar um projeto](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate.html).