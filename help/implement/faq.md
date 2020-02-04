---
title: Perguntas frequentes sobre a implementação do Analytics
description: Perguntas frequentes sobre a implantação e links para mais informações.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Perguntas frequentes sobre a implementação do Analytics

Perguntas frequentes sobre a implantação e links para mais informações.

**Qual é a diferença entre a alocação e a expiração da variável?**

A alocação e a expiração são ambas as configurações que você pode aplicar às variáveis personalizadas. *A alocação* entra em execução quando você tem um valor de variável persistente e um novo valor de variável. Determina se o valor antigo ou novo é mantido. *A expiração* é reproduzida quando você não deseja que um valor variável continue persistindo.

**Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics?**

O Serviço de identidade atribui um identificador exclusivo e persistente que pode ser compartilhado entre outras soluções na Experience Cloud. A ID de visitante do Analytics é usada somente pelo Analytics. A Adobe recomenda usar o Serviço de ID de visitante da Experience Cloud na implementação.

**Como uma ID de visitante é definida se os cookies estiverem bloqueados?**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**Como implementar o rastreamento de vídeo heartbeat?**

Consulte [Avaliação de áudio e vídeo no Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

**Uma interrupção de serviço na Adobe pode afetar o desempenho?**

Não. O arquivo JavaScript não está hospedado em servidores da Adobe, portanto, uma interrupção da Adobe não afeta sua biblioteca do AppMeasurement. Se você usar o Adobe Experience Platform Launch, o arquivo JavaScript será hospedado pelo Akamai ou em um local de servidor determinado pela sua organização.

**O envio de dados do navegador para os serviços da Adobe pode reduzir o desempenho?**

O AppMeasurement cria um objeto de imagem na página HTML e o navegador solicita o objeto de imagem dos servidores de coleta de dados da Adobe. Se os servidores de coleta de dados estivessem lentos ou sem resposta, o thread que processava essa solicitação seria atrasado até que a imagem retornasse ou ocorresse um tempo limite. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar.

**Como faço para rastrear um aplicativo móvel?**

Você pode usar o SDK da plataforma Adobe Experience. Consulte Visão geral [do SDK da plataforma](https://aep-sdks.gitbook.io/docs/) Adobe Experience para obter mais informações.

**O que são plug-ins?**

Plug-ins são trechos de código que executam funções avançadas. Eles estendem os recursos do AppMeasurement para oferecer mais funcionalidade à sua implementação.
