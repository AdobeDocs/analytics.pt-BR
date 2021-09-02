---
title: trackingServerSecure
description: Defina para que local as solicitações de imagem são enviadas em páginas HTTPS.
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# trackingServerSecure

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A variável `trackingServerSecure` determina o local para onde uma solicitação de imagem é enviada por HTTPS. Também determina o local em que os cookies do visitante são armazenados. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!IMPORTANT]
>
>Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies de visitantes estão definidos para serem enviados ao novo local.

## Servidor de rastreamento de SSL usando tags na Adobe Experience Platform

[!UICONTROL Servidor de rastreamento SSL] é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Interface da coleção de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Servidor de rastreamento SSL].

Se esse campo ficar em branco, o padrão será o valor na variável [`trackingServer`](trackingserver.md).

## s.trackingServerSecure no AppMeasurement e no editor de código personalizado do 

A varável `s.trackingServerSecure` é uma string que contém o local para o envio de solicitações de imagem. É quase sempre um subdomínio do seu site. Geralmente, práticas de privacidade modernas em navegadores tornam cookies de terceiros não confiáveis. Se essa variável estiver em branco, ela usará o valor na variável `s.trackingServer`.

O valor dessa variável é quase sempre um domínio próprio, como `data.example.com`. Consulte [Cookies próprios na Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR) no guia do usuário dos serviços principais para obter mais informações sobre o processo de configuração de cookies próprios.

O indivíduo que configura inicialmente a implementação do cookie próprio também define o domínio e o subdomínio que são usados. Por exemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Os registros CNAME normalmente apontam para um subdomínio em `data.adobedc.net`, `sc.adobedc.net` ou `2o7.net`.
