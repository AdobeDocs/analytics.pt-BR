---
description: Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).
keywords: Analytics Implementation
subtopic: Redirects
title: Redirecionamentos e aliases
topic: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Redirecionamentos e aliases

Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).

## Redirecionamentos e aliases {#concept_F4F1D53D473947FE8554897332545763}

Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).

Como os redirecionamentos não necessitam de qualquer interação com o usuário, eles geralmente são executados sem que o usuário jamais perceba. A única coisa que indica que um redirecionamento ocorreu é a barra de endereços do navegador. A barra de endereços exibe uma URL diferente do link que o navegador solicitou inicialmente.

Embora existam apenas dois tipos de redirecionamentos, eles podem ser implementados de várias maneiras. Por exemplo, redirecionamentos do lado do cliente podem ocorrer por que a página da Web para a qual um usuário apontou seu navegador contém script ou código HTML especial que redireciona o navegador para outra URL. Redirecionamentos do lado do servidor podem ocorrer porque a página contém script do lado do servidor ou porque o servidor Web foi configurado para apontar o usuário para outra URL.

## Analytics e redirecionamentos {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

O[!DNL Analytics] reúne alguns de seus dados por meio do navegador e depende de determinadas propriedades dele. Duas dessas propriedades, a &quot;URL de referência&quot; (ou &quot;referenciador&quot;) e a &quot;URL atual&quot; podem ser alteradas por um redirecionamento do lado do servidor. Como o navegador sabe que uma URL foi solicitada, mas uma URL diferente foi devolvida, ele limpa a URL de referência. O resultado é que a URL de referência fica em branco, e o [!DNL Analytics] pode relatar que não existia referenciador para a página.

## Exemplo: navegação sem redirecionamentos  {#section_5C835A4D665A4625A23333C2C21F152D}

Considere a seguinte situação hipotética na qual o usuário não encontra um redirecionamento:

1. O usuário aponta seu navegador para `www.google.com`, digita &quot;discount airline tickets&quot; no campo de pesquisa e clica no botão **[!UICONTROL Pesquisar]**.
1. O navegador exibe os resultados da pesquisa, incluindo um link para seu site, [!DNL https://www.example.com/]. Após exibir os resultados da pesquisa, barra de endereços do navegador exibe os termos de pesquisa que o usuário inseriu no campo de pesquisa ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Observe que os termos de pesquisa foram incluídos nos parâmetros da sequência de consulta do URL após `https://www.google.com/search?`.
1. O usuário clica no link de seu site hipotético [!DNL https://www.example.com/]. Quando o usuário clica nesse link e chega ao site [!DNL example.com], o [!DNL Analytics] usa o JavaScript para coletar o URL de referência (`https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) e o URL atual (`https://www.example.com/`).
1. O [!DNL Analytics] relata as informações coletadas durante essa interação em diversos relatórios, como [!UICONTROL Domínios de referência], [!UICONTROL Mecanismos de pesquisa] e [!DNL Search Keywords].

## Exemplo: navegação com redirecionamentos {#section_921DDD32932847848C4A901ACEF06248}

Redirecionamentos podem fazer com que o navegador apague a URL de referência verdadeira. Considere a seguinte situação

1. O usuário aponta seu navegador para `https://www.google.com`, digita *discount airline tickets* no campo de pesquisa e clica no botão **[!UICONTROL Pesquisar]**.
1. A barra de endereços da janela do navegador exibe os termos de pesquisa que o usuário digitou no campo de pesquisa `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Observe que os termos de pesquisa foram incluídos nos parâmetros da sequência de consulta do URL após `https://www.google.com/search?`. O navegador também exibe uma página que contém os resultados da pesquisa, incluindo um link para um de seus nomes de domínio, [!DNL https://www.flytohawaiiforfree.com/]. Esse domínio *personalizado* é configurado para direcionar o usuário para `https://www.example.com/`.
1. O usuário clica no link `https://www.flytohawaiiforfree.com/` e é redirecionado pelo servidor para o site principal, `https://www.example.com`. Quando o redirecionamento acontece, os dados que são importantes para a coleta de dados do [!DNL Analytics] são perdidos, porque o navegador apaga a URL de referência. Assim, as informações da pesquisa original usadas nos relatórios do [!DNL Analytics] (por exemplo, [!UICONTROL Domínios de Referência], [!UICONTROL Mecanismos de Busca] e [!UICONTROL Palavras-chave de Pesquisa]) são perdidas.

## Implementar redirecionamentos {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Para capturar dados do [!DNL Analytics] por meio de redirecionamentos, quatro pequenas alterações precisam ser feitas no código que cria o redirecionamento e [!DNL AppMeasurement] o arquivo do JavaScript.

<!-- 

redirects_implement.xml

 -->

Completando as etapas a seguir, as informações que o referenciador original passar para seu site (por exemplo, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` na situação acima) serão conservadas:

## Configurar código JavaScript de substituição do referenciador {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

O trecho de código abaixo mostra duas variáveis do JavaScript, *`s_referrer`*e*`s_pageURL`*. Este código está localizado na página de aterrissagem final do redirecionamento.

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>Definir *`s.referrer`*somente uma vez na página. Definir mais de uma vez com cada chamada de rastreamento ou com cada clique de link rastreado causa a contagem dupla do referenciador e dimensões relacionadas, como ferramentas de pesquisa e palavras-chave.

## Redireciona usando getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

Embora o [!UICONTROL getQueryParam] seja uma maneira fácil de preencher as variáveis do [!DNL Analytics] com valores de string de consulta, ele deve ser implementado em conexão com uma variável temporária para que os referenciadores legítimos não sejam substituídos quando a string de consulta estiver vazia. A melhor maneira de usar [!UICONTROL getQueryParam] é na conexão com o plug-in [!UICONTROL getValue], conforme detalhado no seguinte pseudo-código.

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## Modificar o mecanismo de redirecionamento {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Como o navegador tira a URL de referência, você deve configurar o mecanismo que manipula o redirecionamento (por exemplo, o servidor Web, o código do lado do servidor, o código do lado do cliente) para repassar as informações originais do referenciador. Caso você também queira gravar a URL do link alias, ela também deve ser repassada para a página de aterrissagem final. Use a variável *`s_pageURL`*para substituir a URL atual.

Como há muitas maneiras de implementar um redirecionamento, você precisará verificar com seu grupo de operações Web ou parceiro de publicidade on-line para identificar os mecanismos específicos que executam redirecionamentos em seu site.

## Capturar o referenciador original {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

Normalmente, o [!DNL Analytics] obtém o URL de referência pela propriedade [!UICONTROL document.referrer] do navegador, e o URL atual da propriedade [!UICONTROL document.location]. Ao transmitir os valores para as variáveis *`referrer`*e*`pageURL`*, é possível substituir o processamento padrão. Passando um valor para a variável do referenciador, você diz ao [!DNL Analytics] para ignorar as informações do referenciador na propriedade [!UICONTROL document.referrer] e usar um valor alternativo que você definir.

Portanto, a versão final da página inicial precisaria conter o seguinte código para corrigir os problemas apresentados na situação de &quot;discount airline tickets&quot;.

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Verificar o referenciador com o Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Faça um teste para verificar se o referenciador, o URL de origem (*`s_server`*) e as variáveis de campanha estão sendo capturados.

Essas variáveis serão representadas como os parâmetros a seguir no [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL ou Valor da String de Consulta</b> </th> 
   <th class="entry"> <b>Valor como mostrado no DigitalPulse Debugger</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Referenciador Original </p> </td> 
   <td> <p> <span class="filepath">https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Ddiscount%2Bairline%2Btickets</span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=discount+airline+tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL da página </p> </td> 
   <td> <p> <span class="filepath">https://www.flytohawaiiforfree.com</span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>Esse valor será exibido no DigitalPulse Debugger, se a variável <span class="varname"> pageURL </span> for usada. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL da página de aterrissagem final </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com </span> </p> </td> 
   <td> <p>Esse valor NÃO será exibido no DigitalPulse Debugger, se a variável <span class="varname"> pageURL </span> for usada. </p> </td> 
  </tr> 
 </tbody> 
</table>

O texto que o depurador exibe deve corresponder ao seguinte exemplo:

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

Depois de verificar se o Adobe [!UICONTROL Debugger] exibe essas variáveis, é sempre útil confirmar se os termos de pesquisa e o domínio referenciador original (antes do redirecionamento) estão registrando o tráfego nos relatórios.
