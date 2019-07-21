---
description: Perguntas frequentes sobre o rastreamento de links no Activity Map.
seo-description: Perguntas frequentes sobre o rastreamento de links no Activity Map.
seo-title: Perguntas frequentes sobre o rastreamento de link
solution: Analytics
title: Perguntas frequentes sobre o rastreamento de link
topic: Activity Map
uuid: 10172073-b 98 b -4950-8397-67 a 18 b 37 b 3 b 4
translation-type: tm+mt
source-git-commit: d877f86dd5a05d0aa452ecebce47468ebf94cbb2

---


# Perguntas frequentes sobre o rastreamento de link

Perguntas frequentes sobre o rastreamento de links no Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be** **collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.

Veja a seguir alguns casos conhecidos nos quais dados de PII podem ser coletados usando o Rastreamento do Activity Map:

* `Mailto` links. Um link mailto é um tipo de link HTML que ativa o cliente de email padrão no computador para enviar um email.
* `User ID` links que podem aparecer no cabeçalho/rodapé de um site assim que o usuário fizer logon.
* Para instituições financeiras, o número da conta pode ser mostrado como um link. Clicar nele coletará o texto do link.
* Sites de instituições de saúde também podem ter dados de PII mostrados como links. Clicar nesses links coletará o texto do link e, portanto, coletará dados de PII.

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>P: Quando ocorre o rastreamento de links?</b> <p> </p> </td> 
   <td colname="col2"> R: A identificação de link e região do Activity Map ocorre quando os usuários clicam em uma página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: O que é rastreado por padrão?</b> <p> </p> </td> 
   <td colname="col2"> P: Se um evento de clique ocorrer em um elemento, esse terá que passar por algumas verificações para determinar se o AppMeasurement vai tratá-lo como um link. Essas são as verificações: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Isso é uma tag &lt;A&gt; ou &lt;AREA&gt; com uma propriedade HREF? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">Existe um atributo no clique que define uma variável s_objectID? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">Isso é uma tag INSERIR ou um botão ENVIAR com um valor ou texto filho? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">Isso é uma tag INSERIR com uma IMAGEM de tipo e uma propriedade src?  </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Isso é um &lt;Botão&gt;? </li> 
    </ul> <p>Se a resposta for <b>Sim</b> para qualquer uma das perguntas acima, então o elemento é tratado como um link e será rastreado. </p> <p>Importante: tags de botão com o atributo type="button" não são consideradas links por AppMeasurement. Considere remover "type='button'" nas tags de botão e, em vez disso, adicione role="button" ou submit="button". </p> <p>Importante: Uma tag de âncora com um href que começa com " #" é considerada uma localização de destino interna pelo appmeasurement, não um link (já que você não deixa a página.) Por padrão, o Activity Map não rastreia esses locais de meta internos. Rastreia apenas links que navegam pelo usuário para uma nova página.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: Como o Activity Map rastreia outros elementos visuais em HTML?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Com a função <code>s.tl()</code></b> <p>Se o clique ocorreu com uma invocação s.tl, então o Activity Map também receberá esse evento de clique e determinará se uma variável de cadeia de caracteres linkName foi encontrada. Durante a execução da s.tl, o linkName será definido como a ID do link no Activity Map.  O elemento clicado que originou a chamada s.tl() será utilizado para determinar a região. Exemplo: </p> <p> 
       <code>&lt; img &amp; amp; nbsp; onclick = "s. tl (true,' o ',' abc ')" &amp; amp; nbsp; src = "someimageurl. png"/&gt; </code>
  </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Com a variável <code>s_objectID</code></b> <p>Exemplo: </p> <p> 
       <code>&lt; img onclick = "s_ objectid =' abc '; " src = "someimageurl. png"/&gt; &lt; a href = "some-url.html" onclick = "s_ objectid =' abc '; " &gt; Texto do link aqui &lt;/a &gt; </code>
  </p> <p>Importante: observe que é necessário um ponto e vírgula (;) ao usar s_objectID no Activity Map. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: Você poderia fornecer alguns exemplos de links que serão rastreados?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>&lt; a &amp; amp; nbsp; href = "/home" &gt; Home &lt;/a &gt; </code>
  </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>&lt; input &amp; amp; nbsp; type = "enviar" &amp; amp; nbsp; value = "Enviar"/&gt; </code>
  </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>&lt; input &amp; amp; nbsp; type = "image" &amp; amp; nbsp; src = "submit-button. png"/&gt; </code>
  </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>&lt; p onclick = "var s_ objectid =' custom link id '; " &gt; &lt; span class = "title" &gt; Taxas de mercado atuais &lt;/span &gt; &lt; span class = "subtitle" &gt; 1.45 USD &lt;/span &gt; &lt;/p &gt; </code>
  </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>&lt; div onclick = "s. tl (true,' o ',' custom link id ')" &gt; &lt; span class = "title" &gt; Taxas de mercado atuais &lt;/span &gt; &lt; span class = "content" &gt; 1.45 USD &lt;/span &gt; &lt;/div &gt; </code>
  </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>P: Você poderia fornecer alguns exemplos de links que NÃO serão rastreados?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Motivo: a tag Âncora não tem um href válido 
      <code>&lt; a &amp; amp; nbsp; name = "inneranchor" &gt; Seção &amp; amp; nbsp; header &lt;/a &gt; </code>
  </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;p onclick="showPanel('market rates')"&gt;     &lt;span class="title"&gt;Current Market Rates&lt;/span&gt;&lt;span  class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;input type="radio" onclick="changeState(this)" name="group1" value="A"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="B"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: src property is missing a form input element 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

