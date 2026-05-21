---
title: Considerações de migração do Serviço de ID de visitante para o Adobe Analytics
description: Uma visão geral de como o Adobe Analytics faz interface com o Serviço de ID de visitante.
exl-id: da1f9917-5254-41fb-9e2c-c94f66a22360
TQID: https://experienceleague.adobe.com/NnZ-Vv2M5cWkfekbVX1B-dFesdtxy50fMdTlwPYviYQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 671
ht-degree: 0%

---

# Considerações de migração do Serviço de ID de visitante para o Adobe Analytics

Se sua organização planeja mudar para o Serviço de ID de visitante com uma implementação existente do Analytics, há alguns tópicos importantes a serem considerados. Essas considerações permitem que você mantenha a integridade da identificação do visitante e entenda como o Serviço de ID opera na presença de uma implementação existente do Analytics.

>[!TIP]
>
>Esta página se aplica somente às implementações de extensão existentes do AppMeasurement ou do Analytics e está adicionando o Serviço de ID do visitante ou atualizando para uma implementação do Web SDK. Em outras palavras, sua implementação usa uma ID do Analytics herdada (`aid`) e está seguindo para o uso de uma ID do Experience Cloud (`mid`). Todas as implementações do Web SDK já usam uma Experience Cloud ID (`mid`) por padrão.

## Como o Serviço de ID de visitante se conecta com os cookies de visitante herdados do Analytics

Como a AppMeasurement tem seu próprio método para identificar visitantes, alguns visitantes podem ter cookies herdados do Analytics quando uma organização implanta o Serviço de ID de visitante. A lista a seguir descreve como um visitante é identificado em circunstâncias variáveis.

* **Nenhum cookie de visitante presente**: o serviço de ID atribui uma Experience Cloud ID (`mid`).
* **Existe um cookie `s_vi`**: o serviço de ID grava a ID do Analytics herdada existente (`aid`) no cookie `AMCV`, além de uma ID do Experience Cloud (`mid`). Como `aid` é maior na [Ordem das operações](overview.md), a ID herdada do Analytics será o identificador de visitante até que o cookie `AMCV` expire ou seja limpo. Quando um período de carência é habilitado, o Serviço de ID inclui `mid` e `aid` em sua resposta.
* **Existe um cookie de fallback**: o serviço de ID não grava o cookie de fallback (`fid`) no cookie `AMCV`. Em vez disso, os visitantes recebem uma Experience Cloud ID (`mid`) como se fossem um novo visitante.

## Período de carência do Serviço de ID do visitante

Se você tiver várias implementações enviando dados para o mesmo conjunto de relatórios e puder implementar o Serviço de ID de visitante em apenas algumas implementações, a Adobe recomenda configurar um período de carência. Por exemplo, se a seção de suporte do site for gerenciada por uma solução de marcação separada, o Serviço de ID do visitante poderá ser implantado no restante do site antes da seção de suporte. Sem um período de carência, os novos visitantes que visualizarem a seção de suporte receberão uma ID de visitante herdada do Analytics, fazendo com que dois visitantes separados sejam contados. Com um período de carência, o serviço de ID de visitante emite uma Experience Cloud ID (`mid`) e uma ID de visitante herdada do Analytics (`aid`) para que as áreas do site sem o Serviço de ID permaneçam consistentes ao identificar os visitantes.

Se você coordenar a implantação do Serviço de ID de visitante em todas as áreas do site, não será necessário um período de carência. Para configurar um período de carência, contate o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/marketing-cloud/contact-support.html). Os períodos de carência podem ser configurados por até 180 dias e renovados. A Adobe recomenda descontinuar o período de carência assim que toda a propriedade estiver configurada para usar o serviço de ID.

## Rastreamento entre domínios

Algumas implementações de ID de visitante herdadas do Analytics podem usar &quot;cookies de terceiros amigáveis&quot;, em que dois domínios compartilham o mesmo cookie de visitante em um domínio comum como o `data.example.com`. Como os cookies amigáveis de terceiros ainda são cookies de terceiros, muitos navegadores modernos os rejeitam, fazendo com que o Analytics dependa de uma ID de fallback (`fid`) para identificação do visitante. Com a migração para o serviço de ID, todos os domínios podem definir o cookie `AMCV` em um contexto próprio, aumentando sua viabilidade de manter uma ID de visitante.

Embora o Serviço de ID de visitante tente definir um cookie de terceiros para rastreamento entre domínios (o [`demdex` cookie ](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)), ele geralmente é rejeitado pelos navegadores modernos. Considere usar o método [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) para transmitir a Experience Cloud ID de um visitante (`mid`) entre os domínios que você possui.

## Rastreamento do lado do servidor

Você pode chamar [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) para obter a Experience Cloud ID (`mid`) e [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) para obter a Analytics ID herdada (`aid`). A Adobe recomenda verificar se ambos preservam a lógica de identificação do visitante.
