---
title: Considerações de migração do Serviço de ID de visitante para o Adobe Analytics
description: Uma visão geral de como o Adobe Analytics faz interface com o Serviço de ID de visitante.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Considerações de migração do Serviço de ID de visitante para o Adobe Analytics

Se sua organização planeja mudar para o Serviço de ID de visitante com uma implementação existente do Analytics, há alguns tópicos importantes a serem considerados. Essas considerações são importantes para manter a integridade da identificação do visitante e entender como o Serviço de ID opera na presença de uma implementação existente do Analytics.

## Como o Serviço de ID de visitante se conecta com os cookies de visitante herdados do Analytics

Como a AppMeasurement tem seu próprio método para identificar visitantes, alguns visitantes podem ter cookies herdados do Analytics quando uma organização implanta o Serviço de ID de visitante. A lista a seguir descreve como um visitante é identificado em circunstâncias variáveis.

* **Nenhum cookie de visitante presente**: o serviço de ID atribui uma Experience Cloud ID (`mid`).
* **Existe um cookie `s_vi`**: o serviço de ID grava a ID do Analytics herdada existente (`aid`) no cookie `AMCV`, além de uma ID do Experience Cloud (`mid`). Como `aid` é maior na [Ordem das operações](overview.md), a ID herdada do Analytics será o identificador de visitante até que o cookie `AMCV` expire ou seja limpo. Quando um período de carência é habilitado, o Serviço de ID inclui `mid` e `aid` em sua resposta.
* **Existe um cookie de fallback**: o serviço de ID não grava o cookie de fallback (`fid`) no cookie `AMCV`. Em vez disso, os visitantes recebem uma Experience Cloud ID (`mid`) como se fossem um novo visitante.

## Período de carência do Serviço de ID do visitante

Se você tiver várias implementações enviando dados para o mesmo conjunto de relatórios e puder implementar o Serviço de ID de visitante em apenas algumas implementações, a Adobe recomenda configurar um período de carência. Por exemplo, se a seção de suporte do site for gerenciada por uma solução de marcação separada, o Serviço de ID do visitante poderá ser implantado no restante do site antes da seção de suporte. Sem um período de carência, os novos visitantes que visualizarem a seção de suporte receberão uma ID de visitante herdada do Analytics, fazendo com que dois visitantes separados sejam contados. Com um período de carência, o serviço de ID de visitante emite uma Experience Cloud ID (`mid`) e uma ID de visitante herdada do Analytics (`aid`) para que as áreas do site sem o Serviço de ID permaneçam consistentes ao identificar os visitantes.

Se você coordenar a implantação do Serviço de ID de visitante em todas as áreas do site, não será necessário um período de carência. Para configurar um período de carência, contate o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/marketing-cloud/contact-support.html).

## Rastreamento entre domínios

Algumas implementações de ID de visitante herdadas do Analytics podem usar &quot;cookies de terceiros amigáveis&quot;, em que dois domínios compartilham o mesmo cookie de visitante em um domínio comum como o `data.example.com`. Como os cookies amigáveis de terceiros ainda são cookies de terceiros, a maioria dos navegadores modernos os rejeita, fazendo com que o Analytics dependa de uma ID de fallback (`fid`) para identificação do visitante. Com a migração para o serviço de ID, todos os domínios podem definir o cookie `AMCV` em um contexto próprio, aumentando sua viabilidade de manter uma ID de visitante.

Embora o Serviço de ID do visitante tente definir um cookie de terceiros para rastreamento entre domínios (o [`demdex` cookie &#x200B;](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)), ele geralmente é rejeitado pela maioria dos navegadores modernos. Considere usar o método [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) para transmitir as Experience Cloud IDs entre domínios que você possui.

## Rastreamento do lado do servidor

Você pode chamar [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) para obter a Experience Cloud ID (`mid`) e [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) para obter a Analytics ID herdada (`aid`). A Adobe recomenda verificar se ambos preservam a lógica de identificação do visitante.
