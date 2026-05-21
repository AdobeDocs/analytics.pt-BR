---
title: useLinkTrackSessionStorage
description: Armazene dados de rastreamento de link no armazenamento da sessão em vez de um cookie.
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
TQID: https://experienceleague.adobe.com/n2TiWJuwct2fSZ3gz8UOhX9w--yXZ35yLrxQItVOXfk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 86%

---

# useLinkTrackSessionStorage

Se sua organização usar o rastreamento de link, o AppMeasurement usará o cookie `s_sq` para transmitir informações entre as ocorrências. Algumas configurações de site entram em conflito com este cookie. Se você quiser usar o armazenamento de sessão do navegador para rastreamento de link e dados do Activity Map em vez de um cookie, habilite essa variável.

O uso do armazenamento de sessão de um navegador para o rastreamento de link apresenta várias limitações:

* O armazenamento de sessão não funciona entre protocolos. Por exemplo, você tem uma página servida por HTTP e a próxima página servida por HTTPS. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento da sessão devido a diferenças de protocolo.
* O armazenamento de sessão não funciona em subdomínios. Por exemplo, um visitante navega até `store.example.com` e, em seguida, navega até `toys.example.com`. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento da sessão devido a subdomínios diferentes.

>[!TIP]
>
>A implementação mais confiável usando o armazenamento de sessão para rastreamento de link serve todo o conteúdo por meio de HTTPS em um único subdomínio.

O AppMeasurement remove os dados de rastreamento do link do armazenamento da sessão após enviar uma ocorrência para a Adobe. Ela também expira automaticamente quando a guia do navegador é fechada.

## Usar o armazenamento de sessão de rastreamento de link usando o Web SDK

O Web SDK não oferece suporte a essa funcionalidade.

## Usar o armazenamento de sessão de rastreamento de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.useLinkTrackSessionStorage no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.useLinkTrackSessionStorage` é um booleano que determina se o AppMeasurement usa o armazenamento de sessão para dados de rastreamento de link em vez do cookie `s_sq`. O valor padrão é `false`. Defina essa variável como `true` se você deseja que o AppMeasurement use o armazenamento de sessão em vez do cookie `s_sq` para rastreamento de link e Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
