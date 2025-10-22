---
title: Identificação do visitante usando a extensão de tag do Adobe Analytics
description: Identifique corretamente os visitantes ao implementar a extensão de tag da Adobe Analytics.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---

# Identificação do visitante usando a extensão de tag do Adobe Analytics

A extensão de tag da Adobe Analytics permite implementar o AppMeasurement usando uma interface de gerenciamento de tags. Como essa extensão de tag é essencialmente do AppMeasurement, ela oferece métodos semelhantes para identificar visitantes e requer uma extensão de tag separada para o Serviço de ID do visitante.

## Identificação de visitantes usando o Serviço de ID de visitante (recomendado)

Para usar o Serviço de ID de visitante usando a extensão de tag da Adobe Analytics, inclua a extensão de tag do Serviço da Experience Cloud ID na propriedade de tag.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com) usando suas credenciais da Adobe ID.
1. Navegue até **[!UICONTROL Coleção de dados]** > **[!UICONTROL Marcas]**.
1. Localize a propriedade de tag desejada.
1. Navegue até **[!UICONTROL Extensões]** e selecione a guia **[!UICONTROL Catálogo]**.
1. Localize a extensão do **[!UICONTROL Experience Cloud ID Service]** e selecione **[!UICONTROL Instalar]**.

A extensão de tag obtém automaticamente sua ID da organização IMS, portanto, nenhuma configuração adicional é necessária.

## Identificação de visitantes usando o cookie `s_vi` (Não recomendado)

>[!IMPORTANT]
>
>A Adobe recomenda não usar esse método para identificar visitantes.

Se a sua organização não usar a extensão de tag do Serviço de ID de visitante, a extensão de tag da Adobe Analytics usará sua própria forma de identificação do visitante. Quando um visitante chega ao seu site pela primeira vez, a extensão verifica se há um cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Este cookie é definido no domínio correspondente ao **[!UICONTROL Servidor de Rastreamento SSL]** (para HTTPS) ou ao **[!UICONTROL Servidor de Rastreamento]** (para HTTP) ao [configurar a extensão de tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview).

* Se você participar do [Programa de certificado gerenciado](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), o servidor de rastreamento normalmente será um domínio próprio, tornando os cookies do `s_vi` originais.
* Se você não participar do programa de certificado Gerenciado, o servidor de rastreamento normalmente é um subdomínio de `adobedc.net`, `omtrdc.net` ou `2o7.net`, tornando o cookie `s_vi` um cookie de terceiros. Devido aos padrões modernos de privacidade do navegador, os cookies de terceiros são rejeitados pela maioria dos navegadores. Depois de rejeitado, o AppMeasurement tenta definir um cookie de fallback primário (`fid`).

Se você definiu corretamente o [!UICONTROL Servidor de Rastreamento SSL], nenhuma outra medida de identificação de visitante será necessária.

## Identificando visitantes usando `visitorID` (Não recomendado)

>[!IMPORTANT]
>
>A Adobe recomenda não usar esse método para identificar visitantes.

Usar a variável **[!UICONTROL ID de visitante]** permite que sua organização conclua o controle independente de identificação de visitantes. Se você definir [!UICONTROL ID de visitante] usando um elemento de dados, observe as seguintes limitações:

* Cada ocorrência deve conter o mesmo valor [!UICONTROL ID de visitante] para ser contado como um único visitante.
   * Qualquer ocorrência que omita o elemento de dados [!UICONTROL ID de visitante] tenta automaticamente usar outro método de identificação de visitante, tratando-o como um visitante separado.
   * Qualquer ocorrência que contenha um valor de [!UICONTROL ID de visitante] diferente de uma ocorrência anterior é tratada como um visitante separado.
   * A Adobe não oferece uma maneira de compilar ocorrências usando diferentes IDs de visitante no Adobe Analytics.
* Públicos-alvo compartilhados, Analytics para Target e Atributos do cliente não são suportados com visitantes identificados usando a [!UICONTROL ID do visitante].

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para obter instruções de implementação usando essa variável.
