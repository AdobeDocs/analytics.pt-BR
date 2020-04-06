---
title: Visão geral dos plug-ins
description: Cole o código no site para introduzir uma nova funcionalidade.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral dos plug-ins

Plug-ins são trechos de código que executam várias funções avançadas que ajudam na implementação do Analytics. Esses plug-ins estendem a capacidade de seu arquivo JavaScript para fornecer a você mais funcionalidade do que a disponível com a implementação básica. A Adobe oferece diversos outros plug-ins como parte das soluções avançadas.

>[!IMPORTANT] Os plug-ins são fornecidos pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte a nenhum desses plug-ins, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com um plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

A Adobe oferece várias maneiras de instalar um determinado plug-in:

1. Usar a extensão &quot;Plug-ins comuns do Analytics&quot; do Adobe Experience Platform Launch.
2. Colar o código do plug-in usando o editor de código personalizado do Launch.
3. Colar o código do plug-in no seu arquivo `AppMeasurement.js`.

Cada organização tem necessidades de implementação diferentes, de modo que você pode decidir como deseja incluí-los na implementação. Certifique-se de atender aos seguintes critérios ao incluir o código em seu site:

1. Instancie o objeto de rastreamento do Analytics (usando [`s_gi`](../functions/s-gi.md)) primeiro.
   * O Launch instancia automaticamente o objeto de rastreamento quando o Adobe Analytics é carregado.
   * Implementações que usam `AppMeasurement.js` geralmente inicializam o objeto de rastreamento na parte superior do arquivo JavaScript.
2. Como segundo passo, inclua o código do plug-in.
   * A extensão &quot;Plug-ins comuns do Analytics&quot; tem uma configuração de ação com a qual você pode inicializar plug-ins.
   * Se você não quiser usar o plug-in, é possível colar o código do plug-in no editor de código personalizado ao configurar a extensão do Analytics.
   * Se sua implementação não usar o Launch, você poderá colar o código do plug-in no `AppMeasurement.js` em qualquer lugar depois de instanciar o objeto de rastreamento.
3. Como terceiro passo, chame o plug-in.
   * Todas as implementações, dentro e fora do Launch, usam JavaScript para chamar plug-ins. Chame o plug-in usando o formato documentado na página desse plug-in.
4. Valide sua implementação e publique.

Muitas organizações chamam plug-ins usando a função [`doPlugins`](../functions/doplugins.md). Embora essa função não seja necessária, a Adobe considera usá-la uma prática recomendada. O AppMeasurement chama essa função antes de compilar e enviar uma solicitação de imagem, o que é ideal, pois vários plug-ins dependem de outras variáveis do Analytics.
