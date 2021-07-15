---
title: eVars de merchandising e métodos de descoberta de produtos
description: Um aprofundamento dos conceitos por trás das eVars de comercialização e como elas processam e alocam dados.
source-git-commit: e7bfb56b63a9134728360c91f3c835da1952fa5a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# eVars de merchandising e métodos de descoberta de produtos

Este documento explica os conceitos por trás das eVars de comercialização, que processam e alocam dados de forma diferente das eVars padrão. Também explica como as eVars de merchandising estão relacionadas aos Métodos de descoberta de produtos.

Embora a maioria dos sites de varejo tenha muitas maneiras de encontrar produtos, o Adobe considera que os seguintes são os métodos fundamentais para encontrar produtos que cada cliente de varejo deve rastrear no Adobe Analytics:

* Palavras-chave de pesquisa interna
* Códigos de rastreamento de campanha interna
* Categorias de merchandising/navegação
* Links de venda cruzada

Para os fins deste documento, vamos mapear algumas eVars para as soluções da seguinte maneira:

* eVar2: Palavras-chave de pesquisa interna
* eVar3: Códigos de rastreamento de campanha interna
* eVar4: Categorias de merchandising/navegação
* eVar5: Links de venda cruzada

Podemos usar um eVar adicional para medir o desempenho de todos os métodos de busca de produtos em relação uns aos outros. Além dos métodos de descoberta descritos acima, o eVar incluirá outros métodos de descoberta, como links para páginas de detalhes do produto de sites externos, em sua comparação.

* eVar1: Métodos para encontrar produtos

Você não deve configurar nenhuma dessas variáveis para serem eVars padrão, mas deve configurá-las para serem eVars de merchandising.  Usar eVars de merchandising permite alocar qualquer atividade bem-sucedida nos valores capturados pelas eVars em um nível *por produto* em vez de um nível *por visita/por pedido*. Vou esclarecer a diferença entre a atribuição por produto e por encomenda ao longo do resto deste documento.

Para demonstrar como essas variáveis devem ser definidas, começarei com um exemplo em que um visitante decide que usará as &quot;sandals&quot; internas de pesquisa de palavra-chave para encontrar um produto no site.  Na página de resultados da pesquisa por palavra-chave, é necessário capturar dados em pelo menos duas eVars:

* `eVar2` será igual à palavra-chave que foi usada na pesquisa (&quot;sandals&quot;)
* `eVar1` será igual ao método de descoberta de produto usado (&quot;pesquisa interna de palavra-chave&quot;).

Quando você define essas duas variáveis iguais a esses valores específicos, você sabe que o visitante está usando o termo de pesquisa interno de palavra-chave &quot;sandals&quot; para localizar um produto.
Ao mesmo tempo, você sabe que o visitante não está usando os outros métodos de busca de produtos para localizar produtos (por exemplo, o visitante não está navegando pelas categorias de produtos exatamente ao mesmo tempo em que está realizando uma pesquisa por palavra-chave). Para garantir que a alocação adequada por produto ocorra, esses métodos não utilizados não devem ser creditados por localizar um produto que foi encontrado por meio de uma pesquisa interna de palavra-chave.  Portanto, é necessário inserir lógica no código (por exemplo, AppMeasurement, AEP Web SDK etc.) que definirá automaticamente as eVars associadas a esses outros métodos de descoberta como um valor de &quot;método que não seja de descoberta&quot;.

Por exemplo, quando um usuário pesquisa produtos usando a palavra-chave &quot;sandals&quot;, a lógica do código do Analytics deve definir as variáveis iguais às seguintes na página de resultados da pesquisa interna por palavra-chave:

* eVar2=&quot;sandals&quot;: a palavra-chave &quot;sandals&quot; foi usada na pesquisa interna da palavra-chave
* eVar1=&quot;pesquisa interna de palavra-chave&quot;: o método de descoberta &quot;pesquisa interna de palavra-chave&quot; foi usado
* eVar3=&quot;campanha não interna&quot;: uma campanha interna não foi usada para acessar a página de resultados da pesquisa
* eVar4=&quot;não navegado&quot;: uma categoria de navegação não foi acessada na página de resultados da pesquisa
* eVar5=&quot;venda não cruzada&quot;: um link de venda cruzada não foi clicado na página de resultados da pesquisa

