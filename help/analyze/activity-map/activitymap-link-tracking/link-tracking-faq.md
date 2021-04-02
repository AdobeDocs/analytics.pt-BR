---
description: Perguntas frequentes sobre o rastreamento de links no Activity Map.
title: Perguntas frequentes sobre o Rastreamento de links
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 69%

---


# Perguntas frequentes sobre o Rastreamento de links

Perguntas frequentes sobre o rastreamento de links no Activity Map.

>[!CAUTION]
>
>Ao ativar o rastreamento do Activity Map, **você poderá coletar dados de informações pessoalmente identificáveis (PII).** Tais dados podem ser usados isoladamente ou junto a outras informações para identificar, contactar ou localizar uma pessoa, ou para identificar um indivíduo em um contexto.

Veja a seguir alguns casos conhecidos nos quais dados de PII podem ser coletados usando o Rastreamento do Activity Map:

* `Mailto` links. Um link mailto é um tipo de link HTML que ativa o cliente de email padrão no computador para enviar um email.
* `User ID` links que podem ser exibidos no cabeçalho/rodapé de um site depois que o usuário fizer logon.
* Para instituições financeiras, o número da conta pode ser mostrado como um link. Clicar nele coletará o texto do link.
* Sites de instituições de saúde também podem ter dados de PII mostrados como links. Clicar nesses links coletará o texto do link e, portanto, coletará dados de PII.

<table id="table_0951EAC617344156BAE43000CCD838AF">
 <tbody>
  <tr>
   <td colname="col1"> <b>P: Quando ocorre o rastreamento de links?</b> </td>
   <td colname="col2"> R: A identificação de link e região do Activity Map ocorre quando os usuários clicam em uma página. </td>
  </tr>
  <tr>
   <td colname="col1"> <b>P: O que é rastreado por padrão?</b> </td>
   <td colname="col2"> P: Se um evento de clique ocorrer em um elemento, esse terá que passar por algumas verificações para determinar se o AppMeasurement vai tratá-lo como um link. Essas são as verificações:
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0">
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Isso é uma tag <code>&lt;A&gt;</code> ou <code>&lt;AREA&gt;</code> com uma propriedade <code>"href"</code>? </li>
     <li id="li_77828D24D54343E5B9A1FF7345221781">Existe um atributo <code>"onclick"</code> que define uma variável <code>s_objectID</code>? </li>
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">Isso é uma tag <code>&lt;INPUT&gt;</code> ou um botão <code>&lt;SUBMIT&gt;</code> com um valor ou texto filho? </li>
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">Isso é uma tag <code>&lt;INPUT&gt;</code> com o tipo <code>&lt;IMAGE&gt;</code> e uma propriedade <code>"src"</code>? </li>
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Isso é um <code>&lt;BUTTON&gt;</code>? </li>
    </ul>
    Se a resposta for <b>Sim</b> para qualquer uma das perguntas acima, então o elemento é tratado como um link e será rastreado. <br/>
     <br/>
    Importante: Tags de botão com o atributo não  <code>type="button"</code> são consideradas links por AppMeasurement. Considere remover <code>type="button"</code> nas tags de botão e, em vez disso, adicione <code>role="button"</code> ou <code>submit="button"</code>. <br/>
     <br/>
    Importante: Uma âncora de tags com um  <code>"href"</code> que começa com  <code>"#"</code> é considerada um local de destino interno pelo AppMeasurement, não um link (já que você não sai da página). Por padrão, o Activity Map não rastreia esses locais de destino internos. Ele rastreia somente links que levam o usuário a uma nova página. </td> 
  </tr>
  <tr>
   <td colname="col1"> <b>P: Como o Activity Map rastreia outros elementos visuais em HTML?</b> </td>
   <td colname="col2">
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5">
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Com a <code>s.tl()</code> função</b> <br/>
       <br/>
      Se o clique ocorreu com uma invocação , então o Activity Map também receberá esse evento de clique e determinará se uma variável de cadeia de caracteres foi encontrada. <code>s.tl()</code><code>linkName</code> Durante a execução de <code>s.tl()</code>, <code>linkName</code> será definido como ID do link Activity Map. O elemento clicado que originou a chamada <code>s.tl()</code> será usado para determinar a região. <br/>
       <br/>
      Exemplo:  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s.tl(true,'o','abc')"&nbsp;src="someimageurl.png"/&gt;</code><br/>
       
     </li>
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Por meio de  <code>s_objectID</code> </b> <br/>
       <br/>
      variableExample:  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt;</code><br/>
      <code>&lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;</code><br/>
      <code>&nbsp;&nbsp;Link&nbsp;Text&nbsp;Here</code><br/>
      <code>&lt;/a&gt;</code> <br/>
       <br/>
      Importante: Observe que é necessário um ponto e vírgula (<code>;</code>) ao usar  <code>s_objectID</code> no Activity Map.
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>P: Você poderia fornecer alguns exemplos de links que serão rastreados?</b> </td>
   <td colname="col2">
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA">
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0">
      <code>&lt;a&nbsp;href="/home"&gt;Home&lt;/a&gt;</code>
     </li>
     <li id="li_76F3DB36ED734132A2386871E6EB4929">
      <code>&lt;input&nbsp;type="submit"&nbsp;value="Submit"/&gt;</code>
     </li>
     <li id="li_10CF9EDA224645169E7CDF74956DB98B">
      <code>&lt;input&nbsp;type="image"&nbsp;src="submit-button.png"/&gt;</code>
     </li>
     <li id="li_9FA171D7F49547E798DE21869F73A402">
      <code>&lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code>
     </li>
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF">
      <code>&lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/div&gt;</code>
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>P: Você poderia fornecer alguns exemplos de links que NÃO serão rastreados?</b> </td>
   <td colname="col2">
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547">
     <li id="li_99372060646B43EF94C13A9C682CE693">Motivo: A tag âncora não tem um <code>"href"</code> <br/> válido
       <br/>
      <code>&lt;a&nbsp;name="innerAnchor"&gt;Section&nbsp;header&lt;/a&gt;</code><br/>
       
     </li>
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Motivo: a função <code>s_ObjectID</code> e a <code>s.tl()</code> não estão presentes <br/>
       <br/>
      <code>&lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code><br/>
       
     </li>
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Motivo: a função <code>s_ObjectID</code> e a <code>s.tl()</code> não estão presentes <br/>
       <br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;</code><br/>
       
     </li>
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Motivo: A propriedade <code>"src"</code> não tem um elemento de formulário <code>input</code> <br/>
       <br/>
      <code>&lt;input&nbsp;type="image"/&gt;</code><br/>
       
     </li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>
