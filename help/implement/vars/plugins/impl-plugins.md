---
title: Visão geral dos plug-ins
description: Cole o código no site para introduzir uma nova funcionalidade.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 328
ht-degree: 96%

---

# Visão geral dos plug-ins

Plug-ins são trechos de código que executam várias funções avançadas que ajudam na implementação do Analytics. Esses plug-ins estendem a capacidade de seu arquivo JavaScript para fornecer a você mais funcionalidade do que a disponível com a implementação básica. A Adobe oferece diversos outros plug-ins como parte das soluções avançadas.

{{plug-in}}

A Adobe oferece várias maneiras de instalar um determinado plug-in:

* Usar a extensão &quot;Plug-ins comuns do Analytics&quot; usando a extensão do Adobe Analytics
* Colar o código do plug-in usando o editor de código personalizado do
* Colar o código do plug-in no seu arquivo `AppMeasurement.js`.

Cada organização tem necessidades de implementação diferentes, de modo que você pode decidir como deseja incluí-los na implementação. Certifique-se de atender aos seguintes critérios ao incluir o código em seu site:

1. Instancie o objeto de rastreamento do Analytics (usando [`s_gi`](../functions/s-gi.md)) primeiro.
   * Seu site habilitado para tag cria uma instância automática do objeto de rastreamento quando o Adobe Analytics é carregado.
   * Implementações que usam `AppMeasurement.js` geralmente inicializam o objeto de rastreamento na parte superior do arquivo JavaScript.
2. Como segundo passo, inclua o código do plug-in.
   * A extensão &quot;Plug-ins comuns do Analytics&quot; tem uma configuração de ação com a qual você pode inicializar plug-ins.
   * Se você não quiser usar a extensão, é possível colar o código do plug-in no editor de código personalizado ao configurar a extensão do Analytics.
   * Se a sua implementação não usar tags na Adobe Experience Platform, você poderá colar o código do plug-in no `AppMeasurement.js` em qualquer lugar depois de instanciar o objeto de rastreamento.
3. Como terceiro passo, chame o plug-in.
   * Todas as implementações, dentro e fora de um site habilitado para tags, usam JavaScript para chamar plug-ins. Chame o plug-in usando o formato documentado na página desse plug-in.
4. Valide sua implementação e publique.

Muitas organizações chamam plug-ins usando a função [`doPlugins`](../functions/doplugins.md). Embora essa função não seja necessária, a Adobe considera usá-la uma prática recomendada. O AppMeasurement chama essa função antes de compilar e enviar uma solicitação de imagem, o que é ideal, pois vários plug-ins dependem de outras variáveis do Analytics.
