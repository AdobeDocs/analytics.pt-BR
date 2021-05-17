---
title: Opções para atenuar o efeito das limitações de cookies do navegador
description: Saiba como reduzir o efeito das limitações de cookies do navegador para melhorar a coleta de dados do Adobe Analytics.
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 5%

---


# Opções para atenuar o efeito das limitações de cookies do navegador

Este documento discute opções para preservar a identificação persistente do visitante em todas as propriedades e soluções, à medida que os principais navegadores implementam medidas de prevenção de rastreamento para cookies.

O Adobe Analytics depende de cookies próprios para registrar a atividade de um visitante no site. O Analytics também depende de cookies de terceiros para entender a atividade de um visitante fora do site, como a atividade em outros domínios pertencentes a você. Os cookies de terceiros são bloqueados em muitos navegadores e estarão amplamente indisponíveis com a futura remoção do suporte do Chrome (planejada para 2022). Cookies primários são permitidos em todos os navegadores, mas têm uma expiração limitada no Safari e em outros navegadores nas medidas de [prevenção de rastreamento ITP](https://webkit.org/tracking-prevention) da Apple. Para obter mais informações sobre as limitações atuais de cookies do navegador, consulte [Adobe Analytics e cookies do navegador](cookies.md).

Essas limitações do navegador refletem uma mudança maior de rastreamento anônimo de terceiros em direção ao compartilhamento explícito de informações entre usuários e marcas em que eles confiam. Para respaldar essa mudança, o Adobe fornece aos clientes maneiras de complementar os cookies tradicionais, incluindo identificadores duráveis coletados por meio de seus relacionamentos primários.

## Customer Journey Analytics e Análise entre dispositivos

[Adobe Customer Jornada ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) Analytics e  [Cross-Device ](/help/components/cda/overview.md) Analytics para incluir identificadores duráveis, como logons com hash, além de cookies. Isso permite compreender a jornada do cliente em todos os dispositivos e, no caso do Customer Journey Analytics, em canais online e offline:

* **A** Análise de Jornada do cliente criada com o Adobe Experience Platform e oferece a flexibilidade para combinar dados online e offline no Analysis Workspace, com base em qualquer ID de cliente comum. Você pode especificar qual ID deseja usar para qualquer análise e explorar os dados no Analysis Workspace. Os clientes do Analytics Select, Prime e Ultimate podem adquirir esse produto como produto complementar.

* **O Cross-Device** Analytics é um aprimoramento do Adobe Analytics tradicional que permite que os clientes usem identificadores alternativos para os visitantes. Esse recurso permite mover de uma exibição centrada em dispositivos para uma exibição centrada em pessoas. O Cross-Device Analytics está disponível para clientes do Analytics Ultimate.

## Coleta de dados do lado do servidor

A coleção do lado do servidor fornece a flexibilidade para fornecer seu próprio identificador, em vez de depender dos mecanismos do navegador para configurar cookies.

Você pode enviar dados para o lado do servidor do Analytics usando a [API de inserção de dados](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) ou a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). A API de inserção de dados em massa é recomendada para novas implementações do lado do servidor. Para obter uma comparação das duas APIs, consulte &quot;[Qual ferramenta do Adobe Analytics devo usar](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Mais informações

Para obter etapas práticas, sua empresa pode realizar a transição de cookies de terceiros, consulte [Adquirir e manter os clientes em um mundo sem cookies com Adobe](https://business.adobe.com/solutions/cookieless.html) e o [Pensamento detalhado além do cookie de terceiros: Seu guia completo para um mundo sem cookies de terceiros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
[Adobe Analytics e cookies do navegador](cookies.md)>
>
