---
title: Funções e métodos
description: Saiba como você pode usar as funções e os métodos que a Adobe oferece em sua implementação.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Funções e métodos

A Adobe oferece várias funções e métodos que você pode usar na implementação. Quando você faz referência a essas funções ou métodos, eles executam tarefas comuns com uma única linha de código.

Algumas dessas linhas de código pertencem às seguintes categorias:

* **Rastreamento de chamadas**: Os métodos mais comuns e vitais em muitas implementações. Eles incluem os métodos [`t()`](t-method.md) e [`tl()`](tl-method.md) .
* **Utilitários** AppMeasurement: Em versões anteriores do AppMeasurement, as implementações precisavam gravar seu próprio código para executar essas tarefas. A Adobe fornece estes métodos de utilitário para simplificar essas tarefas comuns. Os utilitários do AppMeasurement incluem [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md)e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrar funções**: Você pode gravar suas próprias funções e fazer com que o AppMeasurement as execute automaticamente antes ou depois de enviar uma chamada de rastreamento para a Adobe. As variáveis que se enquadram nesta categoria são [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md)e [`registerPostTrackCallback()`](registerposttrackcallback.md).
