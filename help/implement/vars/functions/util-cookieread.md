---
title: Util.cookieRead
description: Obtém o valor de um cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 72%

---

# Util.cookieRead

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieRead()` para recuperar um valor de um cookie.

## Ler cookies usando a extensão do Adobe Analytics e a extensão SDK da Web

É possível ler cookies definindo valores em elementos de dados.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Elementos de dados] e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina a lista suspensa [!UICONTROL Extensão] como **[!UICONTROL Núcleo]** e o [!UICONTROL Tipo de Elemento de Dados] como **[!UICONTROL Cookie]**.
5. Digite o nome do cookie no campo de texto.

O valor do cookie é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir as variáveis desejadas.

## s.Util.cookieRead() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `s.Util.cookieRead()` para ler um valor de cookie desejado. Seu único argumento é uma string, que é obrigatória. Esse método retorna uma string que contém o valor do cookie. Se os cookies não existirem, uma string vazia será retornada.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
