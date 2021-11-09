---
description: O Construtor de segmentos fornece uma tela para arrastar e soltar Dimensões de métricas, Segmentos e Eventos para os visitantes do segmento com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar segmentos simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.
title: Construir segmentos
feature: Segmentation
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 86766c4452a571a7c7b36ad6693a1a1e0bc2deea
workflow-type: tm+mt
source-wordcount: '2046'
ht-degree: 99%

---

# Construtor de segmentos

O [!UICONTROL Construtor de segmentos] permite que você construa segmentos simples ou complexos que identificam atributos e ações do visitante e ocorrências da página. Fornece uma tela para arrastar e soltar dimensões de métrica, eventos, ou outros segmentos na ordem para visitantes de segmento com base em lógica, regras e operadores de hierarquia.

Há várias maneiras de acessar o Construtor de segmentos:

* **Navegação superior do Analytics**: clique em **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Segmentos]**.
* **[!UICONTROL Analysis Workspace]**: clique em **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, abra um projeto e clique em **[!UICONTROL + Novo]** > **[!UICONTROL Criar segmento]**.
* **[!UICONTROL Reports &amp; Analytics]**: clique em **[!UICONTROL Analytics]** > **[!UICONTROL Relatórios]**, abra um relatório existente e clique no ícone de Segmentos ![](assets/segment_icon.png) na navegação à esquerda e, em seguida, clique em **[!UICONTROL Adicionar]**.
* **[!UICONTROL Report Builder]**: [adicionar ou editar segmentos no Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=pt-BR).

## Critérios do construtor {#section_F61C4268A5974C788629399ADE1E6E7C}

É possível adicionar definições de regra e contêiners para definir seus segmentos.

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Título]**: nomeie o segmento.
1. **[!UICONTROL Descrição]**: forneça uma descrição para o segmento.
1. **[!UICONTROL Tags]**: [marque os segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) que você está criando ao selecionar de uma lista de tags existentes ou criar uma nova tag.
1. **[!UICONTROL Definições]**: é aqui que você [constrói e configura segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md), adiciona regras, bem como aninha e faz a sequência de contêineres.
1. **[!UICONTROL Mostrar]**: (seletor de contêiner superior.) Permite que você selecione o [contêiner de nível superior](/help/components/segmentation/seg-overview.md) ([!UICONTROL Visitante], [!UICONTROL Visita], [!UICONTROL Ocorrência]). O contêiner de nível superior padrão no contêiner Ocorrência.
1. Ícone **[!UICONTROL Opções]**: (engrenagem)

   * **[!UICONTROL + Adicionar contêiner]**: permite que você adicione um novo contêiner (abaixo do contêiner de nível superior) à definição do segmento.
   * **[!UICONTROL Excluir]**: permite definir o segmento ao excluir uma ou mais dimensões, segmentos ou métricas.

1. **[!UICONTROL Dimensões]**: os componentes são arrastados e soltos na lista Dimensões (barra lateral laranja).
1. **[!UICONTROL Operador]**: é possível comparar e restringir valores utilizando operadores selecionados.
1. **[!UICONTROL Valor]**: o valor inserido ou selecionado para a dimensão, segmento ou métrica.
1. **[!UICONTROL Modelos de atribuição]**: disponíveis apenas para dimensões, esses modelos determinam quais valores segmentar em uma dimensão. Os modelos de dimensão são especialmente úteis na segmentação sequencial.

   * **[!UICONTROL Repetição]** (padrão): inclui instâncias e valores persistentes da dimensão.
   * **[!UICONTROL Instância]**: inclui instâncias da dimensão.
   * **[!UICONTROL Instância de não repetição]**: inclui instâncias exclusivas (não repetitivas) da dimensão. Esse é o modelo aplicado no Fluxo quando instâncias repetidas são excluídas.

   ![](assets/attribution-models.jpg)

   **Exemplo: segmento de ocorrência onde eVar1 = A**

   | Exemplo | A | A | A (persistente) | B | A | C |
   |---|---|---|---|---|---|---|
   | Repetição | X | X | X | - | X | - |
   | Instância | X | X | - | - | X | - |
   | Instância de não repetição | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: atribui os operadores [!UICONTROL AND/OR/THEN] entre contêineres ou regras. O operador THEN permite que você [defina segmentos sequenciais](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
1. **[!UICONTROL Métrica]**: (barra lateral verde) métrica que foi arrastada e solta na lista de Métricas.
1. Operador **[!UICONTROL Comparação]**: é possível comparar e restringir valores com operadores selecionados.
1. **[!UICONTROL Valor]**: o valor inserido ou selecionado para a dimensão, segmento ou métrica.
1. **[!UICONTROL X]**: (excluir) permite que você exclua essa parte da definição de segmentos.
1. **[!UICONTROL Publicação na Experience Cloud]**: A publicação de um segmento do Adobe Analytics na Experience Cloud permite que você use o segmento para atividade de marketing no [!DNL Audience Manager] e em outros canais de ativação. [Saiba mais...](/help/components/segmentation/segmentation-workflow/seg-publish.md)
1. **[!UICONTROL Biblioteca de público-alvo]**: Os serviços de público-alvo da Adobe gerenciam a conversão dos dados do visitante em segmentação do público-alvo. Assim, criar e gerenciar públicos-alvo é como criar e usar segmentos, com a capacidade adicional de compartilhar o segmento do público-alvo com a Experience Cloud. [Saiba mais...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR)
1. **[!UICONTROL Pesquisa]**: pesquisa a lista de dimensões, segmentos ou métricas.
1. **[!UICONTROL Dimensões]**: (Lista) clique no cabeçalho para expandir.
1. **[!UICONTROL Métrica]**: clique no cabeçalho para expandir.
1. **[!UICONTROL Segmentos]**: clique no cabeçalho para expandir.
1. **[!UICONTROL Seletor do conjunto de relatórios]**: permite selecionar o conjunto de relatórios em que esse segmento será salvo. Você ainda pode utilizar o segmento em todos os conjuntos de relatórios.
1. **[!UICONTROL Visualização de segmento]**: permite que você visualize as métricas principais para conferir se você tem um segmento válido e a amplitude deste. Represente o detalhamento do conjunto de dados que você pode esperar ao aplicar esse segmento. Mostra 3 círculos concêntricos e uma lista para mostrar o número e o percentual de correspondências para [!UICONTROL Ocorrências], [!UICONTROL Visitas] e [!UICONTROL Visitantes] para uma execução de segmentos em comparação ao conjunto de dados. Esse gráfico é atualizado imediatamente depois de criar ou efetuar alterações para sua definição de segmento.
1. **[!UICONTROL Compatibilidade de produto]**: fornece uma lista de quais produtos do Adobe Analytics (Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Data Warehouse) são compatíveis com o segmento que você criou. A maioria dos segmentos são compatíveis com todos os produtos. Contudo, nem todos os operadores e dimensões são compatíveis com todos os produtos Analytics, especialmente o [Data Warehouse](/help/components/segmentation/seg-reference/seg-compatibility.md). Esse gráfico é atualizado imediatamente depois de efetuar alterações na definição do segmento.
1. **[!UICONTROL Salvar]** ou **[!UICONTROL Cancelar]**: salva ou cancela o segmento. Depois de clicar em **[!UICONTROL Salvar]**, você é levado para o Gerenciador de segmentos onde é possível gerenciar o segmento.

Segmentos com intervalos de datas incorporados continuarão a operar de forma diferente na Analysis Workspace com relação ao [!UICONTROL Reports &amp; Analytics]: na Workspace, um segmento com um intervalo de datas inserido substitui o intervalo de datas do painel. Ao contrário, o [!UICONTROL Reports &amp; Analytics] gera a interseção entre intervalo de datas do relatório e o intervalo de datas inserido do segmento.

## Construir segmentos {#build-segments}

1. Arraste uma Dimensão, um Segmento ou Evento de métrica do painel esquerdo até o campo [!UICONTROL Definições].

   ![](assets/drag_n_drop_dimension.png)

   O contêiner de nível superior padrão [!UICONTROL Ocorrência] é mostrado após arrastar um elemento para [!UICONTROL Definições]. É possível alterar o tipo de contêiner até Visita ou Visitante do menu suspenso **[!UICONTROL Mostrar]**.

1. Defina o [operador](/help/components/segmentation/seg-reference/seg-operators.md) no menu suspenso.
1. Digite ou selecione um valor para o item selecionado.
1. Adicione contêineres adicionar se necessário, com as regras **[!UICONTROL E]**, **[!UICONTROL Ou]**, ou **[!UICONTROL Então]**.
1. Depois de colocar os contêineres e definir as regras, consulte os resultados do segmento no gráfico de validação na parte superior à direita. O validador indica o percentual e o número absoluto de visualizações de página, visitas e visitantes únicos que corresponde ao segmento criado.
1. Em **[!UICONTROL Tags]**, [marque](/help/components/segmentation/segmentation-workflow/seg-tag.md) o contêiner ao selecionar uma tag existente ou cria uma nova.
1. Clique em **[!UICONTROL Salvar]** para salvar o segmento.

Agora você é levado ao [Gerenciador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md), onde é possível marcar, compartilhar e gerenciar o segmento de várias maneiras.

## Adicionar contêiners {#section_1C38F15703B44474B0718CEF06639EFD}

É possível [construir uma estrutura de contêineres](/help/components/segmentation/seg-overview.md) e, em seguida, colocar regras de lógica e operadores entre eles.

1. Clique em **[!UICONTROL Opções > Adicionar contêiner]**.

   ![](assets/add_container.png)

   Um novo contêiner [!UICONTROL Ocorrência] abre sem uma [!UICONTROL Ocorrência] (Visualização de página) identificada.

   ![](assets/new_container.png)

1. Altere o tipo de contêiner como necessário.
1. Arraste uma Dimensão, um Segmento ou Evento do painel esquerdo até o contêiner.
1. Continue a adicionar novos contêineres com o botão **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner]** na parte superior da definição, ou adicione contêineres de um contêiner para aninhar a lógica.

   **OR**

   Selecione uma ou mais regras, em seguida, clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]**. Isso transforma sua seleção em um contêiner separado.

## Utilize intervalos de datas {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

É possível criar segmentos que contêm intervalos de datas flexíveis para responder questões sobre campanhas ou eventos em andamento.

Por exemplo, crie com facilidade um segmento que inclua &quot;todos que realizaram uma compra nos últimos 60 dias&quot;.

Crie um contêiner de Visita e adicione o intervalo [!UICONTROL Últimos 60 dias] e a métrica [!UICONTROL Pedido é superior ou igual a 1], com um operador AND:

![](assets/date-ranges.png)

Este é um vídeo sobre o uso de intervalos de datas flexíveis em segmentos:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Empilhar segmentos {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

O empilhamento de segmentos funciona ao combinar os critérios em cada segmento com um operador &quot;and&quot;, em seguida, ao aplicar os critérios combinados. Isso pode ser feito diretamente em um projeto do Workspace ou no construtor de segmentos.

Por exemplo, empilhar um segmento de &quot;usuários de telefones celulares&quot; e um segmento &quot;Geografia dos EUA&quot; retorna dados somente para usuários de telefones celulares nos EUA.

Pense nesses segmentos como blocos de construção ou módulos que você pode incluir em uma biblioteca de segmentos para que os usuários usem como necessário. Dessa forma, você pode reduzir dramaticamente o número de segmentos necessários. Por exemplo, considera que você tem 40 segmentos:

* 20 para usuários de telefones celulares em países diferentes (US_mobile, Germany_mobile, France_mobile, Brazil_mobile etc.)
* 20 para usuários de tablet em países diferentes (US_tablet, Germany_tablet, France_tablet, Brazil_tablet etc.)

Ao usar o empilhamento de segmentos, você pode reduzir a contagem de segmentos em 22 e empilhá-los como necessário. É necessário criar esses segmentos:

* um segmento para usuários móveis
* um segmento para usuários de tablets
* 20 segmentos para localidades geográficas diferentes

>[!NOTE]
>
>Ao empilhar dois segmentos, eles são unidos por padrão por uma instrução AND. Isso não pode ser alterado para uma instrução OR.

1. Vá para o Construtor de segmentos.
1. Forneça um título e uma descrição para o segmento.

   Resultado da etapa 1. Clique em **[!UICONTROL Mostrar segmentos]** para trazer a lista de segmentos para frente no painel de navegação à esquerda.

   Resultado da etapa 1. Arraste e solte os segmentos que você deseja empilhar na área de definição de segmentos. Este é um exemplo de segmento que empilha os segmentos existentes &quot;Visitas de tablets&quot; e &quot;Geográfico EUA&quot;:

   ![](assets/seg_stack2.png)

1. Salve o segmento.

   Resultado da etapa

## Modelos de segmento {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Os modelos de segmentos são fornecidos para casos de uso comum de segmentação, como &quot;Novas visitas&quot; ou &quot;Visitas de dispositivos móveis&quot;. Eles estão disponíveis em projetos do Workspace e no construtor de segmentos como blocos de construção para novos segmentos.

Os modelos são indicados pelo logotipo &quot;A&quot; da Adobe. Uma amostra dos modelos está listada abaixo:

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
   <td colname="col1"> Visitas em única página </td> 
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
