---
title: Opções para atenuar o efeito das limitações de cookies do navegador
description: Saiba como reduzir o efeito das limitações de cookies do navegador para melhorar a coleção de dados do Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
source-git-commit: 860621a058826ba8bf602d87a702f835c7c00a37
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 85%

---

# Opções para atenuar o efeito das limitações de cookies do navegador

Este documento discute opções para preservar a identificação persistente do visitante em todas as propriedades e soluções, à medida que os principais navegadores implementam medidas de prevenção de rastreamento para cookies.

O Adobe Analytics depende de cookies primários para registrar a atividade de um visitante no site. O Analytics também depende de cookies de terceiros para entender a atividade de um visitante fora do site, como a atividade em outros domínios pertencentes a você. Os cookies de terceiros são bloqueados em muitos navegadores e estarão amplamente indisponíveis com a futura remoção do suporte do Chrome (planejada para o final de 2024). Cookies primários são permitidos em todos os navegadores, mas têm uma expiração limitada no Safari e em outros navegadores nas medidas de [prevenção de rastreamento ITP](https://webkit.org/tracking-prevention) da Apple. Para obter mais informações sobre as limitações atuais de cookies do navegador, consulte [Adobe Analytics e cookies do navegador](cookies.md).

Essas limitações do navegador refletem uma mudança maior de rastreamento anônimo de terceiros em direção ao compartilhamento explícito de informações entre usuários e marcas em que eles confiam. Para respaldar essa mudança, a Adobe fornece aos clientes maneiras de complementar os cookies tradicionais, incluindo identificadores duráveis coletados por meio de seus relacionamentos primários.

## Customer Journey Analytics e Cross Device Analytics

[O Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR) e o [Cross-Device Analytics](/help/components/cda/overview.md) permitem que os usuários incluam identificadores duráveis, como logons com hash, além de cookies. Isso permite compreender a jornada do cliente em todos os dispositivos e, no caso do Customer Journey Analytics, em canais online e offline:

* **O Customer Journey Analytics** é fundamentado na Adobe Experience Platform e oferece flexibilidade para combinar dados online e offline no Analysis Workspace, com base em qualquer ID de cliente comum. Você pode especificar qual ID deseja usar para qualquer análise e explorar os dados no Analysis Workspace. Os clientes do Analytics Select, Prime e Ultimate podem adquirir esse produto complementar.

* **O Cross-Device Analytics** é um aprimoramento do Adobe Analytics tradicional que permite que os clientes usem identificadores alternativos para os visitantes. Esse recurso permite mover de uma exibição centrada em dispositivos para uma exibição centrada em pessoas. O Cross-Device Analytics está disponível para clientes do Analytics Ultimate.

## Coleção de dados do lado do servidor

A coleção do lado do servidor fornece a flexibilidade para fornecer seu próprio identificador, em vez de depender dos mecanismos do navegador para configurar cookies.

Você pode enviar dados para o lado do servidor do Analytics usando a [API de inserção de dados](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). A API de inserção de dados em massa é recomendada para novas implementações do lado do servidor. Para obter uma comparação das duas APIs, consulte &quot;[Qual ferramenta do Adobe Analytics devo usar](/help/analyze/get-started/which-analytics-tool.md).&quot;

## ID do dispositivo próprio (FPID) com o SDK da Web

Com o SDK da Web da Adobe Experience Platform, você pode optar por definir e gerenciar seus próprios identificadores de dispositivos em vez das IDs de Experience Cloud geradas por Adobe (ECIDs). Elas são chamadas de IDs de dispositivo originais (FPIDs). Saiba mais [aqui](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=pt-BR).

## Mais informações

Para obter etapas práticas, sua empresa pode realizar a transição de cookies de terceiros. Consulte [Adquirir e manter os clientes em um mundo sem cookies com a Adobe](https://business.adobe.com/pt/solutions/cookieless.html) e o detalhado [Pensamento além do cookie de terceiros: o manual completo para um mundo sem cookies de terceiros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics e cookies de navegador](cookies.md)
