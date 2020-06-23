---
title: linkURL
description: Substitua o URL de link gerado automaticamente que o AppMeasurement usa nas chamadas de rastreamento de link.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkURL

Sempre que uma chamada de rastreamento de link é enviada para a Adobe, os servidores de coleta de dados detectam automaticamente o URL. Use a variável `linkURL` para substituir o URL detectado.

## URL do link no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.linkURL no AppMeasurement e editor de código personalizado do Launch

A variável `s.linkURL` é uma string que contém o URL do navegador de quando o link foi clicado. Essa variável não preenche nenhuma dimensão disponível no relatório.

```js
s.linkURL = "https://example.com";
```

Se a variável [`linkName`](linkname.md) não estiver definida como uma chamada de rastreamento de link, a variável `linkURL` será usada.
