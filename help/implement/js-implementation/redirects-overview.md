---
description: Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).
keywords: Implementação do Analytics
seo-description: Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).
seo-title: Redirecionamentos e aliases
solution: Analytics
subtopic: Redirecionamentos
title: Redirecionamentos e aliases
topic: Desenvolvedor e implementação
uuid: 11 f 9 ad 7 a -5 c 45-410 f -86 dd-b 7 d 2 cec 2 aae 3
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Redirecionamentos e aliases

Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).

## Redirects and aliases {#concept_F4F1D53D473947FE8554897332545763}

Os redirecionamentos apontam o navegador para um novo local sem interação com usuário. Eles são executados tanto no navegador Web (redirecionamento do lado do cliente) como no servidor Web (redirecionamento do lado do servidor).

Como os redirecionamentos não necessitam de qualquer interação com o usuário, eles geralmente são executados sem que o usuário jamais perceba. A única coisa que indica que um redirecionamento ocorreu é a barra de endereços do navegador. A barra de endereços exibe uma URL diferente do link que o navegador solicitou inicialmente.

Embora existam apenas dois tipos de redirecionamentos, eles podem ser implementados de várias maneiras. Por exemplo, redirecionamentos do lado do cliente podem ocorrer por que a página da Web para a qual um usuário apontou seu navegador contém script ou código HTML especial que redireciona o navegador para outra URL. Redirecionamentos do lado do servidor podem ocorrer porque a página contém script do lado do servidor ou porque o servidor Web foi configurado para apontar o usuário para outra URL.

## Analytics and redirects {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

O [!DNL Analytics] reúne alguns de seus dados por meio do navegador e depende de determinadas propriedades dele. Duas dessas propriedades, a "URL de referência" (ou "referenciador") e a "URL atual" podem ser alteradas por um redirecionamento do lado do servidor. Como o navegador sabe que uma URL foi solicitada, mas uma URL diferente foi devolvida, ele limpa a URL de referência. O resultado é que a URL de referência fica em branco, e o [!DNL Analytics] pode relatar que não existia referenciador para a página.

<!-- 

redirects_sc.xml

 -->

Os exemplos a seguir ilustram como a navegação é afetada com e sem os redirecionamentos:

* [Exemplo: navegação sem redirecionamentos](../../implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [Exemplo: navegação com redirecionamentos](../../implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## Exemplo: navegação sem redirecionamentos {#section_5C835A4D665A4625A23333C2C21F152D}

Considere a seguinte situação hipotética na qual o usuário não encontra um redirecionamento:

1. O usuário aponta seu navegador para `www.google.com`**, digita "discount airline tickets" no campo de pesquisa e clica no botão[!UICONTROL Pesquisar].**
1. O navegador exibe os resultados da pesquisa, incluindo um link para seu site, [!DNL https://www.flywithus.com/]. After displaying the search results, the browser's address bar displays the search terms that the user entered in the search field ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Observe que os termos de pesquisa foram incluídos nos parâmetros da sequência de consulta do URL após `https://www.google.com/search?`.
1. O usuário clica no link de seu site hipotético [!DNL https://www.flywithus.com/]. When the user clicks this link and lands on the [!DNL flywithus.com] website, [!DNL Analytics] uses JavaScript to collect the referring URL ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) as well as the current URL ( `https://www.flywithus.com/`).
1. [!DNL Analytics] relata as informações coletadas durante esta interação em vários relatórios, como Domínios [!UICONTROL de referência], [!UICONTROL Mecanismos de pesquisa]e [!DNL Search Keywords].

## Exemplo: navegação com redirecionamentos {#section_921DDD32932847848C4A901ACEF06248}

Redirecionamentos podem fazer com que o navegador apague a URL de referência verdadeira. Considere a seguinte situação

1. User points his or her browser to `https://www.google.com`, and types, *discount airline tickets* into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser window's address bar displays the search terms that the user typed into the search field `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Observe que os termos de pesquisa foram incluídos nos parâmetros da sequência de consulta do URL após `https://www.google.com/search?`. O navegador também exibe uma página que contém os resultados da pesquisa, incluindo um link para um de seus nomes de domínio, [!DNL https://www.flytohawaiiforfree.com/]. Esse domínio *personalizado* é configurado para direcionar o usuário para `https://www.flywithus.com/`.
1. The user clicks on the link `https://www.flytohawaiiforfree.com/` and is redirected by the server to your main site, `https://www.flywithus.com`. Quando o redirecionamento acontece, os dados que são importantes para a coleta de dados do [!DNL Analytics] são perdidos, porque o navegador apaga a URL de referência. Assim, as informações da pesquisa original usadas nos relatórios do [!DNL Analytics] (por exemplo, [!UICONTROL Domínios de Referência], [!UICONTROL Mecanismos de Busca] e [!UICONTROL Palavras-chave de Pesquisa]) são perdidas.

[A implementação de redirecionamentos](../../implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7) discute como as variáveis do [!DNL Analytics] podem ser aproveitadas para capturar os dados perdidos no redirecionamento. Especificamente, a seção discute como resolver a situação de "discount airline tickets" descrita acima.

## Implement redirects {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

Para capturar dados do [!DNL Analytics][!DNL AppMeasurement] por meio de redirecionamentos, quatro pequenas alterações precisam ser feitas no código que cria o redirecionamento e o arquivo do JavaScript.

<!-- 

redirects_implement.xml

 -->

Completing the following steps will retain the information that the original referrer (for example, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` in the scenario above) passes to your site:

## Configure referrer override JavaScript code {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

The code snippet below shows two JavaScript variables, *`s_referrer`* and *`s_pageURL`*. Este código está localizado na página de aterrissagem final do redirecionamento.

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
>Set *`s.referrer`* only once on the page. Definir mais de uma vez com cada chamada de rastreamento ou com cada clique de link rastreado causa a contagem dupla do referenciador e dimensões relacionadas, como ferramentas de pesquisa e palavras-chave.

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

## Modify the redirect mechanism {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Como o navegador tira a URL de referência, você deve configurar o mecanismo que manipula o redirecionamento (por exemplo, o servidor Web, o código do lado do servidor, o código do lado do cliente) para repassar as informações originais do referenciador. Caso você também queira gravar a URL do link alias, ela também deve ser repassada para a página de aterrissagem final. Use a variável  *`s_pageURL`* para substituir a URL atual.

Como há muitas maneiras de implementar um redirecionamento, você precisará verificar com seu grupo de operações Web ou parceiro de publicidade on-line para identificar os mecanismos específicos que executam redirecionamentos em seu site.

## Capture the original referrer {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

Normalmente, o [!DNL Analytics] obtém o URL de referência pela propriedade [!UICONTROL document.referrer] do navegador, e o URL atual da propriedade [!UICONTROL document.location]. By passing values to the *`referrer`* and *`pageURL`* variables, you can override the default processing. Passando um valor para a variável do referenciador, você diz ao [!DNL Analytics] para ignorar as informações do referenciador na propriedade [!UICONTROL document.referrer] e usar um valor alternativo que você definir.

Portanto, a versão final da página inicial precisaria conter o seguinte código para corrigir os problemas apresentados na situação de "discount airline tickets".

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

## Verify the referrer with the Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Run a test to verify that the referrer, originating URL ( *`s_server`*) and campaign variables are being captured.

These variables will be represented as the following parameters in the [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

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
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl % 3 Den % 26 ie % 3 DUTF 826 q % 3 Ddiscount % 2 Bairline % 2 Btickets </span> </p> </td> 
   <td> <p> <span class="filepath"> r = https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8 &amp; q = discount + airline + tickets </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL da página </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g = https://www.flytohawaiiforfree.com </span> </p> <p>This value will appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL da página de aterrissagem final </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p>This value will NOT appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
 </tbody> 
</table>

O texto que o depurador exibe deve corresponder ao seguinte exemplo:

```
Image 
 
https://flywithuscom.112.2o7.net/b/ss/flywithuscom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to FlyWithUs.com 
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

After verifying that the Adobe [!UICONTROL Debugger] displays these variables, it is always helpful to confirm that the search terms and the original referring domain (prior to the redirect) are registering traffic in reports.
