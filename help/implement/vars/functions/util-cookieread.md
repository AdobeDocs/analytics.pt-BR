---
title: Util.cookieRead
description: Obtém o valor de um cookie.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieRead

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieRead()` para recuperar um valor de um cookie.

## Ler cookies no Adobe Experience Platform Launch

É possível ler cookies definindo valores em elementos de dados.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Elementos de dados] e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina a lista suspensa [!UICONTROL Extensão] como [!UICONTROL Principal] e o [!UICONTROL Tipo de elemento de dados] como [!UICONTROL Cookie].
5. Digite o nome do cookie no campo de texto.

O valor do cookie é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir variáveis do Analytics.

## s.Util.cookieRead() no AppMeasurement e no editor de código personalizado do Launch

Chame o método `s.Util.cookieRead()` para ler um valor de cookie desejado. Seu único argumento é uma string, que é obrigatória. Esse método retorna uma string que contém o valor do cookie. Se os cookies não existirem, uma string vazia será retornada.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
