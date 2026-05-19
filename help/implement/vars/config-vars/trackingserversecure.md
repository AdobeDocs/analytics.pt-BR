---
title: trackingServerSecure
description: O domínio usado para enviar dados para a Adobe por HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 830
ht-degree: 17%

---

# trackingServerSecure

A variável `trackingServerSecure` determina o domínio que o AppMeasurement usa para enviar dados para o Adobe por HTTPS. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

Antes do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home), essa variável também determinava onde os cookies de terceiros eram definidos. A Adobe recomenda usar o serviço de ID em todas as implementações, quando possível.

## Domínio do Edge usando a extensão Web SDK

O Web SDK usa o [!UICONTROL domínio do Edge] para manipular o Servidor de Rastreamento e o Servidor de Rastreamento Seguro. Você pode definir o valor desejado do [!UICONTROL domínio do Edge] ao configurar a extensão do Web SDK.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Selecione a propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e selecione o botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Defina o campo de texto desejado **[!UICONTROL domínio Edge]**.

Consulte [Configurar a extensão do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) na documentação do Web SDK para obter mais informações.

>[!TIP]
>
>Se sua organização mudar de uma implementação de extensão do AppMeasurement ou do Analytics para o Web SDK, esse campo poderá usar o mesmo valor contido em `trackingServerSecure` (ou `trackingServer`).

## Domínio do Edge que implementa manualmente o Web SDK

Configurar o SDK usando [`edgeDomain`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/configure/edgedomain). O campo é uma cadeia de caracteres que determina o domínio para o qual enviar dados.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de rastreamento SSL usando a extensão do Adobe Analytics

[!UICONTROL Servidor de rastreamento SSL] é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Selecione a propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e selecione o botão **[!UICONTROL Configurar]** no Adobe Analytics.
1. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Servidor de rastreamento SSL].

Se este campo ficar em branco, o padrão será o valor no [!UICONTROL Servidor de Rastreamento]. Se o [!UICONTROL Servidor de Rastreamento SSL] e o [!UICONTROL Servidor de Rastreamento] estiverem em branco, o padrão será `[rsid].data.adobedc.net`.

## s.trackingServerSecure no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.trackingServerSecure` é uma cadeia de caracteres que contém o domínio para enviar dados ao Adobe. É somente domínio; omitir protocolo, caminho, porta e barras. Se essa variável estiver em branco, ela usará o valor na variável `s.trackingServer`. Se `s.trackingServerSecure` e `s.trackingServer` estiverem em branco, o padrão será `[rsid].2o7.net`.

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considerações determinando o valor de `trackingServerSecure`

O valor usado para `trackingServerSecure` (ou `edgeDomain`) depende de vários fatores:

* Sua participação no [programa de certificados gerenciados pela Adobe](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/adobe-managed-cert)
* Se você tiver o [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home) implementado e configurado corretamente

**Se sua organização participar do programa de certificados gerenciados pela Adobe**, defina o valor para o domínio próprio que foi selecionado ao configurar o certificado. Normalmente, esse valor é um subdomínio de propriedade de sua organização. Por exemplo, `data.example.com`. Os registros CNAME na organização redirecionam esses dados para a Adobe.

**Se não estiver participando do programa de certificado**, defina o valor como um subdomínio de `data.adobedc.net`. A Adobe recomenda usar a ID da empresa de sua organização para fins de consistência. Por exemplo, `example.data.adobedc.net`. Use as seguintes etapas para determinar a ID da empresa:

1. Faça logon no [Adobe CX Enterprise](https://experience.adobe.com) usando suas credenciais da Adobe ID.
1. Em qualquer lugar na interface do CX Enterprise, pressione `[Cmd]` + `[I]` (iOS) ou `[Ctrl]` + `[I]` (Windows).
1. Um **[!UICONTROL Depurador de dados do usuário]** é exibido. Selecione a guia **[!UICONTROL Organizações atribuídas]**.
1. Expanda a organização IMS desejada.
1. Localize o campo **[!UICONTROL Locatário]**. Este valor é o subdomínio recomendado de `data.adobedc.net` para ser usado.

>[!NOTE]
>
>Não use subdomínios mais profundos do que `example.data.adobedc.net`. Por exemplo, `custom.example.data.adobedc.net` não é um servidor de rastreamento válido.

Implementações mais antigas podem ter valores como `sc.omtrdc.net` ou `2o7.net`. Elas foram usadas principalmente em versões anteriores do Adobe Analytics e ainda são válidas.

A Adobe recomenda que essas informações sejam mantidas em um [documento de design da solução](../../prepare/solution-design.md) para que sejam consistentes em toda a organização.

## Ramificações para não usar o serviço de ID de visitante

A Adobe recomenda usar o [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home) em todas as implementações. O serviço de ID pode ser implementado de várias maneiras diferentes:

* As implementações manuais do AppMeasurement usam `VisitorAPI.js` e chamam o método `getInstance`. Consulte [Implementar o serviço de identidade da Experience Cloud para Analytics](https://experienceleague.adobe.com/pt-br/docs/id-service/using/implementation/setup-analytics) para obter mais informações.
* As implementações que usam a extensão de tag da Adobe Analytics usam a [extensão de tag do serviço da Adobe Experience Cloud ID](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/id-service/overview). Depois de adicionada, nenhuma configuração adicional é necessária.
* As implementações que usam qualquer forma da Web SDK (`alloy.js` ou a extensão de tag da Web SDK) já têm o serviço de ID definido nativamente. Nenhuma configuração é necessária além da definição do valor `edgeDomain`.

**Se sua implementação não usar o serviço de identidade**, considere os seguintes impactos na sua implementação:

* Se o serviço de identidade não estiver sendo usado, `trackingServerSecure` determinará a localização do cookie. Definir essa variável como um domínio de terceiros força o AppMeasurement a usar um cookie de fallback, já que a maioria dos navegadores modernos rejeita cookies de terceiros.
* O rastreamento interno de links e o Activity Map podem ser menos confiáveis.
