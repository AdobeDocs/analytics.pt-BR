---
title: Identificação do visitante usando o AppMeasurement
description: Identifique corretamente os visitantes ao implementar o Adobe Analytics usando o AppMeasurement.
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Identificação do visitante usando o AppMeasurement

O AppMeasurement é a biblioteca JavaScript herdada do Adobe Analytics para coleta de dados. Embora o AppMeasurement por si só ofereça uma maneira nativa de identificar visitantes, muitos navegadores modernos rejeitam os cookies que ele tenta definir. A Adobe recomenda usar o Serviço de ID de visitante da Adobe Experience Cloud em todas as implementações para estar em conformidade com os padrões modernos de privacidade do navegador. Todas as versões do AppMeasurement vêm com o `VisitorAPI.js`, a biblioteca de JavaScript usada para implementar o Serviço de ID de visitante.

## Identificação de visitantes usando o Serviço de ID de visitante (recomendado)

Use esta seção para criar uma integração básica entre o Adobe Analytics e o Serviço de ID do visitante. Esteja preparado com o seguinte:

* Baixe a [versão mais recente do AppMeasurement](https://github.com/adobe/appmeasurement). A biblioteca baixada inclui `AppMeasurement.js` e `VisitorAPI.js`.
* Uma [ID do conjunto de relatórios](/help/admin/tools/manage-rs/new-rs/new-report-suite.md) de desenvolvimento.
* O domínio desejado para [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Sua ID organizacional IMS:
   1. Faça logon em [experience.adobe.com](https://experience.adobe.com) usando suas credenciais da Adobe ID.
   1. Em qualquer lugar na interface do Experience Cloud, pressione `[Cmd]` + `[I]` (iOS) ou `[Ctrl]` + `[I]` (Windows).
   1. Um **[!UICONTROL Depurador de dados do usuário]** é exibido. Selecione a guia **[!UICONTROL Organizações atribuídas]**.
   1. Expanda a organização IMS desejada.
   1. Localize o campo **[!UICONTROL ID]**.

Depois de obter os recursos acima, consulte a seguinte página de exemplo básica contendo o mínimo de chamadas necessárias para enviar dados para o Adobe Analytics:

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
>Você pode acompanhar se uma ocorrência usa o serviço de ID de visitante atribuindo a presença de `Visitor` a uma variável personalizada:
>
>```js
>s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI Present" : "VisitorAPI Missing";
>```

## Identificação de visitantes usando o cookie `s_vi` (Não recomendado)

>[!IMPORTANT]
>
>A Adobe recomenda não usar esse método para identificar visitantes.

Se sua organização não usar o Serviço de ID de visitante, a AppMeasurement usará sua própria forma de identificação do visitante. Quando um visitante chega ao seu site pela primeira vez, a biblioteca verifica se há um cookie [`s_vi`](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/cookies/analytics). Este cookie é definido no domínio correspondente a [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (para HTTPS) ou [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (para HTTP).

* Se você participar do [Programa de certificado gerenciado](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/adobe-managed-cert), o servidor de rastreamento normalmente será um domínio próprio, tornando os cookies do `s_vi` originais.
* Se você não participar do programa de certificado gerenciado, o servidor de rastreamento normalmente é um subdomínio de `adobedc.net`, `omtrdc.net` ou `2o7.net`, tornando o cookie `s_vi` um cookie de terceiros. Devido às práticas modernas de privacidade do navegador, os cookies de terceiros são rejeitados pela maioria dos navegadores. Depois de rejeitado, o AppMeasurement tenta definir um cookie de fallback primário (`fid`).

Se você definir corretamente `trackingServerSecure`, nenhuma outra medida de identificação de visitante será necessária.

## Identificando visitantes usando `visitorID` (Não recomendado)

>[!IMPORTANT]
>
>A Adobe recomenda não usar esse método para identificar visitantes.

Usar a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) permite que sua organização controle independente completo identificando visitantes. Se você usar `visitorID`, observe as seguintes limitações:

* Cada ocorrência deve conter o mesmo valor `visitorID` para ser contado como um único visitante.
   * Qualquer ocorrência que omita `visitorID` tenta automaticamente usar outro método de identificação de visitante, tratando-os como um visitante separado.
   * Todas as ocorrências que contêm um valor `visitorID` diferente de uma ocorrência anterior são tratadas como um visitante separado.
   * A Adobe não oferece nenhuma maneira de compilar ocorrências usando diferentes IDs de visitante juntas.
* Públicos-alvo compartilhados, Analytics para Target e Atributos do cliente não são suportados com visitantes identificados usando `visitorID`.

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para obter instruções de implementação usando essa variável.
