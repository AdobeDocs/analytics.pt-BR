---
description: A chave para uma implementação de rastreamento de link bem-sucedida é compreender as variáveis s.linkTrackVars e s.linkTrackEvents. Essa compreensão permite a você transmitir os valores personalizados da variável nas ações do usuário.
keywords: Analytics Implementation
title: Uso de s.linkTrackVars e s.linkTrackEvents
topic: Developer and implementation
uuid: f6b7019b-987b-4b7d-a446-80205f7cc36c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Uso de s.linkTrackVars e s.linkTrackEvents

A chave para uma implementação de rastreamento de link bem-sucedida é compreender as variáveis s.linkTrackVars e s.linkTrackEvents. Essa compreensão permite a você transmitir os valores personalizados da variável nas ações do usuário.

Se você estiver implementando o rastreamento de link personalizado e estiver definindo variáveis e eventos [!UICONTROL personalizadas], *`events`*, verifique se sua variável [!UICONTROL s.linkTrackVars] contém uma lista separada por vírgulas de todas as variáveis que você está transmitindo, incluindo a variável *`events`*. Verifique se [!UICONTROL s.linkTrackEvents] inclui uma lista separada por vírgulas de todos os eventos que você está transmitindo.

A configuração de [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] não define realmente essas variáveis/eventos, ela apenas prepara o código do [!DNL Analytics] para fazer isso. Você ainda deverá definir as variáveis manualmente, como mostrado no exemplo abaixo:

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

Observe que os eventos são listados na variável [!UICONTROL s.linkTrackVars]. Os eventos individuais que podem ser transmitidos são incluídos na variável [!UICONTROL s.linkTrackEvents] e dentro de [!UICONTROL s.events], posteriormente na função. Cada variável transmitida é listada em [!UICONTROL s.linkTrackVars] antes de ser preenchida mais tarde, na função. Além disso, "event9" foi incluída no [!UICONTROL s.linkTrackEvents], mas não foi incluída em [!UICONTROL s.events]. Isso não é registrado, mas pode ser registrado se o usuário optar por definir s.events="event5,event9".

O download automático de arquivos e o rastreamento de link de [!UICONTROL Saída] funcionam de forma diferente. [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] estão incluídos no arquivo [!DNL s_code.js] padrão, e ambas são definidas como nenhum. Geralmente, essas variáveis são configuradas como nenhum no arquivo [!DNL s_code.js], de forma que o rastreamento automático de link, diferente do [!UICONTROL rastreamento personalizado de link], usa os valores de [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] definidos no arquivo JavaScript global. Elas também transmitem os valores dessas variáveis (sejam eles quais forem) sempre que há download de arquivo ou registro de link de [!UICONTROL saída].

Considere o exemplo em que s.channel="Home" quando a página é carregada e em que s.linkTrackVars="channel" em seu arquivo [!DNL s_code.js]. Se um usuário clicar para baixar um arquivo, o rastreamento automático de download de arquivo transmitirá os dados no [!DNL Analytics], incluindo o valor de [!UICONTROL s.channel] definido no carregamento da página. "Home" é transmitido uma segunda vez, levando ao aumento de dados na exibição de página para esse valor, no relatório [!UICONTROL Seções do site].

A Adobe recomenda fortemente deixar [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] definidas como "nenhum" no arquivo JavaScript global e defini-las explicitamente, conforme necessário, com a implementação de seu [!UICONTROL rastreamento de link personalizado].
