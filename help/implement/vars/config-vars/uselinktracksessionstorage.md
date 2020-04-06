---
title: useLinkTrackSessionStorage
description: Armazene dados de rastreamento de link no armazenamento da sessão em vez de um cookie.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useLinkTrackSessionStorage

Se sua organização usar o rastreamento de link, o AppMeasurement usará o `s_sq` cookie para transmitir informações entre as ocorrências. Algumas configurações de site entram em conflito com este cookie. Se você quiser usar o armazenamento de sessão do navegador para rastreamento de link e dados do mapa de Atividade em vez de um cookie, ative essa variável.

O uso do armazenamento de sessão de um navegador para o rastreamento de link apresenta várias limitações:

* O armazenamento de sessão não funciona entre protocolos. Por exemplo, você tem uma página servida por HTTP e a próxima página servida por HTTPS. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento da sessão devido a diferenças de protocolo.
* O armazenamento de sessão não funciona em subdomínios. Por exemplo, um visitante navega até `store.example.com`e, em seguida, navega até `toys.example.com`. O AppMeasurement não pode acessar dados de rastreamento de link no armazenamento da sessão devido a subdomínios diferentes.

>[!TIP] A implementação mais confiável usando o armazenamento de sessão para rastreamento de link serve todo o conteúdo por meio de HTTPS em um único subdomínio.

O AppMeasurement remove os dados de rastreamento do link do armazenamento da sessão após enviar uma ocorrência para a Adobe. Ela também expira automaticamente quando a guia do navegador é fechada.

## Usar o armazenamento de sessão de rastreamento de link no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.useLinkTrackSessionStorage no AppMeasurement e Iniciar editor de código personalizado

A `s.useLinkTrackSessionStorage` variável é um booleano que determina se o AppMeasurement usa o armazenamento session para dados de rastreamento de link em vez do `s_sq` cookie. O valor padrão é `false`. Defina essa variável como `true` se você deseja que o AppMeasurement use o armazenamento de sessão em vez do `s_sq` cookie para rastreamento de link e mapa de Atividade.

```js
s.useLinkTrackSessionStorage = true;
```
