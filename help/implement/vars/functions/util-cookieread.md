---
title: Util.cookieRead
description: Obtém o valor de um cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieRead

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o `Util.cookieRead()` método para recuperar um valor de um cookie.

## Leia os cookies no Adobe Experience Platform Launch

É possível ler cookies definindo valores em elementos de dados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Data Elements] guia e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina a [!UICONTROL Extension] lista suspensa como [!UICONTROL Core], e a opção [!UICONTROL Data Element Type] como [!UICONTROL Cookie].
5. Digite o nome do cookie no campo de texto.

O valor do cookie é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir variáveis do Analytics.

## s.Util.cookieRead() no AppMeasurement e Iniciar editor de código personalizado

Chame o `s.Util.cookieRead()` método para ler um valor de cookie desejado. Seu único argumento é uma string, que é obrigatória. Esse método retorna uma string contendo o valor do cookie. Se os cookies não existirem, uma string vazia será retornada.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
