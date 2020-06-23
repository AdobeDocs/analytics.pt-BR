---
title: useLinkTrackSessionStorage
description: Armazene dados de rastreamento de link no armazenamento da sessão em vez de um cookie.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useLinkTrackSessionStorage

Se sua organização usar o rastreamento de link, o AppMeasurement usará o cookie `s_sq` para transmitir informações entre as ocorrências. Algumas configurações de site entram em conflito com este cookie. Se você quiser usar o armazenamento de sessão do navegador para rastreamento de link e dados do Activity Map em vez de um cookie, ative essa variável.

O uso do armazenamento de sessão de um navegador para o rastreamento de link apresenta várias limitações:

* O armazenamento de sessão não funciona entre protocolos. Por exemplo, você tem uma página servida por HTTP e a próxima página servida por HTTPS. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento da sessão devido a diferenças de protocolo.
* O armazenamento de sessão não funciona em subdomínios. Por exemplo, um visitante navega até `store.example.com` e, em seguida, navega até `toys.example.com`. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento da sessão devido a subdomínios diferentes.

>[!TIP] A implementação mais confiável usando o armazenamento de sessão para rastreamento de link serve todo o conteúdo por meio de HTTPS em um único subdomínio.

O AppMeasurement remove os dados de rastreamento do link do armazenamento da sessão após enviar uma ocorrência para a Adobe. Ela também expira automaticamente quando a guia do navegador é fechada.

## Usar o armazenamento de sessão de rastreamento de link no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.useLinkTrackSessionStorage no AppMeasurement e no editor de código personalizado do Launch

A variável `s.useLinkTrackSessionStorage` é um booleano que determina se o AppMeasurement usa o armazenamento de sessão para dados de rastreamento de link em vez do cookie `s_sq`. O valor padrão é `false`. Defina essa variável como `true` se você deseja que o AppMeasurement use o armazenamento de sessão em vez do cookie `s_sq` para rastreamento de link e Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
