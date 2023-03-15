---
title: trackingServerSecure
description: Defina para que local as solicitações de imagem são enviadas em páginas HTTPS.
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 68%

---

# trackingServerSecure

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A variável `trackingServerSecure` determina o local para onde uma solicitação de imagem é enviada por HTTPS. Também determina o local em que os cookies do visitante são armazenados. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!WARNING]
>
>Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies de visitantes estão definidos para serem enviados ao novo local.

## Domínio de borda usando a extensão SDK da Web

O SDK da Web usa [!UICONTROL Domínio de borda] para lidar com o Servidor de rastreamento e o Servidor de rastreamento seguro. É possível definir as configurações [!UICONTROL Domínio de borda] ao configurar a extensão SDK da Web.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a [!UICONTROL Extensões] e clique na guia **[!UICONTROL Configurar]** botão em [!UICONTROL Adobe Experience Platform Web SDK].
1. Defina o desejado **[!UICONTROL Domínio de borda]** campo de texto.

Consulte [Configurar a extensão SDK da Web do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) na documentação do SDK da Web para obter mais informações.

>[!TIP]
>
>Se sua organização mudar para o SDK da Web de uma implementação de extensão do AppMeasurement ou do Analytics, esse campo poderá usar o mesmo valor contido em `trackingServerSecure` (ou `trackingServer`).

## Domínio de borda que implementa manualmente o SDK da Web

Configurar o SDK usando o [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR). O campo é uma cadeia de caracteres que determina o domínio para o qual enviar dados.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de rastreamento SSL usando a extensão do Adobe Analytics

[!UICONTROL Servidor de rastreamento SSL] é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Servidor de rastreamento SSL].

Se esse campo ficar em branco, o padrão será o valor na variável [`trackingServer`](trackingserver.md).

## s.trackingServerSecure no AppMeasurement e no editor de código personalizado da extensão do Analytics

A varável `s.trackingServerSecure` é uma string que contém o local para o envio de solicitações de imagem. É quase sempre um subdomínio do seu site. Geralmente, práticas de privacidade modernas em navegadores tornam cookies de terceiros não confiáveis. Se essa variável estiver em branco, ela usará o valor na variável `s.trackingServer`.

O valor dessa variável é quase sempre um domínio próprio, como `data.example.com`. Consulte [Cookies próprios na Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR) no guia do usuário dos serviços principais para obter mais informações sobre o processo de configuração de cookies próprios.

O indivíduo que configura inicialmente a implementação do cookie próprio também define o domínio e o subdomínio que são usados. Por exemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Os registros CNAME normalmente apontam para um subdomínio em `data.adobedc.net`, `sc.adobedc.net` ou `2o7.net`.
