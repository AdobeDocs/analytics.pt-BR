---
description: Saiba mais sobre o construtor de métricas calculadas que fornece uma tela para arrastar e soltar dimensões, métricas, segmentos e funções para criar métricas personalizadas com base na lógica, nas regras e nos operadores da hierarquia do contêiner.
title: Criar métricas
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 97%

---

# Criar métricas calculadas {#build-metrics}

O Adobe Analytics fornece uma tela para arrastar e soltar dimensões, métricas, segmentos e funções para criar métricas personalizadas com base na lógica de hierarquia de containers, regras e operadores. Esta ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples e complexas.

É possível usar o construtor de métricas calculadas para criar ou editar métricas calculadas. Quando criadas dessa forma, as métricas calculadas ficam disponíveis na lista de componentes e podem ser usadas em projetos por toda a organização. Como alternativa, é possível criar rapidamente uma métrica calculada que esteja disponível somente para o projeto em que foi criada, conforme descrito na seção [Criar métricas calculadas para um único projeto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) em [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

[Criar uma métrica calculada](../cm-workflow.md) descreve as diferentes opções disponíveis para criar uma nova métrica calculada.

## Áreas do construtor de métricas calculadas

A caixa de diálogo **[!UICONTROL Criador de métricas calculadas]** é usada para criar novas métricas calculadas ou editar métricas calculadas existentes. A caixa de diálogo é denominada **[!UICONTROL Nova métrica calculada]** ou **[!UICONTROL Editar métrica calculada]** para métricas calculadas criadas ou gerenciadas por meio do gerenciador de [[!UICONTROL métricas calculadas]](../cm-manager.md).

>[!BEGINTABS]

>[!TAB Construtor de métrica calculada]

![Janela de detalhes das métricas calculadas, mostrando os campos e opções descritos na próxima seção.](assets/calculated-metric-builder.png)

>[!TAB Criar ou editar métrica calculada]

![Janela de detalhes da métrica calculada, mostrando os campos e opções descritos na próxima seção.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Especifique os seguintes detalhes (![Obrigatório](/help/assets/icons/Required.svg) é obrigatório):

   | Elemento | Descrição |
   | --- | --- |
   | **[!UICONTROL Conjunto de relatórios]** | Você pode selecionar o conjunto de relatórios para a métrica calculada.  A métrica calculada que você define está disponível nos projetos do Espaço de trabalho com base no conjunto de relatórios selecionado. |
   | **[!UICONTROL Métrica somente do projeto]** | Uma caixa de informações aparece na parte superior desta caixa de diálogo ao editar uma métrica calculada que foi criada para um único projeto, conforme descrito em [Criar métricas calculadas para um único projeto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Se quiser disponibilizar essa métrica calculada para todos os projetos, selecione a opção **[!UICONTROL Disponibilizar essa métrica para todos os seus projetos e adicioná-la à sua lista de componentes]**.</p> |
   | **[!UICONTROL Título]** ![Obrigatório](/help/assets/icons/Required.svg) | Nomeie a métrica calculada, por exemplo, como `Conversion Rate`. |
   | **[!UICONTROL Descrição]** | Forneça uma descrição para o segmento, por exemplo, `Calculated metric to define the conversion rate.` Não há necessidade de descrever a fórmula para a métrica calculada, pois a fórmula já é disponibilizada automaticamente em [!UICONTROL Resumo]. |
   | **[!UICONTROL Formato]** | Selecione um formato para a métrica calculada: você pode selecionar entre **[!UICONTROL Decimal]**, **[!UICONTROL Hora]**, **[!UICONTROL Porcentagem]** e **[!UICONTROL Moeda]**. |
   | **[!UICONTROL Casas decimais]** | Especifique a quantidade de casas decimais para o formato selecionado. Habilitado somente quando o formato selecionado é “Decimal”, “Moeda” ou “Porcentagem”. |
   | **[!UICONTROL Exibir tendência ascendente como]** | Especifique se uma tendência ascendente da métrica calculada é exibida como ▲ **[!UICONTROL Boa (Verde)]** ou como ▼ **[!UICONTROL Ruim (Vermelho)]**. |
   | **[!UICONTROL Moeda]** | Especifique a moeda da métrica calculada. Habilitado somente quando o formato selecionado é “Moeda”. |
   | **[!UICONTROL Tags]** | Para organizar a métrica calculada, crie ou aplique uma ou mais tags. Comece a digitar para encontrar as tags existentes que você pode selecionar. Ou pressione **[!UICONTROL ENTER]** para adicionar uma nova tag. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover uma tag. |
   | **[!UICONTROL Pré-visualizar]** | A visualização abrange os últimos 90 dias e é uma maneira de medir se você definiu a sua métrica corretamente. |
   | **[!UICONTROL Resumo]** | Exibe um resumo da definição da métrica calculada. <br/>Por exemplo: ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total de pedidos]** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessões]**. |
   | **[!UICONTROL Definição]** ![Obrigatória](/help/assets/icons/Required.svg) | Defina o segmento usando o [Criador de definições](#definition-builder). |

1. Para verificar se a definição da sua métrica calculada está correta, use a **[!UICONTROL Visualização]** atualizada constantemente dos resultados da métrica calculada. A **[!UICONTROL Visualização]** abrange os últimos 90 dias e avalia continuamente a definição da sua métrica calculada.

   A **[!UICONTROL Compatibilidade do produto]** indica a compatibilidade da métrica calculada com as funcionalidades do Adobe Analytics. Consulte [Compatibilidade da métrica](/help/components/c-calcmetrics/cm-compatibility.md) para obter mais informações.

1. Selecione:
   * Clique em **[!UICONTROL Salvar]** para salvar a métrica calculada.
   * Clique em **[!UICONTROL Salvar como]** para salvar uma cópia da métrica calculada.
   * Clique em **[!UICONTROL Cancelar]** para cancelar as alterações feitas em uma métrica calculada ou a criação de uma nova métrica calculada.


## Construtor de definições

Use o Criador de definições para arrastar e soltar dimensões, métricas, segmentos e funções para criar métricas personalizadas com base na lógica, nas regras e nos operadores da hierarquia do container. Nesse processo de criação, você pode usar métricas padrão, métricas definidas pela Adobe, métricas calculadas, segmentos, dimensões e funções. Todos esses componentes estão disponíveis no painel de componentes do criador de métricas calculadas. Você também pode usar operadores e containers na definição.

![Criar métrica calculada](assets/create-calculated-metric.gif)

Somente métricas são definidas como componentes singulares na área **[!UICONTROL Definição]**. Todos os outros componentes são definidos como um container, uma métrica de encapsulamento ou outros containers. Consulte [Containers](#containers) para mais informações.

### Métricas

Para adicionar uma métrica:

* Arraste e solte um componente ![Eventos](/help/assets/icons/Event.svg) **[!UICONTROL Métricas]** do painel de componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, segmentos e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.

Se você usar uma métrica calculada como parte da sua definição, a métrica calculada será expandida.

Para modificar uma métrica:

1. Selecione a ![Configuração](/help/assets/icons/Setting.svg) em um componente de métrica, na área **[!UICONTROL Definição]**.
1. Na caixa de diálogo pop-up, é possível definir o tipo de métrica e um modelo de atribuição. Confira [Tipo de métrica e atribuição](m-metric-type-alloc.md).

Para excluir uma métrica:

* Selecione ![Fechar](/help/assets/icons/Close.svg) na métrica.

### Operadores

Os operadores permitem especificar o operador entre componentes ou containers. Os operadores aparecem automaticamente entre

* duas ou mais métricas em um container,
* dois ou mais containers em um container,
* uma ou mais métricas e um ou mais containers em um container.

Você pode selecionar:

| Símbolo | Operador |
|:---:|---|
| ![Dividir](/help/assets/icons/Divide.svg) | Dividir (padrão) |
| ![Fechar](/help/assets/icons/Close.svg) | Multiplicar |
| ![Remover](/help/assets/icons/Remove.svg) | Subtrair |
| ![Adicionar](/help/assets/icons/Add.svg) | Adicionar |

### Número estático

É possível adicionar um número estático à definição da métrica calculada. Para adicionar um número estático:

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** de dentro de um container.
* Selecione **[!UICONTROL Número estático]**. Um container de número estático é exibido.
* Selecione [!UICONTROL *Clique para adicionar um valor*] e digite um valor.


### Containers

Adicione dimensões, segmentos e funções como containers a uma definição de métrica calculada. Você também pode adicionar um container genérico. Os contêineres funcionam como uma expressão matemática e determinam a ordem das operações. Qualquer coisa que estiver um container será processada antes do próximo componente ou container.


#### Container de segmento

Use o conceito de um container de segmento para criar uma [métrica segmentada](metrics-with-segments.md). É possível criar um container de segmento usando um segmento tradicional ou um segmento criado a partir de uma dimensão.

* Para adicionar um container de segmento a partir de uma dimensão:

   1. Arraste e solte um componente ![Dimensões](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensões]** do painel de componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, segmentos e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar componentes específicos.
   1. No pop-up **[!UICONTROL Criar segmento a partir da dimensão]**, defina a condição para o segmento. Selecione um valor na lista de operadores ou insira um valor. Por exemplo, **[!UICONTROL Mês]** **[!UICONTROL é igual a]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Selecione **[!UICONTROL Concluído]**. Um container de segmento é adicionado à **[!UICONTROL Definição]**.


* Para adicionar um container de segmento a partir de um segmento, é possível usar:

   * Arraste e solte um componente ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]** do painel de componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, segmentos e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para pesquisar segmentos específicos.
Isso adiciona automaticamente um container de segmento à **[!UICONTROL Definição]** usando o nome do segmento.

   * Arraste e solte um componente de ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmento]** do painel de componentes em um container genérico. O container será transformado em um container de segmento.

   * Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** de dentro de um container:

      1. Selecione **[!UICONTROL Segmento]**.  Um container de segmento é adicionado à **[!UICONTROL Definição]**.
      1. No novo container de segmento, selecione um segmento no menu suspenso [!UICONTROL *Selecionar...*].

  >[!TIP]
  >
  >É possível adicionar mais de um segmento a um container.

  Os segmentos no container são nomeados com base no componente de segmento. Por exemplo, ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Sessões da web]**. Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para exibir uma janela pop-up com detalhes sobre o segmento. Na janela pop-up, selecione ![Editar](/help/assets/icons/Edit.svg) para editar a definição do segmento.

Para remover um segmento de um container:

* Selecione ![Fechar](/help/assets/icons/Close.svg) ao lado do nome do segmento.

Consulte [Métricas segmentadas](metrics-with-segments.md) para obter mais detalhes e exemplos.

#### Container de função

Para adicionar um container de função, é possível usar:

* Arrastar e soltar:

   1. Arraste e solte um componente ![Função](/help/assets/icons/Effect.svg) **[!UICONTROL Funções]** do painel de componentes para **[!UICONTROL Arraste e solte métricas, dimensões, itens de dimensão, segmentos e/ou funções aqui]**. Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) na barra de componentes para procurar funções específicas.
   1. Automaticamente, um container de função é adicionado à **[!UICONTROL Definição]** usando o nome da função.

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** em um container:

   1. Selecione **[!UICONTROL Função]**.
   1. No container, selecione uma função no menu suspenso [!UICONTROL *Selecionar...*].

O container de função recebe o nome do componente de função. Por exemplo, ![Função](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (metric)]**. Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para exibir uma janela pop-up com detalhes sobre a função. Escolha **[!UICONTROL Saiba mais]** para obter mais informações sobre a função.

Consulte [Usar funções](cm-using-functions.md) para obter detalhes sobre como usar funções e quais funções estão disponíveis para criar uma métrica calculada.


#### Container genérico

Para adicionar um container genérico:

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** em um container
* Escolha **[!UICONTROL Container]**. Um novo container genérico vazio é adicionado à **[!UICONTROL Definição]**. É possível usar um container genérico para aninhar ou criar uma hierarquia na definição da métrica calculada.


#### Excluir um container

Para excluir um container, selecione ![Fechar](/help/assets/icons/Close.svg) no nível do container.

>[!MORELIKETHIS]
>
>[Usar funções](cm-using-functions.md)
>&#x200B;>[Segmentos ](/help/components/segmentation/seg-overview.md)
>


<!--

Adobe Analytics provides a canvas to drag and drop dimensions, metrics, segments, and functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple or complex calculated metrics.

## Begin building a calculated metric

You can use the calculated metric builder to create or edit calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. Alternatively, you can quickly create a calculated metric that is available only for the project where it was created, as described in [Create calculated metrics for a single project](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Access the calculated metric builder to begin creating a calculated metric that is available in the component list. 

1. Access the calculated metric builder in any of the follows ways:

   * In Analysis Workspace, open a project, then select **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
   * In Analysis Workspace, open a project, then select the **Plus** icon next to the [!UICONTROL **Metrics**] section in the left rail.
   * In [!DNL Adobe Analytics], go to **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, then select **[!UICONTROL + Add]** at the top of the Calculated metrics page.

1. Continue with [Areas of the calculated metric builder](#areas-of-the-calculated-metrics-builder).

## Areas of the Calculated metrics builder

The following image and accompanying table explain some of the main areas and features of the Calculated metrics builder.

![](assets/cm_builder_ui.png)

| Location in image  | Name and function  |
|---|---|
| 1 | **Title:** Naming the metric is mandatory. You cannot save the metric unless it is named.  |
| 2 | **Description:** Give it a user-friendly description to show what it's used for and to distinguish it from similar ones. <p>The description also appears within a report. It's best NOT to put the formula into the description - instead, describe what this metric should and should not be used for. (The formula is generated as you build the metric, underneath the Summary heading. As a result, there is no need to add the formula to the description.) </p>  |
| 3 | **Format:** Choices include Decimal, Time, Percent, and Currency.  |
| 4 | **Decimal Places:** Shows how many decimal places will be shown in the report. The maximum number of decimal places you can specify is 10.  |
| 5| **Show Upward Trend As:** This metric polarity setting shows whether Analytics should consider an upward trend in the metric as good (green) or bad (red). As a result, the report's graph will show as green or red when it's going up.  |
| 6 | **Tags:** Tagging is a good way to organize metrics. All users can create tags and apply one or more tags to a metric. However, you can see tags only for those segments that you own or that have been shared with you. What kinds of tags should you create? Here are some suggestions for useful tags:<ul><li>**Team names**, such as Social Marketing, Mobile Marketing.</li><li>**Projects** (analysis tags), such as Entry-page analysis.</li><li>**Categories**, such as Women's; Geography.</li><li>**Workflows**, such as To be approved; Curated for (a specific business unit)</li></ul> |
| 7 | **Summary:** <p>The Summary formula updates anytime you make a change to the metric definition. This formula also shows up in the metrics rail on the left when you hover over a metric and click the <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icon. </p>  |
| 8 | **Definition:** This is where you drag in metrics/calculated metrics, segments, and/or functions to build the calculated metric. <ul><li>If you drag in a calculated metric, it will expand its metric definition automatically. </li> <li>You can nest definitions with containers. However, unlike segment containers, these containers function like a math expression and determine the order of operations. </li> </ul>  |
| 9 | **Operator:** Divided by ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) is the default operator, plus there are the +, -, and x operators. |
| 10 | **Preview:** Provides a quick read on any possible errors. The preview covers the last 90 days. This is a way of initially gauging whether you have selected the right components for your metric. An unexpected result would mean you need to take a second look at the metric definition.  |
| 11 | **Product compatibility:** Product compatibility shows you whether the metric is compatible with <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Current Data </a>, with Fully Processed Data, or only with Marketing Channel reports (first-touch allocation). <p>Note:  Current Data does not support all metrics. Metrics that contain segments or functions are not compatible with current data. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > More... </a> </p> </p>  |
| 12 | **Add:** For all types of calculated metrics, you can add containers and static numbers to the definition. For advanced calculated metrics, you can also add segments and functions. <ul><li>Containers function like a math expression and determine the order of operations. So anything in a container will get processed before the next operation.</li><li>Dragging a segment onto a container segments everything in that container. (Advanced calculated metrics only)</li><li>You can stack multiple segments in a container.</li></ul> |
| 13 | **Gear icon (Metric Type, Attribution):** Selecting the gear icon next to a metric lets you specify the <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > metric type and attribution models </a>. |
| 14 | **New:** Lets you create a new component, such as a new segment (which takes you to the <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Segment Builder </a>.) |
| 15 | **Search Components:** This search bar lets you search for dimensions, metrics, segments (advanced calculated metrics only), and functions (advanced calculated metrics only). |
| 16 | **List of Dimensions:** Rather than leaving the Calculated Metric Builder in order to build a simple segment (in the Segment Builder), e.g. "Page = Homepage", you can drag in Page and select Homepage directly from the Calculated Metric Builder.<p>This results in a much more streamlined workflow for creating segmented calculated metrics.</p> |
| 17 | **List of Metrics:** Metrics come in 3 categories: <ul> <li>Standard metrics (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Calculated metrics ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Metrics templates ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - at the bottom of the list. </li> </ul> <p>When you hover over a metric, you can see the Info icon to the right of it: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Clicking this icon gives you the following information: </p><ul> <li>The formula of how it is calculated. </li><li>A preview trend of the metric. </li><li>An edit (pencil) icon <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> at the top right that will take you to the Calculated Metrics Builder where you can edit this calculated metric. </li></ul> |
| 18 | **List of Segments:** (Advanced calculated metrics only) As an Admin, this list shows all segments created in your login company. If you are a non-Admin user, this list shows segments you own and those shared with you. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > More... </a> |
| 19 | **List of Functions:** (Advanced calculated metrics only) Functions are divided into two lists: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Basic </a> (used most often) and <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Advanced </a>. |
| 20 | **Report Suite selector:** Lets you switch to a different report suite. |

{style="table-layout:auto"}

-->
