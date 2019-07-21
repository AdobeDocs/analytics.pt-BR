---
description: A implementação com AJAX é exatamente como implantar código em uma página HTML padrão.
keywords: Implementação do Analytics
seo-description: A implementação com AJAX é exatamente como implantar código em uma página HTML padrão.
seo-title: Implementação com AJAX
solution: Analytics
title: Implementação com AJAX
topic: Desenvolvedor e implementação
uuid: 9 e 3477 ef -7 dea -4 c 76-ab 61-36 a 188222 be 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementação com AJAX

A implementação com AJAX é exatamente como implantar código em uma página HTML padrão.

A empresa tem perguntas que precisam ser respondidas, as necessidades são avaliadas e as variáveis, atribuídas. O design é então aplicado e implantado. Esses conceitos devem ser familiares e você já deve ter passado pelas fases iniciais de implementação.

## Criação da solução {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

A diferença durante o lançamento de [!UICONTROL AJAX] na combinação é primeiro compreender o nível de detalhes que devem ser reunidos. O potencial de alteração de conteúdo na página (nível macro) ou do rastreamento de atributos do aplicativo (nível micro) determina quais variáveis devem ser definidas e qual método de envio de dados para a Adobe funciona melhor.

## Implantação do código {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Existem duas funções no código JavaScript que permitem enviar dados. Há algumas diretrizes distintas que devem ser seguidas para saber qual método deve ser usado para enviar dados.
Se uma solicitação de imagem foi efetuada anteriormente, primeiro você deve apagar os valores das variáveis definidas anteriormente. Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

>[!NOTE]
>
>Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. Se você está usando o código H, escreva uma rotina simples para definir variáveis em uma string vazia.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

Se uma solicitação de imagem tiver sido previamente feita na mesma página, apague os valores das variáveis definidas previamente. Isso pode ser feito desta forma:

* Escreva uma função JavaScript simples para apagar as variáveis da Adobe.
* Defina as variáveis *`linkTrackVars`* e *`linkTrackEvents`* variáveis se você ainda não tiver feito isso no [!DNL s_code.js] arquivo.

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```

