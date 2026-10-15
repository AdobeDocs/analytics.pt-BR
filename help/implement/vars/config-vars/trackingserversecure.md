---
title: trackingServerSecure
description: O domínio usado para enviar dados para a Adobe por HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 832a3752ab758d573e5b15b2dc38dad120fe8300
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 11%
---
# trackingServerSecure

A variável `trackingServerSecure` determina o domínio que o AppMeasurement usa para enviar dados para o Adobe por HTTPS. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!NOTE]
>
>[`trackingServer`](configuration-variables.md#retired-configuration-variables) é uma variante removida desta variável. Especificou o domínio para dados enviados via HTTP; com a prevalência de HTTPS, use `trackingServerSecure`. Se `s.trackingServerSecure` estiver em branco, o AppMeasurement voltará ao valor `s.trackingServer`.

## Domínio do Edge usando a extensão Web SDK

O Web SDK usa o [!UICONTROL domínio do Edge] para manipular o Servidor de Rastreamento e o Servidor de Rastreamento Seguro. Você pode definir o valor desejado do [!UICONTROL domínio do Edge] ao configurar a extensão do Web SDK.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Selecione a propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e selecione o botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Defina o campo de texto desejado **[!UICONTROL domínio Edge]**.

Consulte [Configurar a extensão do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) na documentação do Web SDK para obter mais informações.

>[!TIP]
>
>Se sua organização mudar de uma implementação de extensão do AppMeasurement ou do Analytics para o Web SDK, esse campo poderá usar o mesmo valor contido em `trackingServerSecure` (ou `trackingServer`).

## Domínio do Edge que implementa manualmente o Web SDK

Configurar o SDK usando [`edgeDomain`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgedomain). O campo é uma cadeia de caracteres que determina o domínio para o qual enviar dados.

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
// Example value when using a first-party domain
s.trackingServerSecure = "data.example.com";

// Example value when using a third-party domain
s.trackingServerSecure = "example.data.adobedc.net";
```

## Considerações para determinar o valor de `trackingServerSecure`

O valor usado para `trackingServerSecure` (ou `edgeDomain`) depende de como sua organização envia dados para a Adobe:

* **Se sua organização usar um domínio próprio**, como por meio do [programa de certificados gerenciados pela Adobe](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), um [certificado gerenciado pelo cliente](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/customer-managed-cert) ou uma [rede de entrega de conteúdo (CDN)](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cdn), defina o valor para esse domínio. Por exemplo, `data.example.com`.
* **Se sua organização usar um domínio de terceiros**, defina o valor de `data.adobedc.net` como o subdomínio da ID do locatário. Por exemplo, `example.data.adobedc.net`.

Consulte [Escolher um domínio de coleção de dados](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/collection-domain) no guia de administração e interface da CX Enterprise para obter detalhes sobre cada opção, incluindo como encontrar sua ID de locatário.

A Adobe recomenda que essas informações sejam mantidas em um [documento de design da solução](../../prepare/solution-design.md) para que sejam consistentes em toda a organização.

## Ramificações para não usar o Serviço de ID do visitante ou o Serviço de identidade da Experience Platform

A Adobe recomenda usar a ECID como a forma principal de identidade do visitante em todas as implementações. A coleta de ECIDs pode ser implementada de várias maneiras diferentes, dependendo do tipo de implementação:

* As implementações manuais do AppMeasurement usam `VisitorAPI.js` e chamam o método `getInstance`. Consulte [Implementar o Serviço de ID de visitante para o Analytics](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics) para obter mais informações.
* As implementações que usam a extensão de tag da Adobe Analytics usam a [[!UICONTROL extensão de tag do Serviço da Experience Cloud ID]](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview), que implementa o Serviço de ID de visitante. Depois de adicionada, nenhuma configuração adicional é necessária.
* As implementações que usam qualquer forma da Web SDK (`alloy.js` ou a extensão de tag da Web SDK) incluem automaticamente o Experience Platform Identity Service. Nenhuma configuração é necessária além da definição do valor `edgeDomain`.

**Se sua implementação não usar ECIDs**, considere os seguintes impactos na sua implementação:

* Se o Serviço de ID de Visitante ou o Serviço de Identidade da Experience Platform não estiver sendo usado, `trackingServerSecure` determinará a localização do cookie. Definir essa variável como um domínio de terceiros força o AppMeasurement a usar um cookie de fallback, já que a maioria dos navegadores modernos rejeita cookies de terceiros.
* O rastreamento interno de links e o Activity Map podem ser menos confiáveis.
