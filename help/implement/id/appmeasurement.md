---
title: Identificação do visitante usando o AppMeasurement
description: Identifique corretamente os visitantes ao implementar o Adobe Analytics usando o AppMeasurement.
exl-id: 38797ca5-dc53-431e-95df-3c9e68aead94
TQID: https://experienceleague.adobe.com/vWLzF0HXreytCKr01H4-gKzNlO36ySHA2vbcHvT3cIw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 0%

---

# Identificação do visitante usando o AppMeasurement

O AppMeasurement é a biblioteca JavaScript herdada do Adobe Analytics para coleta de dados. Embora o AppMeasurement por si só ofereça uma maneira nativa de identificar visitantes, muitos navegadores modernos rejeitam os cookies de terceiros que ele tenta definir. A Adobe recomenda usar o Serviço de ID de visitante da Adobe Experience Cloud em todas as implementações para estar em conformidade com os padrões modernos de privacidade do navegador. Todas as versões do AppMeasurement vêm com o `VisitorAPI.js`, a biblioteca de JavaScript usada para implementar o Serviço de ID de visitante.

## Identificação de visitantes usando o Serviço de ID de visitante (recomendado)

Esteja preparado com o seguinte:

* Baixe a [versão mais recente do AppMeasurement](https://github.com/adobe/appmeasurement). A biblioteca baixada inclui `AppMeasurement.js` e `VisitorAPI.js`.
* Uma [ID do conjunto de relatórios](/help/admin/tools/manage-rs/new-rs/new-report-suite.md) de desenvolvimento.
* O domínio de borda desejado para [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Sua ID organizacional IMS:
   1. Faça logon no [Adobe CX Enterprise](https://experience.adobe.com) usando suas credenciais da Adobe ID.
   1. Em qualquer lugar na interface do CX Enterprise, pressione `[Cmd]` + `[I]` (iOS) ou `[Ctrl]` + `[I]` (Windows).
   1. Um **[!UICONTROL Depurador de dados do usuário]** é exibido. Selecione a guia **[!UICONTROL Organizações atribuídas]**.
   1. Expanda a organização IMS desejada.
   1. Localize o campo **[!UICONTROL ID]**.

Depois de usar os recursos acima, a página de exemplo básica a seguir conterá o mínimo de chamadas necessárias para enviar dados ao Adobe Analytics:

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>Você pode acompanhar se uma ocorrência usa o serviço de ID de visitante atribuindo a presença de `Visitor` a uma variável personalizada em [`doPlugins`](/help/implement/vars/functions/doplugins.md):
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## Identificação de visitantes usando o cookie `s_vi` (Não recomendado)

>[!IMPORTANT]
>
>A Adobe recomenda não usar esse método para identificar visitantes.

Se sua organização não usar o Serviço de ID de visitante, a AppMeasurement usará sua própria forma de identificação do visitante. Quando um visitante chega ao seu site pela primeira vez, a biblioteca verifica se há um cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Este cookie é definido no domínio correspondente a [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (para HTTPS) ou [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (para HTTP).

* Se você participar do [Programa de certificado gerenciado](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), o servidor de rastreamento normalmente será um domínio próprio, tornando os cookies do `s_vi` originais.
* Se você não participar do programa de certificado gerenciado, o servidor de rastreamento normalmente é um subdomínio de `adobedc.net`, `omtrdc.net` ou `2o7.net`, tornando o cookie `s_vi` um cookie de terceiros. Devido aos padrões modernos de privacidade do navegador, os cookies de terceiros são rejeitados pela maioria dos navegadores. Depois de rejeitado, o AppMeasurement tenta definir um cookie de fallback primário (`fid`).

Se você definir corretamente `trackingServerSecure`, nenhuma outra medida de identificação de visitante será necessária.

## Identificando visitantes usando `visitorID` (Não recomendado)

>[!IMPORTANT]
>
>A Adobe recomenda não usar esse método para identificar visitantes.

Usar a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) permite que sua organização controle independente completo identificando visitantes. Se você usar `visitorID`, observe as seguintes limitações:

* Cada ocorrência deve conter o mesmo valor `visitorID` para ser contado como um único visitante.
   * Qualquer ocorrência que omita `visitorID` tenta automaticamente usar outro método de identificação de visitante, tratando-os como um visitante separado.
   * Todas as ocorrências que contêm um valor `visitorID` diferente de uma ocorrência anterior são tratadas como um visitante separado.
   * A Adobe não oferece uma maneira de compilar ocorrências usando diferentes IDs de visitante no Adobe Analytics.
* Públicos-alvo compartilhados, Analytics para Target e Atributos do cliente não são suportados com visitantes identificados usando `visitorID`.

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para obter instruções de implementação usando essa variável.
