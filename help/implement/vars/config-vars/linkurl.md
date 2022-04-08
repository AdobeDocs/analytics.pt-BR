---
title: linkURL
description: Substitua o URL de link gerado automaticamente que o AppMeasurement usa nas chamadas de rastreamento de link.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '118'
ht-degree: 100%

---

# linkURL

Sempre que uma chamada de rastreamento de link é enviada para a Adobe, os servidores de coleta de dados detectam automaticamente o URL. Use a variável `linkURL` para substituir o URL detectado.

## URL do link usando tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.linkURL no AppMeasurement e editor de código personalizado do

A variável `s.linkURL` é uma string que contém o URL do navegador de quando o link foi clicado. Essa variável não preenche nenhuma dimensão disponível no relatório.

```js
s.linkURL = "https://example.com";
```

Se o terceiro argumento do método [tl()](../functions/tl-method.md) não estiver definido, a variável `linkURL` será usada.
