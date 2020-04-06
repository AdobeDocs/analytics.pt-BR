---
description: Os conjuntos de relatórios virtuais podem ser preparados para incluir e excluir componentes.na área de trabalho de Análise.
title: Curadoria do componente de conjunto de relatórios virtual
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Curadoria do componente de conjunto de relatórios virtual

Os conjuntos de relatórios virtuais podem ser preparados para incluir e excluir componentes.na área de trabalho de Análise.

>[!NOTE] As alterações foram feitas aos componentes que são visíveis por administradores e não administradores em projetos preparados da Workspace e em conjuntos de relatórios virtuais preparados (VRSs). Anteriormente, qualquer pessoa podia ver componentes sem curadoria clicando em **[!UICONTROL Show all Components]**. The [updated curation experience](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/curate-projects-vrs.html) allows for more fine-grained control over which components are visible.

Para permitir a curadoria de componentes,

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. Depois de definir o **[!UICONTROL Settings]**, clique na **[!UICONTROL Components]** guia.

1. Marque a caixa de seleção **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Se a personalização de componentes estiver ativada, o conjunto de relatórios virtuais poderá ser acessado **somente na Analysis Workspace** e não em:

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * API em relatórios do Analytics
   Depois de marcado, você pode adicionar os componentes que gostaria de incluir no conjunto de relatórios virtual arrastando os componentes aplicáveis da coluna &quot;componentes excluídos&quot; para a coluna &quot;componentes incluídos&quot;. Os componentes que podem ser incluídos e excluídos são:

   * Dimensões
   * Métricas
   * Segmentos
   * Intervalos de datas
   >[!NOTE]
   >
   >Não há necessidade de *compartilhar* componentes com curadoria (segmentos, métricas calculadas, intervalos de datas). Eles sempre estarão visíveis na Analysis Workspace se tiverem curadoria para o conjunto de relatórios virtual, mesmo se não forem compartilhados.

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Renomear componentes {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Você pode alterar os nomes de exibição dos componentes incluídos específicos do conjunto de relatórios virtual. Por exemplo, se você quiser incluir o Nome da página no conjunto de relatórios virtual, mas quiser renomeá-lo para um contexto mais amigável para dispositivos móveis, você pode alterá-lo para Telas do aplicativo. O novo nome é exibido na área de trabalho da Análise sempre que este conjunto de relatórios virtual é usado.

![](assets/vrs-rename-component.png)

Na área de trabalho da Análise, clique no ícone de informações de qualquer componente incluído para revelar o nome original do componente renomeado:

![](assets/vrs-aw-renamed.png)

## Grupos de componentes  {#section_483BEC76F49E46ADAAA03F0A12E48426}

Use grupos de componentes para fazer adições de componentes em massa ao seu conjunto de relatórios virtual. Por exemplo, se você quiser importar um conjunto padrão de componentes específicos para a análise de aplicativos móveis, selecione o grupo de aplicativos móveis. Um conjunto correspondente de dimensões e métricas (já renomeadas) é adicionado automaticamente à lista Incluída do conjunto de relatórios virtual.

![](assets/vrs-comp-grp.png)

## Comportamento do Workspace {#section_6C32F8B642804C0097FCB14E21028D4A}

Para obter mais informações sobre a preparação na Analysis Workspace, consulte [Preparar e compartilhar um projeto](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/curate.html).
