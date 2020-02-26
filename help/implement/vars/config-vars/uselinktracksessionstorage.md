---
title: useLinkTrackSessionStorage
description: Armazene dados de rastreamento de link no armazenamento da sessão em vez de um cookie.
translation-type: tm+mt
source-git-commit: e1a08ecd3d5eb41bce7ca91027249871c3b5b22f

---


# useLinkTrackSessionStorage

Se sua organização usar o rastreamento de link, o AppMeasurement usará o `s_sq` cookie para transmitir informações entre as ocorrências. Algumas configurações de site entram em conflito com este cookie. Se você quiser usar o armazenamento da sessão do navegador para rastreamento de links e dados do Activity Map em vez de um cookie, ative essa variável.

O uso do armazenamento de sessão de um navegador para o rastreamento de links tem várias limitações:

* O armazenamento da sessão não funciona entre protocolos. Por exemplo, você tem uma página servida por HTTP e a próxima página servida por HTTPS. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento de sessão devido a diferenças de protocolo.
* O armazenamento da sessão não funciona em subdomínios. Por exemplo, um visitante navega até `store.example.com`e, em seguida, navega até `toys.example.com`. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento de sessão devido a subdomínios diferentes.

> [!TIP] A implementação mais confiável usando armazenamento de sessão para rastreamento de link serve todo o conteúdo por meio de HTTPS em um único subdomínio.
O AppMeasurement remove os dados de rastreamento do link de armazenamento de sessão após enviar uma ocorrência para a Adobe. Ela também expira automaticamente quando a guia do navegador é fechada.

## Usar o armazenamento da sessão de rastreamento de link no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.useLinkTrackSessionStorage no AppMeasurement e Iniciar editor de código personalizado

A `s.useLinkTrackSessionStorage` variável é um booleano que determina se o AppMeasurement usa o armazenamento de sessão para dados de rastreamento de link em vez do `s_sq` cookie. Its default value is `false`. Defina essa variável para `true` se você deseja que o AppMeasurement use armazenamento de sessão em vez do `s_sq` cookie para rastreamento de link e Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
