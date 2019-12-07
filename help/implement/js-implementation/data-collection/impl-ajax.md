---
description: A implementação com AJAX é exatamente como implantar código em uma página HTML padrão.
keywords: Analytics Implementation
title: Implementação com AJAX
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementação com AJAX

A implementação com AJAX é exatamente como implantar código em uma página HTML padrão.

A empresa tem perguntas que precisam ser respondidas, as necessidades são avaliadas e as variáveis, atribuídas. O design é então aplicado e implantado. Esses conceitos devem ser familiares e você já deve ter passado pelas fases iniciais de implementação.

## Criação da solução {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

A diferença durante o lançamento de [!UICONTROL AJAX] na combinação é primeiro compreender o nível de detalhes que devem ser reunidos. O potencial de alteração de conteúdo na página (nível macro) ou do rastreamento de atributos do aplicativo (nível micro) determina quais variáveis devem ser definidas e qual método de envio de dados para a Adobe funciona melhor.

## Implantação do código {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Existem duas funções no código JavaScript que permitem enviar dados. Há algumas diretrizes distintas que devem ser seguidas para saber qual método deve ser usado para enviar dados.
Se uma solicitação de imagem foi efetuada anteriormente, primeiro você deve apagar os valores das variáveis definidas anteriormente. Use a função `clearVars()` no [!DNL AppMeasurement] para JavaScript ou grave uma simples função JavaScript para apagar as variáveis, se você estiver usando o código H. Defina os valores apropriados para o conteúdo alterado, a saber, a *`pageName`* variável. Depois que as variáveis forem definidas, chame a função *`t()`*.

> [!NOTE] Antes de chamar `s.t()`, é necessário apagar os valores no objeto s que você não deseja que persistam. se você estiver usando [!DNL AppMeasurement] para JavaScript, é possível chamar `s.clearVars()`. Se você está usando o código H, escreva uma rotina simples para definir variáveis em uma string vazia.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

O exemplo a seguir mostra uma chamada de rastreamento no retorno de chamada `done` da função `.ajax` de JQuery:

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
* Defina as variáveis As variáveis *`linkTrackVars`* e *`linkTrackEvents`*, se você ainda não tiver feito isso no arquivo [!DNL s_code.js].

* Defina os valores apropriados para o conteúdo alterado, a saber, a *`pageName`* variável.
* Depois que as variáveis forem definidas, chame a função *`tl()`*.

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

