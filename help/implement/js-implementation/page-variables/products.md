---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# products

A variável é usada para rastrear produtos e categorias de produto, assim como quantidade e preço da compra. Ela geralmente é definida em conjunto com um evento de carrinho ou um evento.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>Em janeiro de 2016, atualizamos a lógica que define o evento *`prodView`* automaticamente, o que acontece quando há *`product`*, mas não há *`event`*. Esta atualização pode causar um aumento nos eventos no *`prodView`*. *`prodViews`* só aumentarão quando:
>
>1. A variável de eventos não contém nada além de um evento não reconhecido, como *`shoppingCart`* ou *`cart`*, que não são eventos válidos.
   >
   >
1. A variável *`products`* não está vazia.
>
>
Um possível efeito colateral é que eVars de merchandising acionadas por eventos *`prodView`* podem ser associadas a um *`product`* vazio, mas somente se *`product list`* contiver apenas um produto inválido (como um ponto e vírgula sem produto listado).

A variável *`products`* rastreia a forma como os usuários interagem com os produtos do site. Por exemplo, a variável products pode rastrear quantas vezes um produto é exibido, adicionado ao carrinho, passado pelo checkout e adquirido. Ela também pode rastrear a eficácia relativa de categorias de comercialização de seu site. Os cenários abaixo são comuns para uso da variável products.

A variável *`products`* deve ser sempre definida juntamente com um evento bem-sucedido. 

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>A string " <span class="wintitle"> products </span>" tem um tamanho máximo de 64k. </p> </td> 
   <td> products </td> 
   <td> Produtos <p>Categorias (opcional) </p> <p>Receita (opcional) </p> <p>Unidades (opcional) </p> <p>Eventos personalizados (opcional) </p> <p>eVars (opcional) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxe** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definição |
|---|---|
| Categoria | Contém a categoria associada do produto. Na versão 15, os produtos podem ser associados à várias categorias. Isso cria a limitação presente na versão 14. Se você não gravava as categorias do produto, recomendamos popular a área com os conjuntos de relatórios presentes na versão 15. |
| Produto | (obrigatório) O identificador usado para rastrear um produto. O identificador é usado para preencher o relatório [!UICONTROL Produtos]. Não deixe de usar o mesmo identificador por meio do processo de checkout. |
| Quantidade | O número de unidades compradas. Este campo deve ser definido com um evento de [!UICONTROL compra] a ser gravado. |
| Preço | Refere-se ao custo total de quantidade adquirida (unidades vs preço unitário), e não o valor individual. Este campo deve ser definido com um evento de [!UICONTROL compra] a ser gravado. |
| Eventos | eventos de moeda associados ao produto em questão. Consulte [eventos de moeda do produto em questão](/help/implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) e [eventos de moeda do pedido](/help/implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0). |
| eVars | Valores eVar de merchandising associados a um produto específico. Consulte [Variáveis de merchandising](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

As valores inclusos na *`products`* variável são baseados no tipo de evento que está sendo gravado. O delimitador (;) de categoria/produto é necessário como espaço reservado na omissão de Categoria. O uso de outros delimitadores só é necessário para diferenciar o parâmetro que está sendo incluído, conforme exibido nos exemplos desta página.

**Configuração de products com eventos que não são de compra** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

A variável *`products`* deve ser definida juntamente com um evento bem-sucedido.

**Configuração de products com um evento de compra** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

O evento *`purchase`* deve ser definido na confirmação final ("Obrigado.") página do processo do pedido. O nome do produto, a categoria, quantidade e o preço são capturados na variável *`products`*. Embora a variável *`purchaseID`* não seja obrigatória, ela é extremamente recomendável para evitar pedidos duplicados.

**Evento de moeda do produto em questão** {#section_F814DF053C0D463A97DA039E6323720C}

Se um evento de moeda receber um valor na variável *`products`*, em vez da variável de eventos, ele se aplica somente a esse valor. Isso é útil para rastrear descontos em produtos, envio de produtos e outros valores similares. Por exemplo, se você configurou o evento 1 para rastrear o envio do produto, um produto com uma carga de envio de "4,50" deverá ser exibido da seguinte maneira:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

Neste exemplo, o valor 4,50 está associado diretamente ao produto "Tênis de corrida". Se você adicionar evento 1 ao relatório de produtos, verá "4,50" listado para o item de linha "Tênis de corrida". Assim como o Preço, este valor deve refletir a soma total para a quantidade listada. Caso tenha 2 itens com uma taxa de envio de 4,50 cada, o evento 1 deverá ser "9,00".

**eventos de moeda do pedido** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Se um evento de moeda receber um valor na lista de eventos, em vez da variável *`products`*, ele se aplica a todos os produtos na variável *`products`*. Isso serve para rastrear descontos, frete e valores similares de todo o pedido sem alterar o preço do produto ou rastreando na lista de produtos separadamente.

evento 10 para incluir os descontos de todos os produtos, poderá aparecer uma compra com um desconto de 10% semelhante à compra a seguir:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Nos relatórios de moeda, o total do relatório representa o total do evento com duplicação eliminada (neste exemplo, a quantidade total de descontos durante o período do relatório) e não a soma dos valores do evento para cada produto. Por exemplo, você verá "9,95" listado tanto para "Tênis de corrida" como para "Meias de corrida", e o total ainda será de "9,95".

> [!NOTE] se um valor para o mesmo Evento numérico/de moeda for especificado na variável *`products`* e na variável *`events`*, o valor do evento *`events`* será usado.

**Armadilhas, dúvidas e dicas** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* A variável *`products`* deve ser sempre definida juntamente com um evento [!UICONTROL bem-sucedido] (eventos). Se nenhum evento [!UICONTROL bem-sucedido] for especificado, o evento padrão será [!UICONTROL prodView].

* Retire todas as vírgulas e pontos-e-vírgulas dos nomes de produto e categoria antes de preencher os produtos.
* Retire todos os caracteres HTML (símbolos registrados, marcas comerciais e assim por diante).
* Retire símbolos de moedas ($) do preço.

**Exemplos** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

