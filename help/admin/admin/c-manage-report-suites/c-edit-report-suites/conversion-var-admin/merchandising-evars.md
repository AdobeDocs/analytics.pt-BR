---
title: eVars de merchandising e métodos de busca de produtos
description: Um aprofundamento nos conceitos por trás das eVars de merchandising e como elas processam e alocam dados.
feature: Admin Tools
role: Admin
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '5279'
ht-degree: 96%

---

# eVars de merchandising e métodos de busca de produtos

Este documento detalhado explica os conceitos por trás das eVars de merchandising, que processam e alocam dados de forma diferente das eVars padrão. Ele também explica como as eVars de merchandising estão relacionadas aos métodos de busca de produtos.

## Visão geral

Usar eVars de merchandising permite alocar qualquer atividade bem-sucedida nos valores capturados pelas eVars em um nível *por produto* em vez de um nível *por visita/por pedido*.

Embora a maioria dos sites de varejo tenha muitas maneiras de encontrar produtos, a Adobe considera que os seguintes são os métodos fundamentais de busca de produtos que cada cliente de varejo deve utilizar no Adobe Analytics:

* Palavras-chave de pesquisa interna
* Códigos de rastreamento de campanha interna
* Categorias de merchandising/navegação
* Links de venda cruzada

Para fins deste documento, vamos mapear algumas eVars para as suas soluções da seguinte maneira:

* eVar2: palavras-chave de pesquisa interna
* eVar3: códigos de rastreamento de campanha interna
* eVar4: categorias de merchandising/navegação
* eVar5: links de venda cruzada

Podemos usar uma eVar adicional para medir o desempenho de todos os métodos de busca de produtos em relação uns aos outros. Além dos métodos de busca descritos acima, a eVar inclui outros métodos semelhantes, como links para páginas de detalhes de produtos de sites externos.

* eVar1: métodos de busca de produtos

Em vez de configurar qualquer uma dessas variáveis para serem eVars padrão, configure-as para serem eVars de merchandising.

Para demonstrar como definir essas variáveis, aqui está um exemplo em que um visitante decide usar a palavra-chave de pesquisa interna “sandálias”, para localizar um produto no site. Na página de resultados da pesquisa por palavra-chave, você deve capturar dados em pelo menos duas eVars:

* `eVar2` é igual à palavra-chave que foi usada na pesquisa (“sandálias”)
* `eVar1` é igual ao método de descoberta de produto usado (“pesquisa interna por palavra-chave”).

Ao definir essas duas variáveis iguais a esses valores específicos, você sabe que o visitante está usando o termo de pesquisa interna por palavra-chave “sandálias” para localizar um produto. Ao mesmo tempo, você sabe que o visitante não está usando os outros métodos de busca de produtos para localizar produtos (por exemplo, o visitante não está navegando pelas categorias de produtos exatamente ao mesmo tempo em que está realizando uma pesquisa por palavra-chave). Para garantir que a alocação adequada por produto ocorra, esses métodos não utilizados não devem receber crédito pela localização de um produto encontrado por meio de uma pesquisa interna por palavra-chave. Portanto, você deve inserir lógica no código (como AppMeasurement, Adobe Experience Platform Web SDK e assim por diante) que define automaticamente as eVars associadas a esses outros métodos de descoberta como um valor de &quot;método que não seja de descoberta&quot;.

Por exemplo, quando um usuário pesquisa produtos usando a palavra-chave “sandálias”, a lógica do código do Analytics deve definir as variáveis na página de resultados da pesquisa interna por palavra-chave da seguinte maneira:

* eVar2=&quot;sandálias&quot;: a palavra-chave “sandálias” foi usada na pesquisa interna por palavra-chave
* eVar1=&quot;pesquisa interna por palavra-chave&quot;: o método de busca “pesquisa interna por palavra-chave” foi usado
* eVar3=&quot;campanha não interna&quot;: uma campanha interna não foi usada para acessar a página de resultados da pesquisa
* eVar4=&quot;não navegado&quot;: uma categoria de navegação não foi acessada na página de resultados da pesquisa
* eVar5=&quot;venda não cruzada&quot;: um link de venda cruzada não foi clicado na página Resultados da pesquisa

## Configurações de eVars de merchandising

Estas são as diferentes configurações que você pode usar com as eVars de merchandising. A seguinte captura de tela é do Gerenciador de conjunto de relatórios. Acesse em [!UICONTROL Analytics] > [!UICONTROL Administrador] > [!UICONTROL Conjuntos de relatórios] > [!UICONTROL Editar configurações] > [!UICONTROL Conversão] > [!UICONTROL Variáveis de conversão] > [!UICONTROL Adicionar novo] > [!UICONTROL Habilitar merchandising].

![eVars Merch](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/assets/merch-evars1.png)

Encontre mais detalhes sobre essas configurações nas seções abaixo da tabela.

| Configuração | Descrição |
|--- | --- |
| Nome | O Nome ou a dimensão de relatório à qual a variável deve ser associada. Se o objetivo de `eVar1` for capturar os Métodos de descoberta de produto, o campo Nome para `eVar1` deverá ser definido como &quot;Métodos de descoberta de produto&quot;. |
| Merchandising | O tipo de sintaxe que será usada para capturar os valores de eVar de merchandising |
| Alocação | Ajuda a determinar o valor do eVar de merchandising que deverá receber crédito quando um evento bem-sucedido ocorrer. |
| Expirar após | Determina quando os vínculos de eVar de produto e merchandising existentes não devem mais estar em vigor. |
| Tipo | O tipo de dados que está sendo coletado no eVar de comercialização |
| Evento compulsório de merchandising | Os eventos que determinam quando um produto deve ser vinculado a um valor de eVar de comercialização |
| Redefinir | Um acionador que redefinirá todos os dados de back-end do eVar nesse ponto |
| Ativar o merchandising | Um sinalizador que precisa ser definido como &quot;Ativado&quot; para transformar o eVar de um eVar padrão em um eVar de comercialização |

### Ativar o merchandising

Quando a configuração &quot;Ativar merchandising&quot; estiver definida como &quot;Ativado&quot;, todas as configurações conforme descrito abaixo serão exibidas no Gerenciador de conjunto de relatórios. Quando a configuração &quot;Ativar merchandising&quot; estiver definida como &quot;Desativado&quot;, somente as configurações de eVar padrão estarão disponíveis.

### Merchandising

Essa opção não está disponível para eVars padrão. A configuração [!UICONTROL Merchandising] permite selecionar [!UICONTROL Sintaxe de variável de conversão] ou [!UICONTROL Sintaxe de produto] como o método para capturar o valor do eVar de merchandising.

**[!UICONTROL A sintaxe da variável de conversão]** significa que você definiu o valor do eVar em sua própria variável. Por exemplo, com a Sintaxe de variável de conversão, a variável `eVar1` O valor de &quot;pesquisa interna de palavra-chave&quot; é definido da seguinte maneira no código de página (ou no código de AppMeasurement, código do Adobe Experience Platform Web SDK e assim por diante):

`s.eVar1="internal keyword search";`

Com a **[!UICONTROL Sintaxe de produto]**, no entanto, o eVar é definido somente na variável de produtos do Adobe Analytics. A variável de produtos do Analytics é dividida em seis partes diferentes por produto:

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Categoria] e [!UICONTROL Nome] identificam o produto em questão.
* [!UICONTROL Quantidade] e [!UICONTROL Receita] são úteis quando uma compra de produto está sendo rastreada.
* [!UICONTROL Eventos] são úteis para registrar valores de evento de moeda ou incrementais personalizados que não devem ser contados como receita (como frete, descontos etc.)

As eVars de merchandising configuradas para usar a Sintaxe de produto são definidas na parte final da variável products. Por exemplo, suponha que um visitante tenha usado uma pesquisa interna de palavra-chave para encontrar a ID de produto &quot;12345&quot;. A maneira baseada em sintaxe de produto de configurar o eVar1 neste exemplo seria semelhante a:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observe que ainda temos espaços reservados delimitados por ponto e vírgula para quantidade, receita e partes do evento da variável products.  Sem esses espaços reservados, a configuração `eVar1` da pesquisa interna de palavra-chave seria completamente ignorada.

### Alocação

O termo &quot;Alocação&quot; para eVars de merchandising é enganoso, especialmente para eVars de comercialização que usam Sintaxe de variável de conversão. Todas as eVars padrão podem ter sua própria configuração de alocação individual. No entanto, eVars de merchandising com Sintaxe de variável de conversão usam somente a configuração de alocação &quot;Mais recente (último)&quot;, independentemente das configurações de alocação no Gerenciador de conjunto de relatórios mostradas.

Entender o que essa configuração faz significa entender a diferença entre a alocação de eVar e a vinculação de eVar de merchandising. Para eVars de merchandising, &quot;Vínculo de eVar de merchandising&quot; é um nome mais apropriado para essa configuração de &quot;Alocação&quot;.

#### Configuração padrão de alocação de eVar

Sempre que qualquer eVar com sintaxe padrão é coletado de uma solicitação de imagem, os servidores de processamento do Adobe Analytics inserem dados em outra coluna de banco de dados, chamada de coluna `post_evar`. Como as eVars devem ser persistentes, elas expiram em algum ponto além da ocorrência atual na maioria dos casos. Os servidores definem essa coluna `post_evar` em cada solicitação de imagem subsequente. É definido como igual ao último valor passado para o eVar correspondente. Para eVars padrão, quando um evento bem-sucedido ocorre, o Adobe Analytics usa a coluna `post_evar` em vez da coluna de eVar regular para determinar o valor do eVar que deve receber crédito pelo evento.

Para eVars padrão, a configuração Alocação determina se o primeiro ou o último valor de eVar coletado durante determinado período será inserido na coluna `post_evar`. Se a configuração Alocação de um eVar padrão for igual ao &quot;Valor original (primeiro)&quot;, o primeiro valor de eVar coletado do visitante será inserido na coluna `post_evar` para todas as solicitações de imagem subsequentes. Isso continua para todas as solicitações futuras enviadas do navegador do visitante até que o eVar expire de acordo com a configuração &quot;Expirar após&quot;.

Se a configuração Alocação de um eVar padrão for igual a &quot;Mais recente (último)&quot;, o valor de eVar mais recente coletado do visitante será preenchido na coluna `post_evar` para todas as solicitações de imagem subsequentes. A alocação &quot;Mais recente (último)&quot; implica que o valor `post_evar` muda sempre que o eVar correspondente é definido como um novo valor em qualquer solicitação de imagem. A alocação &quot;Valor original (primeiro)&quot; implica que a coluna `post_evar` não é alterada entre ocorrências, mesmo que seu eVar correspondente possa ser definido com um valor diferente em uma solicitação de imagem futura.

#### Configuração de alocação de eVar de merchandising (compulsório)

Como mencionado anteriormente, todas as eVars de merchandising com Sintaxe de variável de conversão têm somente a alocação &quot;Mais recente (último)&quot;.  Assim, a configuração Alocação de eVars de merchandising não determina quais valores são inseridos na coluna post_evar, pois um visitante continua usando o site. Em vez disso, essa configuração determina qual valor de eVar se vincula a um produto e como esses produtos alocam os eventos de sucesso de volta aos valores de eVar aos quais estão vinculados.

O seguinte acontece quando a configuração Alocação de eVar de merchandising (ou seja, vinculação) é definida como “Valor original (primeiro)”: qualquer produto definido com a coluna post_evar e que não tenha sido previamente vinculado à eVar &quot;pré-processada&quot; correspondente da coluna post_evar será vinculado ao valor contido na coluna post_evar. Esse vínculo entre o valor da eVar e o produto nunca será alterado até que a eVar expire de acordo com as definições de “Expirar após” nas configurações do Conjunto de relatórios.

Sempre que uma solicitação de imagem atender aos critérios que, de outra forma, vinculariam um produto já vinculado ao valor do eVar definido mais recentemente, a configuração &quot;Valor original (primeiro)&quot; forçará os servidores de coleta de dados do Adobe Analytics a ignorar quaisquer tentativas adicionais. O oposto acontece com eVars de merchandising com a configuração Alocação (vinculação) igual a &quot;Mais recente (último)&quot;. Sempre que uma solicitação de imagem atender aos critérios que vinculam um produto a um eVar de merchandising, o produto se vinculará (e se vinculará novamente) ao valor mais recente passado para o eVar ou ao valor que está (sempre) contido na coluna `post_evar`.

Como mencionado anteriormente, eVars de merchandising permitem alocar eventos bem-sucedidos para valores de eVar por produto, em vez de por visita/por pedido. Assim, sempre que um produto vinculado tiver um evento bem-sucedido (como uma adição ou compra de carrinho) associado a ele, o evento bem-sucedido dará seu crédito ao produto e aos valores de eVar de merchandising aos quais o produto está vinculado no momento.

### Expirar após

A configuração de expiração de uma eVar de merchandising permite escolher

* Quando os vínculos produto/eVar devem expirar e

* Quando a coluna post_evar não deve mais ser preenchida automaticamente depois que uma eVar é transmitida a uma solicitação de imagem.

A expiração de uma eVar pode ocorrer quando um evento bem-sucedido é registrado ou um determinado período passa. O Adobe Analytics permite somente uma configuração de Expiração por vez por eVar.

Para o Método de descoberta de produto, a prática recomendada para definir a expiração de uma eVar de merchandising deve ser configurá-la como

* O tempo que um produto é mantido no carrinho de compras de um site antes que o site o remova automaticamente do carrinho (por exemplo, 14 dias, 30 dias etc.)
* OU quando o evento de compra ocorre.

Com qualquer configuração, todos os produtos que um visitante adquire têm o pedido/unidade/crédito de receita alocado para os valores de eVar de merchandising aos quais os produtos estavam vinculados naquele momento.

### Tipo

A configuração do tipo de eVar determina o tipo de dados que é inserido no eVar. Na maioria dos casos, esse valor deve ser igual a &quot;Texto&quot;. É raro usar &quot;Contador&quot; para uma eVar de merchandising. No entanto, &quot;Contador&quot; pode ser usado para alocar o sucesso aos valores de eVar do Contador com base em cada produto.  A discusão de soluções do tipo &quot;Contador&quot; está fora do escopo deste documento.

### Evento compulsório de merchandising

A configuração Evento compulsório de merchandising permite especificar as condições que fazem com que um produto seja vinculado ao valor de uma eVar de merchandising. Essas condições estão limitadas ao acionamento de eventos bem-sucedidos específicos ou eVars somente. O acionamento de variáveis de tráfego (por exemplo, props) não afeta os vínculos de merchandising.

Observe que a configuração Evento compulsório de merchandising pode vincular um produto a um valor de eVar por meio de mais de um evento. Exemplos:

* Por meio de um evento de visualização de produto
* Por meio de um evento de adição ao carrinho
* Por meio de um evento de compra

Por padrão, a configuração vincula um produto a um valor de eVar de merchandising sempre que outro evento/eVar (merchandising ou padrão) estiver contido na mesma solicitação de imagem do produto.

### Redefinir

A configuração Redefinir permite que você &quot;expire&quot; imediatamente todos os valores de eVar para todos os visitantes que atualmente têm um valor `post_evar` no banco de dados de back-end do Adobe Analytics. Também elimina todos os vínculos atuais de produto/eVar.

>[!IMPORTANT]
>A Adobe não recomenda usar a configuração Redefinir, a menos que você pretenda que o eVar recomece completamente com uma &quot;tabulação limpa&quot; de dados a partir do momento em que a redefinição ocorrer.

## Quais configurações você deve usar?

Entre as muitas combinações de configurações disponíveis, você pode se perguntar quais configurações são uma prática recomendada?

Se você quiser vincular &quot;pesquisa interna de palavra-chave&quot; à ID de produto 12345, a variável products será definida da seguinte maneira:

`s.products=";12345;;;;eVar1=internal keyword search";`

Qualquer evento bem-sucedido (adições ao carrinho, compras) capturado ao mesmo tempo que productID 12345 são creditados à ID de produto 12345 e ao valor de eVar1 de “pesquisa interna de palavra-chave”. A única maneira de um valor de eVar1 diferente receber crédito por eventos bem-sucedidos associados à ID de produto 12345 é se a eVar1 for posteriormente definida como um valor diferente na variável produtos (com a ID de produto 12345).

Por exemplo:

```js
s.products=";12345;;;;eVar1=internal campaign";
```

Essa configuração de variável altera o vínculo da ID do produto 12345 do valor de eVar1 de “pesquisa de palavra-chave interna” para o valor eVar1 de “campanha interna”. Além disso, essa mudança de revinculação ocorre quando a eVar é configurada para usar a sintaxe do produto e a configuração de alocação (vinculação) de “Mais recente (última)”. Se a configuração Alocação (vínculo) fosse definida como “Valor original (primeiro)”, definir a eVar1 como “campanha interna” ao lado da ID de produto 12345 não recuperaria a ID de produto 12345 para o valor de eVar1 de “campanha interna”. Em vez disso, o vínculo permaneceria com o valor originalmente vinculado - “pesquisa interna de palavra-chave”.

### Desafios de usar a sintaxe do produto

Sem um planejamento cuidadoso, vários problemas podem surgir com o uso da Sintaxe do produto. Considere o caso de usar várias eVars para rastrear os métodos de descoberta de produtos no site. Aqui, cada eVar do método de descoberta de produto individual deve ser definido ao mesmo tempo para dar um crédito específico ao eVar do método de descoberta (e as outras eVars do método de descoberta não recebem crédito). A Sintaxe do produto pode ser usada em tais cenários, mas o código resultante para implantação é mais complicado.

Se usarmos nosso exemplo original de &quot;sandálias&quot; e o adaptarmos para usar a Sintaxe de produto (supondo que o visitante tenha encontrado um produto com a ID de &quot;sandal123&quot; usando o termo de palavra-chave de &quot;sandals&quot;), a variável de produtos resultante deverá ser definida da seguinte maneira:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Embora a sintaxe da variável products seja longa neste exemplo, ela vinculará cada um dos valores de eVar vistos à ID de produto de &quot;sandal123&quot;. A partir de então, todos os eventos bem-sucedidos (por exemplo, inclusões de carrinho, compras) capturados ao mesmo tempo que o produto &quot;sandal123&quot; são creditados aos valores de eVar que foram vinculados por último ao produto.  Este exemplo de código mostra se uma compra de uma unidade do produto &quot;sandal123&quot; (por US$ 79,95) ocorre depois que as eVars acima foram vinculadas ao produto &quot;sandal123&quot;:

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Os seguintes valores teriam uma ordem, uma unidade e US$ 79,95 da receita atribuída a eles:

* Valor da eVar2 de &quot;sandals&quot;
* Valor de eVar1 de &quot;pesquisa interna de palavra-chave&quot;
* Valor eVar3 de &quot;campanha não interna&quot;
* Valor eVar4 de &quot;não navegação&quot;
* Valor de eVar5 de “não venda cruzada”

Essa é a atribuição correta, que não é um problema. Em vez disso, o grande dilema dessa abordagem é determinar como e quando definir as eVars de método de descoberta de produto.

Na maioria dos casos com a Sintaxe de produto, as eVars de método de descoberta de produto precisariam ser definidas em uma página de detalhes do produto, em vez de na página em que o método de descoberta foi realmente usado (por exemplo, na página de resultados de pesquisa de palavra-chave, na página de navegação, na página de aterrissagem da campanha interna etc.). É razoável supor que um produto não foi realmente &quot;encontrado&quot; até que um visitante interaja com um produto em algum grau. Dessa forma, essas eVars (usando Sintaxe de produto) não devem ser definidas na página de método de descoberta, pois vários produtos são (geralmente) exibidos nessas páginas. Queremos vincular o valor do método de descoberta somente aos produtos com os quais o visitante interagiu.

Além disso, ao visualizar uma página de método de descoberta, os visitantes podem ter a capacidade de clicar em um link que os leva para uma página de detalhes do produto individual ou adicionar um produto individual ao carrinho diretamente da página de método de descoberta. Usando nosso exemplo de palavra-chave de pesquisa &quot;sandals&quot;, se um visitante adicionar o produto &quot;sandal123&quot; ao carrinho diretamente de uma página de resultados de pesquisa por palavra-chave, o código para capturar a adição do carrinho (por meio do evento onClick do botão Adicionar ao carrinho etc.) precisará ser gerado dinamicamente no momento em que a adição do carrinho ocorrer ou &quot;codificado&quot; diretamente por meio do código da página ou de um sistema de gerenciamento de tags.  Independentemente disso, o código a ser acionado em tais casos seria semelhante a:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Esse código vincula corretamente os valores de eVar vistos acima ao produto &quot;sandal123&quot;. No entanto, para definir esses valores adequadamente quando o evento de clique ocorrer, o desenvolvedor deverá:

* Adicionar a lógica do lado do servidor à página de resultados da pesquisa que determina os valores que devem ser inseridos nas eVars de método de descoberta do produto e
* Reunir toda a variável de produtos vista acima sem erros de sintaxe.

Além disso, se um visitante decidir &quot;encontrar&quot; o produto clicando em um link para a página de detalhes do produto, o desenvolvedor deverá:

* Passe os detalhes do método de descoberta do produto (como visto acima) da página de método de descoberta para a página de detalhes do produto e
* Recrie o mesmo valor de variável de produtos dos itens que foram transmitidos da página anterior.

### Quando a Sintaxe do produto é útil

A Sintaxe do produto ainda é útil quando

* Vários produtos com as mesmas IDs de produto recebem interação ao mesmo tempo e
* As eVars a serem vinculadas a esses produtos precisam ter valores diferentes por ID de produto.

Por exemplo, muitos produtos de roupas têm &quot;SKUs secundárias&quot;, que designam o tamanho, a cor, o estilo e quaisquer outros atributos. Esses atributos separam um único produto secundário de outros produtos que pertencem ao mesmo produto principal. Digamos que você decida comprar uma camiseta azul tamanho médio e uma camiseta vermelha tamanho grande. Suponha que ambas as camisetas tenham a ID de produto principal &quot;tshirt123&quot; e o `eVar10` tenha sido configurado para capturar SKUs secundárias. As variáveis definidas na página de confirmação de compra seriam definidas da seguinte maneira:

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

Nesse caso, ambos os valores `eVar10` (childSKU) de &quot;tshirt123-m-blue&quot; e &quot;tshirt123-l-red&quot; obtêm crédito pela compra das respectivas instâncias da ID de produto &quot;tshirt123&quot;.

### Desafios com a alocação &quot;mais recente&quot;

Você pode enfrentar problemas adicionais usando a configuração Alocação (vínculo) de &quot;Mais recente (último)&quot;. Em muitas experiências de navegação na Web, os visitantes &quot;encontram novamente&quot; um produto que já viram e/ou adicionaram ao carrinho. Isso geralmente acontece por meio de uma visita subsequente ou antes de eles decidirem concluir uma compra. Suponha que, durante uma visita ao site, um visitante encontre o produto “sandal123” por meio da pesquisa de palavra-chave “sandals”. Eles imediatamente o adicionam ao carrinho por meio da página de resultados da pesquisa de palavra-chave. O código que captura a adição do carrinho seria definido da seguinte maneira:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

Como resultado, cada valor de eVar visto nessa solicitação de imagem é vinculado ao produto &quot;sandal123&quot;.

Agora, imagine que o visitante não compra o produto durante essa visita, mas retorna ao site três dias depois com o produto “sandals123” ainda no carrinho. O visitante deseja saber mais sobre o produto antes de realizar a compra. Em vez de usar uma pesquisa por palavra-chave para encontrar o produto, o visitante navega pelo site. Ele chega à seção de navegação de comercialização &quot;mulheres > sapatos > sandálias&quot; logo antes de &quot;encontrar novamente&quot; o produto. Quando ele &quot;encontra novamente&quot; a página de detalhes do produto &quot;sandal123&quot;, as variáveis são definidas da seguinte maneira (no carregamento da página):

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Com uma configuração de Alocação (vínculo) de &quot;Mais recente (último)&quot;, o produto &quot;sandal123&quot; se vincula a valores de eVar completamente diferentes do que foi originalmente vinculado. Além disso, se o visitante concluir a compra de &quot;sandal123&quot;, todo o crédito de compra será dado a esses valores de eVar recém-vinculados, em vez dos valores originalmente vinculados!

A questão aqui é: quais valores de eVar devem receber crédito pela compra?&quot; Lembre-se de que o visitante encontrou inicialmente o produto &quot;sandal123&quot; por meio de uma pesquisa interna de palavra-chave. Em seguida, ele o adiciona ao carrinho diretamente na página de resultados de pesquisa. Portanto, o valor de eVar1 de &quot;pesquisa interna de palavra-chave&quot; (e o valor de eVar2 de &quot;sandals&quot;) deve receber crédito pela compra. No entanto, as configurações de Alocação (vínculo) foram definidas como &quot;Mais recente (último)&quot;. Portanto, o valor de eVar1 de &quot;browse&quot; (e o valor de eVar4 de &quot;womens > shoes > sandals&quot;) obteria o crédito de compra em vez disso. O motivo é que foram os últimos valores vinculados a &quot;sandal123&quot; antes de o visitante concluir a compra.

Uma solução para esse problema é alterar a configuração Alocação (vinculação) do eVar de merchandising de &quot;Mais recente (último)&quot; para &quot;Valor original (primeiro)&quot;. Dessa forma, os valores do eVar original vinculados ao produto &quot;sandal123&quot; recebem crédito quando a compra ocorre, independentemente de quantas vezes o visitante &quot;encontra novamente&quot; o produto.

Se o visitante adicionar um produto ao carrinho, mas nunca o comprar, a expiração do eVar permitirá que um novo valor do método de descoberta seja vinculado ao produto. A expiração do eVar deve ser igual ao tempo que um site permite que o produto permaneça no carrinho de compras antes de ser removido automaticamente.

### Utilização da sintaxe de variável de conversão

Vamos retornar à pergunta &quot;Sintaxe do produto&quot; vs. &quot;Sintaxe de variável de conversão&quot;. A Adobe descobriu um método mais fácil para coletar eVars de merchandising do método de descoberta de produtos e vincular seus valores a produtos encontrados pelos visitantes: o uso da Sintaxe de variável de conversão reduz o trabalho de implementação pelo qual os desenvolvedores do cliente são responsáveis. Ele ainda oferece as mesmas informações que o método da Sintaxe do produto (ou informações melhores). Os desenvolvedores simplesmente precisam seguir as instruções de implantação fornecidas, e o restante do código pode ser colocado no arquivo SDK da Web da Adobe AppMeasurement/Adobe Experience Platform.

Por exemplo, vamos examinar a solução recomendada para rastrear o desempenho interno da pesquisa de palavras-chave. Ela diz que, na página de resultados da pesquisa por palavra-chave, o código captura a palavra-chave pesquisada por meio de uma prop (por exemplo, prop4) e outra prop (por exemplo, prop5). Essas props rastreiam o número de resultados mostrados na pesquisa. Sempre que uma solicitação de imagem do Adobe Analytics era gerada na página de resultados da pesquisa, ela usava os objetos da camada de dados (ou código de página) implantados pelos desenvolvedores para preencher as variáveis acima (as props).

A lógica adicional contida no arquivo SDK da Web do AppMeasurement/Adobe Experience Platform pode preencher o restante das variáveis (eVars/dimensões de merchandising) que precisam ser definidas ao mesmo tempo.\
Por exemplo, se um novo visitante fizesse uma pesquisa por palavra-chave por &quot;sandals&quot;, que retornasse 25 resultados na página de resultados da pesquisa, o código a ser acionado (por meio do código da página OU da captura da camada de dados) seria semelhante a:

```js
s.prop4="sandals";
s.prop5="25";
```

A lógica no arquivo SDK do AppMeasurement/Analytics poderia transformar automaticamente esse trecho de código no seguinte:

```js
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Não há necessidade de se preocupar com a transmissão de dados para cada página e com a tentativa de criar uma sequência de caracteres muito grande e difícil de ser inserida na variável products. Em vez disso, os desenvolvedores podem implementar sua parte das soluções de rastreamento (que está inserida nas props) e deixar o restante da implementação para o código personalizado fornecido pela Adobe Consulting.

Como explicado anteriormente, todas as eVars de merchandising que usam a Sintaxe de variável de conversão têm a configuração Alocação de &quot;Mais recente (último)&quot;. Depois que um eVar é definido como qualquer valor, esse valor persiste em todas as ocorrências subsequentes (por meio da coluna post_evar). Ela persiste até ser definida como um valor diferente ou até que o eVar expire. Assim, qualquer produto com o qual qualquer pessoa interage depois que os eVars são definidos, se ainda não tiverem sido vinculados a esses eVars, vincula-se aos valores &quot;Mais recente (último)&quot; passados ao eVar.

Usando nosso exemplo acima, o valor `eVar2` de &quot;sandals&quot; e o valor de eVar1 de &quot;pesquisa interna de palavra-chave&quot; etc. persiste em todas as páginas visualizadas depois que a pesquisa por palavra-chave ocorreu. Eles persistem até que os eVars sejam substituídos por outros valores. Digamos que um visitante clique em um link da página de detalhes do produto da ID de produto &quot;sandal123&quot; na página de resultados da pesquisa por palavra-chave.  Em seguida, a ID de produto &quot;sandal123&quot; (se ainda não tiver sido vinculada) é vinculada a cada um dos valores contidos nas colunas post_evar ou aos valores de eVar que foram coletados da página anterior (resultados de pesquisa).

Há mais um item a ser reconsiderado na Sintaxe de variável de conversão. Os eventos de vinculação devem ser configurados para vincular um valor de eVar a um produto. Simplesmente definir um eVar de merchandising (em sua própria variável) com um produto (na variável products ) em uma solicitação de imagem do Adobe Analytics não vincula necessariamente o valor do eVar ao produto.  Em vez disso, a configuração Evento de vinculação de merchandising, que é definida no Gerenciador de conjunto de relatórios, determina os critérios que vinculam um valor de eVar a um produto

Como queremos vincular os valores de eVar do Método de descoberta de produto aos produtos sempre que uma interação de produto ocorrer (o que significa que um produto foi &quot;encontrado&quot;), é seguro presumir que as interações mais comuns &quot;produto encontrado&quot; que podem ocorrer são uma exibição de produto (quando os visitantes vão para uma página de detalhes do produto) ou uma adição ao carrinho (quando os visitantes adicionam um produto ao carrinho diretamente em uma página de método de descoberta de produto).

Assim, podemos escolher esses dois eventos (prodView, scAdd) como os eventos &quot;fundamentais&quot; de vinculação de merchandising.
Veja o que acontece quando um desses eventos de vinculação está contido em uma solicitação de imagem. Qualquer ID de produto contida na mesma solicitação (dentro da variável produtos ) e que não foi vinculada a uma eVar de merchandising será vinculada aos valores mais recentes transmitidos para a eVar de merchandising (colunas post_evar). Qualquer tentativa de vincular novamente esses produtos após essa vinculação original será ignorada quando a configuração Alocação (vinculação) for definida como &quot;Valor original (primeiro)&quot;.

### Configurações de prática recomendada

Veja a seguir as configurações de práticas recomendadas. Eles implementam facilmente o método de descoberta de produtos com os melhores resultados. A Adobe recomenda que os clientes configurem cada um de seus eVars de merchandising de método de descoberta de produto (em geral) da seguinte maneira:

* Merchandising ativado: Ativado
* Sintaxe [de merchandising]: sintaxe de variável de conversão
* Vinculação [de alocação]: valor original (primeiro)
* Expirar após: o tempo que um produto permanece em um carrinho antes de ser removido automaticamente (por exemplo, 14 dias, 30 dias etc.).  Se esse tempo não existir, Expirar após o evento &quot;compra&quot;
* Tipo: Texto
* Eventos de vinculação de merchandising: exibição do produto, adição ao carrinho e compra

## O que os eventos de vinculação realmente fazem?

Quando um evento de vinculação está contido na mesma chamada de servidor que a variável products, os valores de eVar de merchandising (usando a Sintaxe de variável de conversão) em sua coluna de publicação vinculam-se à variável products. Com base no exemplo anterior, suponha que uma chamada de servidor contenha os seguintes valores de eVar de Merchandising:

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Como explicado anteriormente, as eVars acima persistem além da ocorrência atual por meio de sua respectiva coluna post_evar. Portanto, servidores Adobe transformam as eVars acima no seguinte:

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Essas colunas de publicação são armazenadas no banco de dados da Adobe e persistem além da ocorrência atual na qual foram inicialmente definidas. Isso pressupõe que não ocorra expiração ou redefinição de variável.  Os servidores da Adobe têm esses valores post_evar &quot;disponíveis&quot; no momento em que processam quaisquer chamadas futuras do servidor que contenham a variável products e o evento compulsório.

O vínculo que ocorre é apenas entre esses valores post_evar e o conteúdo da variável products. O evento compulsório não é necessariamente &quot;vinculado&quot; às eVars ou à variável products. É o &quot;catalisador&quot; que instrui os servidores da Adobe a vincular os valores de post_evar aos produtos.

Suponha que, em uma ocorrência futura, as seguintes variáveis estejam definidas:

```js
s.products=";sandals123"
s.events="prodView";
```

Nas colunas post_evar, os servidores de processamento da Adobe veem essa ocorrência da seguinte maneira:

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Suponha que eVar1, eVar2, eVar3, eVar4 e eVar5 tenham sido configurados para usar `prodView` como um evento compulsório. Se qualquer um desses eVars não estiver configurado para usar prodView como um evento compulsório, o vínculo entre esse eVar (configurado incorretamente) e a variável products não ocorrerá.

O vínculo produz alguns resultados muito interessantes, que podem ser vistos no valor da coluna post_products. O vínculo transforma o código acima e define mais algumas colunas de publicação, da seguinte maneira:

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

O valor contido na coluna post_products pode ser familiar para você. Role para cima neste documento e compare esse valor de post_products com o valor de s.products, como mostrado em. Observe que a coluna post_products é definida usando a Sintaxe de variável do produto.

Isso significa que o Vínculo &quot;copia&quot; os valores do eVar da Sintaxe de variável de conversão para a variável products por meio da Sintaxe de produto. Essa ação de cópia ocorre somente quando a variável products e um evento compulsório (definido por meio da configuração de eVar) estão contidos na mesma solicitação. Nesse ponto, os valores contidos nas colunas post_eVar são vinculados ao produto. Esse Vínculo é representado por meio da Sintaxe do produto, conforme armazenado na coluna post_products.

## eVars de merchandising, a métrica Instâncias e a Atribuição

Quando uma eVar padrão é enviada em uma chamada de servidor do Analytics, o valor em sua coluna post_evar sempre obtém uma Instância atribuída a ela. As Instâncias representam o número de vezes que uma eVar foi definida igual a um valor específico em uma solicitação de imagem.

Por exemplo, suponha que `eVar10` seja uma eVar padrão com atribuição [!UICONTROL Último contato]. Se você definir `s.eVar10="hello world"` em qualquer página, o valor de &quot;olá mundo&quot; será transmitido para a coluna post_evar10 quando a Adobe processar a ocorrência. A métrica de instâncias é igual a &quot;1&quot; para cada configuração `eVar10` individual de `hello world`. Lembre-se de que uma instância nem sempre é registrada quando a coluna post_evar tem um valor. Em vez disso, a coluna post_evar determina qual valor obtém a instância quando uma instância é registrada.

As Instâncias de uma eVar de merchandising atribuem aos valores coletados pela eVar. Mas isso acontece apenas quando um produto que estava vinculado ao valor eVar de merchandising &quot;interagiu&quot; com ele ao mesmo tempo.

Por exemplo, definir `s.eVar1="Internal Keyword Search"` por si só não dá crédito à métrica da Instância para o valor de eVar1 de &quot;Pesquisa de palavra-chave interna&quot;. Uma instância é registrada nesse ponto. No entanto, a menos que um produto esteja vinculado a esse valor de &quot;Pesquisa de palavra-chave interna&quot; ao mesmo tempo em que `eVar1` é definido, a instância é atribuída ao intervalo Não especificado. Em outras palavras, o valor `eVar1` de &quot;Pesquisa de palavra-chave interna&quot; pode obter uma Instância. Mas isso acontece somente quando um produto vinculado ao valor de &quot;Pesquisa de palavra-chave interna&quot; é exibido na variável produtos na mesma solicitação de imagem.

Em resumo, sem configuração adicional, a métrica Instâncias pronta para uso de uma eVar de merchandising é menos que útil. Por sorte, Adobe liberado [Atribuição](/help/analyze/analysis-workspace/attribution/overview.md). Ele permite aplicar vários modelos de atribuição a qualquer métrica personalizada que o Adobe Analytics coleta. As métricas que aplicam esses modelos de atribuição não usam os valores contidos nas colunas post_evar ou os valores que estão vinculados a um produto específico. Em vez disso, essas métricas usam apenas os valores que são transmitidos por meio das próprias solicitações de imagem (ou valores capturados por meio das regras de processamento do Adobe Analytics). Você pode usar os recursos na Atribuição para obter uma métrica de instâncias atribuída com precisão para todas as eVars de merchandising que usam a Sintaxe de variável de conversão.

![Seleção de atribuição](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/assets/attribution-select.png)

Ao adicionar uma métrica de instância para um eVar de merchandising a um relatório, o modelo de Atribuição apropriado seria o modelo &quot;Último contato&quot;. Nesse caso, a configuração da Janela de pesquisa do modelo não importa. O motivo é que um modelo de atribuição de Último contato &quot;forçado&quot; sempre dá crédito de instância para cada valor individual transmitido por uma solicitação. Isso ocorre independentemente de as configurações de atribuição/vínculo reais da eVar serem definidas como &quot;Mais recente (último)&quot; a &quot;Valor original (primeiro)&quot;.
