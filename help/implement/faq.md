---
title: Perguntas frequentes sobre a implementação do Analytics
description: Perguntas frequentes sobre a implantação e links para mais informações.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Perguntas frequentes sobre a implementação do Analytics

Perguntas frequentes sobre a implantação e links para mais informações.

**Qual é a diferença entre a alocação e a expiração da variável?**

A alocação e a expiração são configurações que você pode aplicar às variáveis personalizadas. A *alocação* entra em ação quando você tem um valor de variável persistente e um novo valor de variável. Ela determina se o valor antigo ou o novo é mantido. A *expiração* entra em ação quando você quer que um valor variável seja mantido.

**Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics?**

O Serviço de identidade atribui um identificador exclusivo e persistente que pode ser compartilhado entre outras soluções na Experience Cloud. A ID de visitante do Analytics é usada somente pelo Analytics. A Adobe recomenda usar o Serviço de ID de visitante da Experience Cloud na implementação.

**Como uma ID de visitante será definida se os cookies estiverem bloqueados?**

Se o cookie `s_vi` padrão estiver indisponível, um cookie de fallback será criado no domínio do site com uma ID exclusiva gerada aleatoriamente. Este cookie, chamado `s_fid`, é definido com uma expiração de 2 anos e usado como método de identificação de fallback a partir de então.

**Como implementar o rastreamento de vídeo Heartbeat?**

Consulte [Avaliação de áudio e vídeo no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/media-analytics/using/media-overview.html).

**Uma interrupção de serviço na Adobe pode afetar o desempenho?**

Não. O arquivo JavaScript não fica hospedado nos servidores da Adobe, de forma que uma interrupção da Adobe não afete a biblioteca do AppMeasurement. Se você usar o Adobe Experience Platform Launch, o arquivo JavaScript será hospedado pelo Akamai ou em um local de servidor determinado pela organização.

**O envio de dados de um navegador para os serviços da Adobe pode reduzir o desempenho?**

O AppMeasurement cria um objeto de imagem na página HTML e, em seguida, o navegador solicita o envio do objeto de imagem aos servidores de coleta de dados da Adobe. Caso os servidores de coleta de dados fiquem lentos e com pouca capacidade de resposta, o thread responsável pela solicitação será adiado até que a imagem volte ou o tempo limite seja atingido. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar.

**Como rastrear um aplicativo para dispositivos móveis?**

Use o SDK da Adobe Experience Platform. Consulte [Visão geral do SDK da Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/) para obter mais informações.

**O que são plug-ins?**

Plug-ins são trechos de código que executam funções avançadas. Eles estendem os recursos do AppMeasurement para oferecer mais funcionalidade à implementação.
