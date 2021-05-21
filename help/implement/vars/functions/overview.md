---
title: Funções e métodos
description: Saiba como você pode usar as funções e os métodos que a Adobe oferece na implementação.
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---

# Funções e métodos

A Adobe oferece várias funções e métodos que você pode usar na implementação. Quando você faz referência a essas funções ou métodos, eles executam tarefas comuns com uma única linha de código.

Algumas dessas linhas de código pertencem às seguintes categorias:

* **Rastreamento de chamadas**: os métodos mais comuns e essenciais em muitas implementações. Eles incluem os métodos [`t()`](t-method.md) e [`tl()`](tl-method.md).
* **Utilitários AppMeasurement**: em versões anteriores do AppMeasurement, as implementações precisavam gravar seu próprio código para executar essas tarefas. A Adobe fornece estes métodos de utilitário para simplificar essas tarefas comuns. Os utilitários AppMeasurement incluem [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrar funções**: você pode gravar suas próprias funções e fazer com que o AppMeasurement as execute automaticamente antes ou depois de enviar uma chamada de rastreamento para a Adobe. As variáveis que se encaixam nesta categoria são [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) e [`registerPostTrackCallback()`](registerposttrackcallback.md).
