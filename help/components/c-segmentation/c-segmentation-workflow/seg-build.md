---
description: O Construtor de segmentos fornece uma tela para arrastar e soltar Dimensões de métricas, Segmentos e Eventos para os visitantes do segmento com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.
seo-description: O Construtor de segmentos fornece uma tela para arrastar e soltar Dimensões de métricas, Segmentos e Eventos para os visitantes do segmento com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.
seo-title: Construir segmentos
solution: Analytics
title: Construir segmentos
topic: Segmentos
uuid: c 01393 df-ccdd -431 c -83 a 6-3 c 2700 bd 4999
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Construtor de segmentos

O Construtor de segmentos fornece uma tela para arrastar e soltar Dimensões de métricas, Segmentos e Eventos para os visitantes do segmento com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.

O [!UICONTROL Construtor de segmentos] fornece uma tela para arrastar e soltar Dimensões de métrica, Segmentos e Eventos para os visitantes do segmento com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.

>[!IMPORTANT]
>
>Introduzimos modelos de atribuição de dimensão na versão de junho de 2019. Consulte # 6 em Recursos da interface de usuário da Web abaixo.

Há várias maneiras de acessar o Construtor de segmentos:

* **Navegação superior do Analytics:** Clique **[!UICONTROL em Análises]** &gt; **[!UICONTROL Componentes]** &gt; **[!UICONTROL Segmentos]**.
* **[!UICONTROL Analysis Workspace]:** Clique **[!UICONTROL em Analytics]** &gt; **[!UICONTROL Espaço de trabalho]**, abra um projeto e clique **[!UICONTROL em + Novo]** &gt; **[!UICONTROL Criar segmento]**.
* **[!UICONTROL Relatórios e análises]:** Clique **[!UICONTROL em Analytics]** &gt; **[!UICONTROL Relatórios]**, abra um relatório existente e clique no ícone Segmentos ![](assets/segment_icon.png) na navegação à esquerda e clique **[!UICONTROL em Adicionar]**.
* **[!UICONTROL Análise ad hoc]:** [Criar segmentos na análise ad hoc](../../../components/c-segmentation/c-segmentation-workflow/seg-build.md#section_E440630183D64999BA2369D1B8048AA6).
* **[!UICONTROL Construtor de relatórios]:** [Adicionar ou editar segmentos no Construtor de relatórios](https://marketing.adobe.com/resources/help/en_US/arb/segmentation.html).

## Segment Builder user interface {#concept_643F2DF74C544796B58F4656ABC5F726}

O [!UICONTROL Construtor de segmentos] permite que você construa segmentos simples ou complexos que identificam atributos e ações do visitante e ocorrências da página. Fornece uma tela para arrastar e soltar dimensões de métrica, eventos, ou outros segmentos na ordem para visitantes de segmento com base em lógica, regras e operadores de hierarquia.

## Recursos de interface do usuário da Web {#section_F61C4268A5974C788629399ADE1E6E7C}

O [!UICONTROL Construtor de segmentos] permite que você construa e edite segmentos na Interface do usuário da Web (ou em uma [Interface do usuário Java na Análise ad hoc](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#section_E440630183D64999BA2369D1B8048AA6)). Você pode adicionar definições de regra e contêineres para refinar seus segmentos, empilhá-los e aninhá-los para refinar. Também é possível validar quantas visualizações de página, visitas e visitantes únicos resultam da definição de segmento atual. Também é possível salvar o segmento para necessidades futuras.

Acesse o Construtor de segmentos por

* Exiba um relatório existente e clicar no ícone Segmentos ![](assets/segment_icon.png) na navegação à esquerda. No painel de segmentos exibido, clique em **[!UICONTROL Adicionar]**.

* No Gerenciador de segmentos, ao clicar em **[!UICONTROL + Adicionar]**.
* Ao clicar em um título de segmento existente no Gerenciador de segmentos para editar o segmento no Construtor de segmentos.

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Título:]** Permite nomear ou renomear o segmento.
1. **[!UICONTROL Descrição:]** Forneça uma descrição para o segmento. Você deve fornecer uma descrição se deseja compartilhar o segmento.
1. **[!UICONTROL Tags:]** [Marque o segmento](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_CD892CEB326C4986A1B67487052DBA50) que você está criando escolhendo de uma lista de tags existentes ou criando uma nova tag.
1. **[!UICONTROL Definições:]** Este é o local onde você [constrói e configura segmentos](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_BD4C17B01C5B4E378D0C14C852D055D4), adiciona regras e aninha e sequencia contêineres. Permite que você forneça uma descrição para o novo segmento ao selecionar o contêiner, e arrastar e soltar dimensões, segmentos ou métricas na definição.
1. **[!UICONTROL Mostrar:]** (Seletor de contêiner superior.) Lets you select the top-level [container](../../../components/c-segmentation/seg-overview.md#concept_A38E7000056547399E346559D85E2551) ( [!UICONTROL Visitor], [!UICONTROL Visit], [!UICONTROL Hit]). O contêiner de nível superior padrão no contêiner Ocorrência.
1. **[!UICONTROL Opções:]** ícone (engrenagem)

   * **[!UICONTROL + Adicionar contêiner:]** Permite adicionar um novo contêiner (abaixo do contêiner de nível superior) à definição do segmento.
   * **[!UICONTROL + Adicionar contêiner da seleção:]** Permite criar um novo contêiner a partir dos elementos selecionados (multi-) selecionados no campo Definições.
   * **[!UICONTROL Excluir:]** Permite definir o segmento ao excluir uma ou mais dimensões, segmentos ou métricas.
   **[!UICONTROL Modelos de atribuição:]** Para segmentação de dimensões. Os modelos de dimensão são particularmente úteis na segmentação sequencial, como naqueles que suportam visualizações de Fluxo:
   * **[!UICONTROL Repetir]** (padrão)): Inclui instâncias e valores persistentes para a dimensão.
   * **[!UICONTROL Instância]**: Inclui instâncias para a dimensão.
   * **[!UICONTROL Instância não repetitiva]**: Inclui instâncias exclusivas (não repetitivas) para a dimensão.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensões:]** A dimensão é arrastada e solta da lista Dimensões (barra lateral laranja).
1. **[!UICONTROL Comparação:]** Você pode comparar e restringir valores usando operadores selecionados.
1. **[!UICONTROL Valor:]** O valor inserido ou selecionado para a dimensão ou o segmento ou métrica.
1. **[!UICONTROL E/Ou/Então]**: Atribui os operadores [!UICONTROL AND/OR/THEN] entre contêineres ou regras. The THEN operator lets you [define sequential segments](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_83AEC78CD25F442EBEE364856A889560).
1. **[!UICONTROL Métrica]**: (Barra lateral verde) Métrica que foi arrastada e solta da lista Métricas.
1. **[!UICONTROL Operador de comparação]** : Você pode comparar e restringir valores usando operadores selecionados.
1. **[!UICONTROL Valor]**: O valor inserido ou selecionado para a dimensão ou o segmento ou métrica.
1. **[!UICONTROL X]**: (Excluir) Permite excluir essa parte da definição do segmento.
1. **[!UICONTROL Salvar]** ou **[!UICONTROL Cancelar]**: Salva ou cancela o segmento. After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Pesquisa:]** Pesquisa a lista de dimensões, segmentos ou métricas.
1. **[!UICONTROL Dimensões:]** (Lista) Clique no cabeçalho para expandir.
1. **[!UICONTROL Métricas:]** Clique no cabeçalho para expandir.
1. **[!UICONTROL Segmentos:]** Clique no cabeçalho para expandir.
1. **[!UICONTROL Seletor de conjunto de relatórios:]** Permite selecionar o conjunto de relatórios no qual este segmento será salvo. Você ainda pode utilizar o segmento em todos os conjuntos de relatórios.
1. **[!UICONTROL Visualização do segmento:]** Permite visualizar as métricas principais para verificar se você tem um segmento válido e a amplitude do segmento. Represente o detalhamento do conjunto de dados que você pode esperar ao aplicar esse segmento. Mostra 3 círculos concêntricos e uma lista para mostrar o número e o percentual de correspondências para [!UICONTROL Ocorrências], [!UICONTROL Visitas] e [!UICONTROL Visitantes] para uma execução de segmentos em comparação ao conjunto de dados. Esse gráfico é atualizado imediatamente depois de criar ou efetuar alterações para sua definição de segmento.
1. **[!UICONTROL Compatibilidade do produto:]** Fornece uma lista de quais produtos do Adobe Analytics (Analysis Workspace, [!UICONTROL Relatórios e análises], Análise ad hoc, Data Warehouse) com os quais o segmento criado é compatível. A maioria dos segmentos são compatíveis com todos os produtos. Contudo, nem todos os operadores e dimensões são compatíveis com todos os produtos Analytics, especialmente o [Data Warehouse](../../../components/c-segmentation/seg-reference/seg-compatibility.md#concept_7A2CC00352274A75ACD4949CA3C144D4). Esse gráfico é atualizado imediatamente depois de efetuar alterações na definição do segmento.

   Segments with embedded date ranges continue to operate differently in Analysis Workspace versus [!UICONTROL Reports &amp; Analytics]: In Workspace, a segment with an embedded date range overrides the panel date range. By contrast, [!UICONTROL Reports &amp; Analytics] gives you the intersection of the report date range and the segment's embedded date range.

**[!UICONTROL Publicar na Experience Cloud (para`<report suite name>`)]**: (Não exibido na tela) Essa opção aparece somente se o conjunto de relatórios no qual você está salvando este segmento estiver [habilitado para a Experience Cloud](../../../components/c-segmentation/c-segmentation-workflow/seg-workflow.md#concept_1E9FC92437D748C392546542B6511D01). By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. É necessário um título de segmento e uma descrição.

>[!NOTE]
>
>No Analytics, você pode editar ou excluir um segmento publicado. Se o segmento estiver em uso, uma mensagem de aviso será emitida quando um segmento for editado. Não é possível excluir um segmento publicado que esteja sendo usado pelo Adobe [!DNL Target].

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>É necessário limitar o número de públicos-alvo compartilhados do Analytics a 20 para evitar atrasos adicionais no processamento. Públicos-alvo compartilhados com a Experience Cloud a partir do Analytics não podem exceder 20 milhões de membros únicos. Além disso, devido a questões relacionadas ao cache, conjuntos de relatórios excluídos no Analytics permanecem exibidos na Experience Cloud por 12 horas após a exclusão.

>[!IMPORTANT]
>
>Once a visitor qualifies for the audience shared from Analytics, there is a 24 - 48 hour delay before that information is actionable in [!DNL Target], [!DNL Advertising Cloud], and [!DNL Campaign].

## Build segments {#section_050E3343533E45C3923242398E0E0213}

1. Arraste uma Dimensão, um Segmento ou Evento de métrica do painel esquerdo até o campo [!UICONTROL Definições].

   ![](assets/drag_n_drop_dimension.png)

   O contêiner de nível superior padrão [!UICONTROL Ocorrência] é mostrado após arrastar um elemento para [!UICONTROL Definições]. É possível alterar o tipo de contêiner até Visita ou Visitante do menu suspenso **[!UICONTROL Mostrar].**

1. Set the [operator](../../../components/c-segmentation/seg-reference/seg-operators.md) from the drop-down menu.
1. Digite ou selecione um valor para o item selecionado.
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. Depois de colocar os contêineres e definir as regras, consulte os resultados do segmento no gráfico de validação na parte superior à direita. O validador indica o percentual e o número absoluto de visualizações de página, visitas e visitantes únicos que corresponde ao segmento criado.
1. Under **[!UICONTROL Tags]**, [tag](../../../components/c-segmentation/c-segmentation-workflow/seg-tag.md#concept_CD892CEB326C4986A1B67487052DBA50) the container by selecting an existing tag or creating a new one.
1. Clique em **[!UICONTROL Salvar]para salvar o segmento.**

You are now taken to the [Segment Manager](../../../components/c-segmentation/c-segmentation-workflow/seg-manage.md#concept_7A2E019317864065B7C641DC3315928F), where you can tag, share, and manage your segment in multiple ways.

## Build and nest containers {#section_1C38F15703B44474B0718CEF06639EFD}

You can [build a framework of containers](../../../components/c-segmentation/seg-overview.md#concept_82653C7E29FE49F5A4B5E5E93B0A6399) and then place logic rules and operators between.

1. Clique em **[!UICONTROL Opções &gt; Adicionar contêiner]**.

   ![](assets/add_container.png)

   Um novo contêiner [!UICONTROL Ocorrência] abre sem uma [!UICONTROL Ocorrência] (Visualização de página) identificada.

   ![](assets/new_container.png)

1. Altere o tipo de contêiner como necessário.
1. Arraste uma Dimensão, um Segmento ou Evento do painel esquerdo até o contêiner.
1. Continue to add new containers from the top-level **[!UICONTROL Options]** &gt; **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **OU**

   Select one or more rules and then click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]**. Isso transforma sua seleção em um contêiner separado.

## Use date ranges in segments {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

É possível criar segmentos que contêm intervalos de datas flexíveis para responder questões sobre campanhas ou eventos em andamento.

Por exemplo, crie com facilidade um segmento que inclua “todos que realizaram uma compra nos últimos 60 dias”.

Crie um contêiner de Visita e adicione o intervalo [!UICONTROL Últimos 60 dias] e a métrica [!UICONTROL Pedido é superior ou igual a 1], com um operador E:

![](assets/date-ranges.png)

## Stack segments {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

O empilhamento de segmentos funciona ao combinar os critérios em cada segmento com um operador "e", em seguida, ao aplicar os critérios combinados.

Por exemplo, empilhar um segmento de "usuários de telefones celulares" e um segmento "Geografia dos EUA" retorna dados somente para usuários de telefones celulares nos EUA.

Pense nesses segmentos como blocos de construção ou módulos que você pode incluir em uma biblioteca de segmentos para que os usuários usem como necessário. Dessa forma, você pode reduzir dramaticamente o número de segmentos necessários. Por exemplo, considera que você tem 40 segmentos:

* 20 para usuários de telefones celulares em países diferentes (US_mobile, Germany_mobile, France_mobile, Brazil_mobile etc.)
* 20 para usuários de tablet em países diferentes (US_tablet, Germany_tablet, France_tablet, Brazil_tablet etc.)

Ao usar o empilhamento de segmentos, você pode reduzir a contagem de segmentos em 22 e empilhá-los como necessário. É necessário criar esses segmentos:

* um segmento para usuários móveis
* um segmento para usuários de tablets
* 20 segmentos para localidades geográficas diferentes

>[!NOTE]
>
>Ao empilhar dois segmentos, eles são unidos por padrão por uma instrução AND. Isso não pode ser alterado para uma instrução OU.

1. Vá para o Construtor de segmentos.
1. Forneça um título e uma descrição para o segmento.

   Resultado da etapa 1. Clique em **[!UICONTROL Mostrar segmentos]para trazer a lista de segmentos para frente no painel de navegação à esquerda.**

   Resultado da etapa 1. Arraste e solte os segmentos que você deseja empilhar na área de definição de segmentos. Este é um exemplo de segmento que empilha os segmentos existentes "Visitas de tablets" e "Geográfico EUA":

   ![](assets/seg_stack2.png)

1. Salve o segmento.

   Resultado da etapa

## Use segment templates {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Os modelos representam os segmentos antigos pré-configurados e do pacote.

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. Now click the Segments icon  ![](assets/segment_icon.png)

para abrir o trilho de segmentos. Os modelos do segmento aparecem na parte inferior da lista de segmentos. É possível distingui-los por um ícone de pasta à esquerda do nome do modelo:

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

## Example: Campaign visitors segment {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

Mostra um exemplo deste segmento frequentemente usado.

Vários clientes desejam visualizar as métricas dos visitantes que responderam a campanhas específicas. A criação de um segmento de visitantes da campanha é uma forma fácil de obter esses dados.

A construção desse segmento no Construtor de segmentos significa que de um contêiner de Visita de nível superior você arrasta uma dimensão de campanha, neste caso Nome da campanha:

![](assets/seg_campaign_visitor.png)

(Opcional) Você também pode aplicar uma tag de Campanhas a esse segmento, se você deseja filtrar facilmente todos os segmentos relacionados à campanha.
