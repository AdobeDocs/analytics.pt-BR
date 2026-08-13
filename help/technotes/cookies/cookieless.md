---
title: Opções para atenuar o efeito das limitações de cookies do navegador
description: Saiba como reduzir o efeito das limitações de cookies do navegador para melhorar a coleção de dados do Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
TQID: https://experienceleague.adobe.com/f6gcSRLmsupsIVKYH-bF1T7vuVhoj9Ef8zVh3t6vU2Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 98%

---

# Opções para atenuar o efeito das limitações de cookies do navegador

Este documento discute opções para preservar a identificação persistente do visitante em todas as propriedades e soluções, à medida que os principais navegadores implementam medidas de prevenção de rastreamento para cookies.

O Adobe Analytics depende de cookies primários para registrar a atividade de um visitante no site. O Analytics também depende de cookies de terceiros para entender a atividade de um visitante fora do site, como a atividade em outros domínios pertencentes a você. Os cookies de terceiros são bloqueados em muitos navegadores e estarão amplamente indisponíveis com a futura remoção do suporte do Chrome (planejada para o fim de 2024). Cookies primários são permitidos em todos os navegadores, mas têm uma expiração limitada no Safari e em outros navegadores nas medidas de [prevenção de rastreamento ITP](https://webkit.org/tracking-prevention) da Apple. Para obter mais informações sobre as limitações atuais de cookies do navegador, consulte [Adobe Analytics e cookies do navegador](cookies.md).

Essas limitações do navegador refletem uma mudança maior de rastreamento anônimo de terceiros em direção ao compartilhamento explícito de informações entre usuários e marcas em que eles confiam. Para respaldar essa mudança, a Adobe fornece aos clientes maneiras de complementar os cookies tradicionais, incluindo identificadores duráveis coletados por meio de seus relacionamentos primários.

## Customer Journey Analytics e Cross Device Analytics

[O Adobe Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-overview) e o [Cross-Device Analytics](/help/components/cda/overview.md) permitem que os usuários incluam identificadores duráveis, como logons com hash, além de cookies. Isso permite compreender a jornada do cliente em todos os dispositivos e, no caso do Customer Journey Analytics, em canais online e offline:

* **O Customer Journey Analytics** é fundamentado na Adobe Experience Platform e oferece flexibilidade para combinar dados online e offline no Analysis Workspace, com base em qualquer ID de cliente comum. Você pode especificar qual ID deseja usar para qualquer análise e explorar os dados no Analysis Workspace. Os clientes do Analytics Select, Prime e Ultimate podem adquirir esse produto complementar.

* **O Cross-Device Analytics** é um aprimoramento do Adobe Analytics tradicional que permite que os clientes usem identificadores alternativos para os visitantes. Esse recurso permite mover de uma exibição centrada em dispositivos para uma exibição centrada em pessoas. O Cross-Device Analytics está disponível para clientes do Analytics Ultimate.

## Coleção de dados do lado do servidor

A coleção do lado do servidor fornece a flexibilidade para fornecer seu próprio identificador, em vez de depender dos mecanismos do navegador para configurar cookies.

Você pode enviar dados para o lado do servidor do Analytics usando a [API de inserção de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) ou a [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/). A API de inserção de dados em massa é recomendada para novas implementações do lado do servidor. Para obter uma comparação das duas APIs, consulte “[Qual ferramenta do Adobe Analytics devo usar](/help/analyze/get-started/which-analytics-tool.md)”.

## ID do dispositivo próprio (FPID) com o SDK da Web

Com o SDK da Web da Adobe Experience Platform, você pode optar por definir e gerenciar seus próprios identificadores de dispositivos em vez das Experience Cloud IDs (ECIDs) geradas pela Adobe. Elas são chamadas de IDs de dispositivo próprios (FPIDs). Saiba mais [aqui](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/identity/first-party-device-ids).

## Mais informações

Para obter etapas práticas, sua empresa pode realizar a transição de cookies de terceiros. Consulte [Adquirir e manter os clientes em um mundo sem cookies com a Adobe](https://business.adobe.com/pt/solutions/cookieless.html) e o detalhado [Pensamento além do cookie de terceiros: o manual completo para um mundo sem cookies de terceiros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics e cookies de navegador](cookies.md)
