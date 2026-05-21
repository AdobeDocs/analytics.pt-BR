---
title: Funções e métodos
description: Saiba como você pode usar as funções e os métodos que a Adobe oferece na implementação.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 100%

---

# Funções e métodos

A Adobe oferece várias funções e métodos que você pode usar na implementação. Quando você faz referência a essas funções ou métodos, eles executam tarefas comuns com uma única linha de código.

Algumas dessas linhas de código pertencem às seguintes categorias:

* **Rastreamento de chamadas**: os métodos mais comuns e essenciais em muitas implementações. Eles incluem os métodos [`t()`](t-method.md) e [`tl()`](tl-method.md).
* **Utilitários AppMeasurement**: em versões anteriores do AppMeasurement, as implementações precisavam gravar seu próprio código para executar essas tarefas. A Adobe fornece estes métodos de utilitário para simplificar essas tarefas comuns. Os utilitários AppMeasurement incluem [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) e [`Util.getQueryParam()`](util-getqueryparam.md).
* **Registrar funções**: você pode gravar suas próprias funções e fazer com que o AppMeasurement as execute automaticamente antes ou depois de enviar uma chamada de rastreamento para a Adobe. As variáveis que se encaixam nesta categoria são [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) e [`registerPostTrackCallback()`](registerposttrackcallback.md).
