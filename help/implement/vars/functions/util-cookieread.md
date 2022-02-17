---
title: Util.cookieRead
description: Obtém o valor de um cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 100%

---

# Util.cookieRead

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieRead()` para recuperar um valor de um cookie.

## Ler cookies usando tags na Adobe Experience Platform

É possível ler cookies definindo valores em elementos de dados.

1. Faça logon na [Interface da coleção de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Elementos de dados] e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina a lista suspensa [!UICONTROL Extensão] como [!UICONTROL Principal] e o [!UICONTROL Tipo de elemento de dados] como [!UICONTROL Cookie].
5. Digite o nome do cookie no campo de texto.

O valor do cookie é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir variáveis do Analytics.

## s.Util.cookieRead() no AppMeasurement e no editor de código personalizado do 

Chame o método `s.Util.cookieRead()` para ler um valor de cookie desejado. Seu único argumento é uma string, que é obrigatória. Esse método retorna uma string que contém o valor do cookie. Se os cookies não existirem, uma string vazia será retornada.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
