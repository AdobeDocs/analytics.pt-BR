---
description: Essa seção destina-se aos Administradores do Adobe Analytics. Tem como foco os novos parâmetros de rastreamento de links e como eles garantem a singularidade do link e a consistência entre navegadores e dispositivos, além de melhorar a manipulação do reposicionamento do link em uma página.
seo-description: Essa seção destina-se aos Administradores do Adobe Analytics. Tem como foco os novos parâmetros de rastreamento de links e como eles garantem a singularidade do link e a consistência entre navegadores e dispositivos, além de melhorar a manipulação do reposicionamento do link em uma página.
seo-title: Metodologia de rastreamento de link
solution: Analytics
title: Metodologia de rastreamento de link
topic: Activity Map
uuid: 67864 bf 9-33 cd -46 fa -89 a 8-4 d 83 d 3 b 81152
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Metodologia de rastreamento de link

Essa seção destina-se aos Administradores do Adobe Analytics. Tem como foco os novos parâmetros de rastreamento de links e como eles garantem a singularidade do link e a consistência entre navegadores e dispositivos, além de melhorar a manipulação do reposicionamento do link em uma página.

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). Para obter mais informações sobre como o Activity Map pode coletar dados de PII, acesse [aqui](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6).

O Activity Map baseia seu rastreamento de links nessas duas IDs:

* ID primária: este é o parâmetro reconhecível do link.
* Região do link: este é um parâmetro secundário, que permite aos usuários especificar uma cadeia de caracteres que representa a área total do link na página ou região. Esse parâmetro pode ser gerado automaticamente se não for fornecido pelo usuário.

## ID primária {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se o HTML tiver uma função s_objectid, então a ID primária é padronizada para s_objectid. Caso contrário, os seguintes parâmetros são usados &#x200B;&#x200B;como ID primária (nesta ordem de prioridade):

* InnerText
* AltText
* Título
* Src
* Ação

## Usar o InnerText, em vez da Ação do link (URL) {#section_70C3573E22274522A8CC035BF18EC468}

A ação do link é a medida tomada pela página da Web quando o link é clicado, geralmente o URL que é visitado depois de clicar no link. Alguns dos problemas que você pode enfrentar ao usar a Ação do link são:

* ter dois ou mais links diferentes com a mesma ID
* a leitura do link
* um link com múltiplas ações (dependendo do dispositivo em que o link é exibido)

Como resultado, usamos o InnerText com essas vantagens, em vez da Ação do link (URL):

* É uma boa representação da identidade do link. A duplicação da ID primária é significativamente reduzida, pois não é comum ter vários links com o mesmo texto.
* Isso garante a consistência da ID primária em todos os tipos de dispositivos e navegadores.
* Ela não é afetada por um reposicionamento de link na página.
* Melhora a leitura, assim os usuários podem iniciar a análise dos relatórios de Rastreamento do link fora do Activity Map.

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Este novo atributo permite aos usuários especificar uma cadeia de caracteres que representa a região da página onde o link está localizado.

Por exemplo, para um link “Fale Conosco”, que está localizado na seção Menu da página da Web, o usuário pode querer passar um parâmetro de região “Menu”. Da mesma forma, para um link “Fale Conosco” localizado no rodapé da página da Web, o parâmetro de região pode ser definido como “Rodapé”.

O valor da Região do link não está definido no próprio link, mas em um elemento HTML acima da árvore DOM HTML que engloba a região.
O uso da Região do link tem os seguintes benefícios:

* Ajuda a diferenciar os links com a mesma ID primária.
* As tendências em uma região são menos afetadas pelo aspecto dinâmico da página da Web.
* Os usuários podem ver os links com melhor desempenho dentro de uma região. Com Região como uma âncora, podemos mostrar as sobreposições de links que não estão visíveis atualmente na página (Ajax, Direcionamento).
* A Região pode substituir páginas, já que uma determinada região pode ser usada em várias páginas da Web. Ela ajuda a responder a perguntas como: “A região de Ofertas de produtos tem um melhor desempenho na Página de aterrissagem para mulheres ou para homens?”
* A Região é uma dimensão relevante para analisar as páginas da Web altamente dinâmicas. Isso ocorre porque ela remove o ruído, devido aos links em mudança contínua: uma Região de “Notícias recentes” na página de aterrissagem CNN pode conter vários links dinâmicos. Mas a região vai estar sempre lá. Dessa forma, pode ser interessante direcionar a nível de Região durante muitos dias.

**Rastreamento de região personalizada**

É possível personalizar o parâmetro Região para um link (o padrão é uma ID do link): um conjunto de tags definido como “ID” vai usar todos os elementos HTML que tenham um parâmetro “id” como uma Região. Assim, definir a tag de Região para “id” provavelmente retornará várias regiões distintas (assim como existem diferentes “IDs” na página). Como alternativa, se você quiser uma implementação mais personalizada, é possível definir a tag Região para algo mais específico, como “region_id”.

Abaixo, é possível observar alguns exemplos de HTML que usam o atributo padrão de ID da região, a “id”.

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

Se desejar, você pode marcar elementos com um identificador de cadeia de caracteres arbitrário, neste caso “lpos”, e depois adicionar os atributos com o nome “lpos”.

```
s.ActivityMap.regionIDAttribute="lpos"; 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## Configuration variables {#section_634197EACD404AC086DF9A03B813C8C3}

Observe que essas variáveis &#x200B;&#x200B;estão listadas apenas para fins de referência. O Activity Map deve ser configurado adequadamente para instalação, mas é possível personalizar a sua implementação usando essas variáveis.

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da variável </th> 
   <th colname="col2" class="entry"> Exemplo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s. activitymap. regionidattribute </td> 
   <td colname="col2"> Padrões para o parâmetro “id”. Você pode definir para outro parâmetro. </td> 
   <td colname="col3"> A cadeia de caracteres que identifica o atributo da tag para usar como ID da região de algum elemento ascendente (pais, avós, ...) de s.linkObject, ou seja, <b>o elemento que foi clicado</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. link </td> 
   <td colname="col2"> 
    <code>// usar apenas os atributos "título" de uma função de tags (clickedelement) {var linkid; if (clickedelement &amp; &amp; clickedelement. tagname. touppercase () = = =' A ') {linkid = clickedelement. getattribute (' title '); } return linkid; }} </code>
  </td> 
   <td colname="col3"> A função que recebe o HTMLElement clicado e deve retornar um valor de cadeia de caracteres que representa <b>o link que foi clicado</b>. <p>Se o valor de retorno for falso (nulo, indefinido, cadeia de caracteres vazia, 0), nenhum link será rastreado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. region </td> 
   <td colname="col2"> 
    <code>// usar apenas a versão em minúsculas do nome da tag concatenada com o primeiro classname como a função região (clickedelement) {var regionid, classname; while (clickedelement &amp; &amp; clickedelement = clickedelement. parentnode)) {regionid = clickedelement. tagname; if (regionid) {return regionid. tolowercase (); }}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}}} </code>
  </td> 
   <td colname="col3"> A função que recebe o HTMLElement clicado e deve retornar um valor de cadeia de caracteres que representa <b>a região onde o link foi encontrado, quando clicado</b>. <p>Se o valor de retorno for falso (nulo, indefinido, cadeia de caracteres vazia, 0), nenhum link será rastreado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>// Links de exclusão marcados com uma classe CSS de linkexcluída especial &lt; estilo &gt;. linkexcluded {display: block; altura: 1 px; left: -9999 px; overflow: oculto; position: absolute; largura: 1 px; } &lt;/style &gt; &lt; a href = "next-page.html" &gt; Link é rastreado porque o link não tem texto oculto correspondente ao filtro.&lt;/a &gt; &lt; a href = "next-page.html" &gt; Link não rastreado porque s. activitymap. linkexclusions está definido e este link tem texto oculto correspondente ao filtro. &lt; span class = "linkexcluded" &gt; delete-link 1 &lt;/span &gt; &lt;/a &gt; &lt; a href = "next-page.html" &gt; Link não rastreado porque s. activitymap. linkexclusions está definido e este link tem texto oculto correspondente ao filtro.  &lt;span class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Uma sequência de caracteres que recebe uma lista de sequências de caracteres separadas por vírgula para pesquisa no texto do link. Caso encontrado, o link deixará de ser rastreado pelo Activity Map. Caso não esteja definido, nenhuma tentativa foi feita para interromper o rastreamento do link no Activity Map.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>// Excluir regiões na página de seus links que estão sendo rastreáveis por activitymap &lt; div id = "links-incluídos" &gt; &lt; a href = "next-page.html" &gt; Link é rastreado porque s. activitymap. regionexclusions está definido, mas não corresponde ao filtro.&lt;/a &gt; &lt;/div &gt; &lt; div id = "links-excluídos" &gt; &lt; a href = "next-page.html" &gt; Link não rastreado porque s. activitymap. regionexclusions está definido e este link corresponde ao filtro.&lt;/a&gt; &lt;/div&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.regionExclusions = 'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Uma sequência de caracteres que recebe uma lista de sequências de caracteres separadas por vírgula para pesquisa no texto da região. Caso encontrado, o link deixará de ser rastreado pelo Activity Map. Caso não esteja definido, nenhuma tentativa foi feita para interromper o rastreamento do link no Activity Map.  </p> </td> 
  </tr> 
 </tbody> 
</table>
