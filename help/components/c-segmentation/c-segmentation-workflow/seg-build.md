---
description: O Construtor de segmentos fornece uma tela para arrastar e soltar Dimensões de métricas, Segmentos e Eventos para os visitantes do segmento com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.
title: Construir segmentos
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Construtor de segmentos

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.

>[!IMPORTANT]
>
>Introduzimos modelos de atribuição de dimensão na versão de junho de 2019. Consulte nº 6 em Recursos da interface do usuário da Web abaixo.

Há várias maneiras de acessar o Construtor de segmentos:

* **Navegação** superior do Analytics: Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Segments]**.
* **[!UICONTROL Analysis Workspace]**: Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, abra um projeto e clique em **[!UICONTROL + New]** > **[!UICONTROL Create Segment]**.
* **[!UICONTROL Reports & Analytics]**: Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, abra um relatório existente e clique no ícone Segmentos ![](assets/segment_icon.png) no painel de navegação esquerdo e clique em **[!UICONTROL Add]**.
* **[!UICONTROL Ad Hoc Analysis]**: [Construir segmentos na Análise ad hoc](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments).
* **[!UICONTROL Report Builder]**: [Adicionar ou editar segmentos no Construtor de relatórios](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/data-requests/segmentation.html).

## Interface do usuário do Construtor de segmentos {#concept_643F2DF74C544796B58F4656ABC5F726}

The [!UICONTROL Segment Builder] lets you build simple or complex segments that identify visitor attributes and actions across visits and page hits. Fornece uma tela para arrastar e soltar dimensões de métrica, eventos, ou outros segmentos na ordem para visitantes de segmento com base em lógica, regras e operadores de hierarquia.

## Recursos de interface do usuário da Web  {#section_F61C4268A5974C788629399ADE1E6E7C}

The [!UICONTROL Segment Builder] lets you build and edit segments in the web UI (or in a [Java UI in Ad Hoc Analysis](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)). Você pode adicionar definições de regra e contêineres para refinar seus segmentos, empilhá-los e aninhá-los para refinar. Também é possível validar quantas visualizações de página, visitas e visitantes únicos resultam da definição de segmento atual. Também é possível salvar o segmento para necessidades futuras.

Acesse o Construtor de segmentos por:

* Exiba um relatório existente e clicar no ícone Segmentos ![](assets/segment_icon.png) na navegação à esquerda. In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* Ao clicar em um título de segmento existente no Gerenciador de segmentos para editar o segmento no Construtor de segmentos.

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title]**: Permite nomear ou renomear o segmento.
1. **[!UICONTROL Description]**: Forneça uma descrição para o segmento. Você deve fornecer uma descrição se deseja compartilhar o segmento.
1. **[!UICONTROL Tags]**: [marcar o segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) que você está criando ao selecionar de uma lista de tags existentes ou criar uma nova tag.
1. **[!UICONTROL Definitions]**: É aqui que você [constrói e configura segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md), adiciona regras e aninha e sequencia container. Permite que você forneça uma descrição para o novo segmento ao selecionar o contêiner, e arrastar e soltar dimensões, segmentos ou métricas na definição.
1. : (Seletor **[!UICONTROL Show]** Contêiner superior.) Lets you select the top-level [container](/help/components/c-segmentation/seg-overview.md) ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). O contêiner de nível superior padrão no contêiner Ocorrência.
1. **[!UICONTROL Options]**: Ícone (engrenagem)

   * **[!UICONTROL + Add container]**: Permite adicionar um novo container (abaixo do container de nível superior) à definição do segmento.
   * **[!UICONTROL + Add container from selection]**: Permite criar um novo container a partir dos elementos que você (multi-) selecionou no campo Definições.
   * **[!UICONTROL Exclude]**: Permite que você defina o segmento excluindo uma ou mais dimensões, segmentos ou métricas.

1. **[!UICONTROL Attribution Models]**: Para segmentação de dimensão. Os modelos de dimensão são especialmente úteis na segmentação sequencial, como nos que oferecem suporte para visualizações de Fluxo:

   * **[!UICONTROL Repeating]** (padrão): Inclui instâncias e valores persistentes para a dimensão.
   * **[!UICONTROL Instance]**: Inclui instâncias da dimensão.
   * **[!UICONTROL Non-repeating instance]**: Inclui instâncias exclusivas (de não repetição) da dimensão.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions]**: As dimensões são arrastadas e soltas da lista Dimensões (barra lateral laranja).
1. **[!UICONTROL Comparison]**: É possível comparar e restringir valores com operadores selecionados.
1. **[!UICONTROL Value]**: O valor inserido ou selecionado para a dimensão ou semento ou métrica.
1. **[!UICONTROL And/Or/Then]**: Atribui os operadores [!UICONTROL AND/OR/THEN] entre container ou regras. O operador ENTÃO permite que você [defina segmentos sequenciais](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Metric]**: (Barra lateral verde) Métrica que foi arrastada e solta da lista Métricas.
1. **[!UICONTROL Comparison]** operador: Você pode comparar e restringir valores usando operadores selecionados.
1. **[!UICONTROL Value]**: O valor inserido ou selecionado para a dimensão ou semento ou métrica.
1. **[!UICONTROL X]**: (excluir) permite que você exclua essa parte da definição de segmentos.
1. **[!UICONTROL Save]** ou **[!UICONTROL Cancel]**: Salva ou cancela o segmento. After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search]**: Pesquisa a lista de dimensões, segmentos ou métricas.
1. **[!UICONTROL Dimensions]**: (Lista) Clique no cabeçalho para expandir.
1. **[!UICONTROL Metrics]**: Clique no cabeçalho para expandir.
1. **[!UICONTROL Segments]**: Clique no cabeçalho para expandir.
1. **[!UICONTROL Report suite selector]**: Permite selecionar os conjuntos de relatórios sob os quais esse segmento será salvo. Você ainda pode utilizar o segmento em todos os conjuntos de relatórios.
1. **[!UICONTROL Segment Preview]**: Permite que você visualize as métricas principais para conferir se você tem um segmento válido e a amplitude deste. Represente o detalhamento do conjunto de dados que você pode esperar ao aplicar esse segmento. Shows 3 concentric circles and a list to show the number and percentage of matches for [!UICONTROL Hits], [!UICONTROL Visits], and [!UICONTROL Visitors] for a segment run against a data set. Esse gráfico é atualizado imediatamente depois de criar ou efetuar alterações para sua definição de segmento.
1. **[!UICONTROL Product Compatibility]**: Fornece uma lista de quais produtos do Adobe Analytics (área de trabalho de Análise, [!UICONTROL Reports & Analytics], Análise ad hoc, Data Warehouse) são compatíveis com o segmento criado. A maioria dos segmentos são compatíveis com todos os produtos. Contudo, nem todos os operadores e dimensões são compatíveis com todos os produtos Analytics, especialmente o  [Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md). Esse gráfico é atualizado imediatamente depois de efetuar alterações na definição do segmento.

Segmentos com intervalos de datas incorporados continuarão a operar de forma diferente na Analysis Workspace com relação ao [!UICONTROL Reports & Analytics]: na Workspace, um segmento com um intervalo de datas inserido substitui o intervalo de datas do painel. Ao contrário, o [!UICONTROL Reports & Analytics] gera a interseção entre intervalo de datas do relatório e o intervalo de datas inserido do segmento.

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**: (Não exibido na tela) Essa opção aparece somente se o conjunto de relatórios no qual você está salvando esse segmento estiver [ativado para a Experience Cloud](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md). By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. É necessário um título de segmento e uma descrição.

>[!NOTE]No Analytics, você pode editar ou excluir um segmento publicado. Se o segmento estiver em uso, uma mensagem de aviso será emitida quando um segmento for editado. Não é possível excluir um segmento publicado que esteja sendo usado pelo Adobe [!DNL Target].

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>É preciso limitar para 20 o número de públicos-alvo compartilhados por meio do Analytics para evitar atrasos adicionais de processamento. Públicos-alvo compartilhados com a Experience Cloud a partir do Analytics não podem exceder 20 milhões de membros únicos. Além disso, devido a questões relacionadas ao cache, conjuntos de relatórios excluídos no Analytics permanecem exibidos na Experience Cloud por 12 horas após a exclusão.

>[!IMPORTANT]
>
>Depois que um visitante é qualificado para o público-alvo compartilhado do Analytics, existe um atraso de 24 a 48 horas antes de as informações serem ativadas no [!DNL Target], no [!DNL Advertising Cloud] e no [!DNL Campaign].

## Construir segmentos {#build-segments}

1. Simply drag a Dimension, Segment, or Metric Event from the left pane to the [!UICONTROL Definitions] field.

   ![](assets/drag_n_drop_dimension.png)

   The default top-level [!UICONTROL Hit] container is shown after dragging an element to [!UICONTROL Definitions]. You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. Defina o [operador](/help/components/c-segmentation/seg-reference/seg-operators.md) no menu suspenso.
1. Digite ou selecione um valor para o item selecionado.
1. Adicione container adicionais, se necessário, usando **[!UICONTROL And]**, **[!UICONTROL Or]** ou **[!UICONTROL Then]** regras.
1. Depois de colocar os contêineres e definir as regras, consulte os resultados do segmento no gráfico de validação na parte superior à direita. O validador indica o percentual e o número absoluto de visualizações de página, visitas e visitantes únicos que corresponde ao segmento criado.
1. Under **[!UICONTROL Tags]**, [tag](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

Agora você é levado ao [Gerenciador de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md), onde é possível marcar, compartilhar e gerenciar o segmento de várias maneiras.

## Construir e aninhar contêineres {#section_1C38F15703B44474B0718CEF06639EFD}

É possível [construir uma estrutura de contêineres](/help/components/c-segmentation/seg-overview.md) e, em seguida, colocar regras de lógica e operadores entre eles.

1. Clique em **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   A new [!UICONTROL Hit] container opens without a [!UICONTROL Hit] (Page View) identified.

   ![](assets/new_container.png)

1. Altere o tipo de contêiner como necessário.
1. Arraste uma Dimensão, um Segmento ou Evento do painel esquerdo até o contêiner.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OU**

   Select one or more rules and then click **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. Isso transforma sua seleção em um contêiner separado.

## Usar intervalos de datas em segmentos {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

É possível criar segmentos que contêm intervalos de datas flexíveis para responder questões sobre campanhas ou eventos em andamento.

Por exemplo, crie com facilidade um segmento que inclua &quot;todos que realizaram uma compra nos últimos 60 dias&quot;.

Crie um container de Visita e, dentro dele, adicione o intervalo de [!UICONTROL Last 60 days] tempo e a métrica [!UICONTROL Orders is greater than or equal to 1], com um operador E:

![](assets/date-ranges.png)

## Empilhar segmentos {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

O empilhamento de segmentos funciona ao combinar os critérios em cada segmento com um operador &quot;e&quot;, em seguida, ao aplicar os critérios combinados.

Por exemplo, empilhar um segmento de &quot;usuários de telefones celulares&quot; e um segmento &quot;Geografia dos EUA&quot; retorna dados somente para usuários de telefones celulares nos EUA.

Pense nesses segmentos como blocos de construção ou módulos que você pode incluir em uma biblioteca de segmentos para que os usuários usem como necessário. Dessa forma, você pode reduzir dramaticamente o número de segmentos necessários. Por exemplo, considera que você tem 40 segmentos:

* 20 para usuários de telefones celulares em países diferentes (US_mobile, Germany_mobile, France_mobile, Brazil_mobile etc.)
* 20 para usuários de tablet em países diferentes (US_tablet, Germany_tablet, France_tablet, Brazil_tablet etc.)

Ao usar o empilhamento de segmentos, você pode reduzir a contagem de segmentos em 22 e empilhá-los como necessário. É necessário criar esses segmentos:

* um segmento para usuários móveis
* um segmento para usuários de tablets
* 20 segmentos para localidades geográficas diferentes

>[!NOTE] Ao empilhar dois segmentos, eles são unidos por padrão por uma instrução E. Isso não pode ser alterado para uma instrução OU.

1. Vá para o Construtor de segmentos.
1. Forneça um título e uma descrição para o segmento.

   Resultado da etapa 1. Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   Resultado da etapa 1. Arraste e solte os segmentos que você deseja empilhar na área de definição de segmentos. Este é um exemplo de segmento que empilha os segmentos existentes &quot;Visitas de tablets&quot; e &quot;Geográfico EUA&quot;:

   ![](assets/seg_stack2.png)

1. Salve o segmento.

   Resultado da etapa

## Usar modelos de segmentos {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Os modelos representam os segmentos antigos pré-configurados e do pacote.

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. Em seguida, clique no ícone Segmentos ![](assets/segment_icon.png)

para exibir o painel de segmentos. Os modelos do segmento aparecem na parte inferior da lista de segmentos. É possível distingui-los por um ícone de pasta à esquerda do nome do modelo:

![](assets/seg_template.png)

Você pode arrastar esses modelos para uma área de Definições e usá-los como foram definidos, ou modificá-los.

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome do modelo </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Abandonar carrinho </td> 
   <td colname="col2">Visualizar dados para visitantes que adicionaram itens aos carrinhos, mas não fizeram nenhum pedido. Em Definição de segmento, o contêiner é Visita. A regra para esse segmento sequencial é <p> Adições de carrinho não é nulo </p> <p>Então </p> <p>Pedidos equivale a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Novas visitas </td> 
   <td colname="col2">Exibição de dados para visitantes que visitaram [1] uma vez no máximo. Em Definição de segmento, o contêiner é Visita. A regra é <p>Número de visitas é igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Não compradores </td> 
   <td colname="col2">Exibição de dados a visitantes que não participaram de um evento de compra. Na Definição do segmento, o contêiner é Visitante. Esse segmento usa a lógica Excluir. A regra é <p>Pedidos não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visita de página não única (sem retornos) </td> 
   <td colname="col2">Exibir dados para visitantes que visitaram mais de uma vez. Na Definição do segmento, o contêiner é Visitante. Esse segmento usa a lógica Excluir. A regra é <p>Acesso único não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pesquisa paga </td> 
   <td colname="col2">Exibir dados de visitantes de uma pesquisa paga. Em Definição de segmento, o contêiner é Visita. A regra é <p>Pesquisa paga igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compradores </td> 
   <td colname="col2">Exibição de dados a visitantes que participaram de um evento de compra. Na Definição do segmento, o contêiner é Visitante. A regra é <p>Pedidos não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de Retorno </td> 
   <td colname="col2">Exibir dados de visitantes que visitaram pelo menos uma vez. Em Definição de segmento, o contêiner é Visita. A regra é <p>Número de visitas superior a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas únicas à página </td> 
   <td colname="col2"> Exibir dados de visitas onde você visualiza um valor de página única, embora você possa enviar várias visualizações de página durante essa visita. Visitas de página única com eventos de link de saída são incluídas no segmento. Em Definição de segmento, o contêiner é Visita. A regra é <p>Visitas Únicas à Página é igual a 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Produto visualizado não adicionado ao carrinho </td> 
   <td colname="col2">Exibir dados para visitantes que visualizaram produtos, mas não adicionaram nada ao carrinho. Em Definição de segmento, o contêiner é Visita. A regra para esse segmento sequencial é <p>Visualizações de produto não é nulo </p> <p>Então </p> <p> Adições de carrinho é igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas da campanha </td> 
   <td colname="col2">Exibir de dados de visitantes enviados por redes sociais. Em Definição de segmento, o contêiner é Visita. A regra é <p>Código de rastreamento não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de dispositivos móveis </td> 
   <td colname="col2">Exibir dados de visitantes com dispositivos móveis. Em Definição de segmento, o contêiner é Visita. A regra é <p>Dispositivo móvel não é nulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas da pesquisa natural </td> 
   <td colname="col2">Exibir dados de visitantes não originários de uma pesquisa paga. Em Definição de segmento, o contêiner é Visita. A regra é <p>Pesquisa paga igual a 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de dispositivos não móveis </td> 
   <td colname="col2">Exibir dados de visitantes que não usam dispositivos móveis. Em Definição de segmento, o contêiner é Visita. Esse segmento usa a lógica Excluir. A regra é <p>O tipo do dispositivo móvel equivale a telefone celular </p> <p>Ou </p> <p>O tipo do dispositivo móvel equivale a tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de telefones </td> 
   <td colname="col2">Exibir dados de visitantes com telefones. Em Definição de segmento, o contêiner é Visita. A regra é <p>Tipo de dispositivo igual a Telefone móvel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de mecanismos de pesquisa </td> 
   <td colname="col2">Exibir dados de visitantes enviados por mecanismos de pesquisa. Em Definição de segmento, o contêiner é Visita. A regra é <p>Tipo de referenciador igual a Mecanismos de pesquisa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de sites sociais </td> 
   <td colname="col2">Exibição de dados do visitante enviados por redes sociais. Em Definição de segmento, o contêiner é Visita. A regra é <p>Tipo de referenciador igual às redes sociais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de tablets </td> 
   <td colname="col2">Exibir dados de visitantes com tablets. Em Definição de segmento, o contêiner é Visita. A regra é <p>Tipo de dispositivo equivale a Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes com cookie de ID do visitante </td> 
   <td colname="col2">Exibir dados de visitantes do site, onde é necessário um cookie persistente. Em Definição de segmento, o contêiner é Visita. A regra é <p>Cookies persistentes igual a 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplo: Segmento de visitantes da campanha {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

Mostra um exemplo deste segmento frequentemente usado.

Vários clientes desejam visualizar as métricas dos visitantes que responderam a campanhas específicas. A criação de um segmento de visitantes da campanha é uma forma fácil de obter esses dados.

A construção desse segmento no Construtor de segmentos significa que de um contêiner de Visita de nível superior você arrasta uma dimensão de campanha, neste caso Nome da campanha:

![](assets/seg_campaign_visitor.png)

(Opcional) Você também pode aplicar uma tag de Campanhas a esse segmento, se você deseja filtrar facilmente todos os segmentos relacionados à campanha.
