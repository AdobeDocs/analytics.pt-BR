---
title: Opções para atenuar o efeito das limitações de cookies do navegador
description: Saiba como reduzir o efeito das limitações de cookies do navegador para melhorar a coleta de dados do Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 6%

---


# Opções para atenuar o efeito das limitações de cookies do navegador

Este documento explica como preservar a identificação persistente do visitante em todas as propriedades e soluções, à medida que os principais navegadores implementam medidas de prevenção de rastreamento para cookies.

O Adobe Analytics depende de cookies próprios para registrar a atividade de um visitante no site. O Analytics também depende de cookies de terceiros para entender a atividade de um visitante fora do site, como a atividade em outros domínios pertencentes a você. Os cookies de terceiros são bloqueados em muitos navegadores e estarão amplamente indisponíveis com a futura remoção do suporte do Chrome (planejada para 2022). Cookies primários são permitidos em todos os navegadores, mas têm uma expiração limitada no Safari e em outros navegadores nas medidas de [prevenção de rastreamento ITP](https://webkit.org/tracking-prevention) da Apple. Para obter mais informações sobre as limitações atuais de cookies do navegador, consulte &quot;[Adobe Analytics e cookies do navegador](cookies.md).

Essas limitações do navegador refletem uma mudança maior de rastreamento anônimo de terceiros em direção ao compartilhamento explícito de informações entre usuários e marcas em que eles confiam. Para respaldar essa mudança, o Adobe fornece aos clientes maneiras de complementar os cookies tradicionais, incluindo identificadores duráveis coletados por meio de seus relacionamentos primários.

## Customer Journey Analytics e Análise entre dispositivos

[Adobe Customer Jornada ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) Analytics e  [entre dispositivos ](/help/components/cda/overview.md) Analytics para incluir identificadores duráveis, como logons com hash, além de cookies:

* **O Customer Jornada** Analytics permite a análise entre canais no Analysis Workspace por meio de uma integração com o Adobe Experience Platform. Ele consolida os dados de clientes online e offline disponíveis para você no Experience Platform no momento da consulta, usando qualquer ID.

* **O Cross-Device** Analytics identifica como os dispositivos digitais são mapeados para pessoas e une a jornada do usuário em qualquer ID usando o serviço de identidade da Adobe Experience Platform. Ele usa o gráfico Adobe Experience Cloud Device Co-op, um gráfico de dispositivos privado ou a compilação em campo.

## Coleta de dados do lado do servidor

A coleção do lado do servidor fornece a flexibilidade para fornecer seu próprio identificador, em vez de depender dos mecanismos do navegador para configurar cookies.

Você pode importar dados do lado do servidor para o Analytics usando a [API de inserção de dados](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). Para obter uma comparação das duas APIs, consulte &quot;[Qual ferramenta do Adobe Analytics devo usar](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Mais informações

Para obter etapas práticas, sua empresa pode realizar a transição de cookies de terceiros, consulte &quot;[Adquirir e manter os clientes em um mundo sem cookies com Adobe](https://business.adobe.com/solutions/cookieless.html)&quot; e o &quot;[Pensando além do cookie de terceiros: Seu guia completo para um mundo sem cookies de terceiros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics e cookies do navegador](cookies.md)
