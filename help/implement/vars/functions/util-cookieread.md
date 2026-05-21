---
title: Util.cookieRead
description: Obtém o valor de um cookie.
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
TQID: https://experienceleague.adobe.com/BuAe772j8DToDmAkr46Bg5kEAifNIFso0xQ423xdwxg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 72%

---

# Util.cookieRead

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieRead()` para recuperar um valor de um cookie.

## Ler cookies usando a extensão do Adobe Analytics e a extensão do Web SDK

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
