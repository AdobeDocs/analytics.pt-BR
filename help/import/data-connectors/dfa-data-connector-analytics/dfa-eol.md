---
title: Integração do DFA - Informações de fim de vida útil
description: Por que o fim da vida útil do Adobe é o conector de dados do DFA e quais alternativas existem?
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Integração do DFA - Informações de fim de vida útil

O Adobe anunciou recentemente [seus planos para o Data Connector do fim da vida útil](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html), um conjunto de ferramentas herdado para integrar dados de terceiros (por exemplo, ESP, VOC etc.) com o Adobe Analytics.

## Por que os Data Connectors estão entrando no fim da vida útil?

A plataforma compatível para integração de parceiros é [Adobe Exchange](https://exchange.adobe.com/experiencecloud), que foi projetada para facilitar a integração de aplicativos Adobe Digital Experience, a integração de CXM de terceiros e para dar suporte aos vários requisitos de dados de clientes e parceiros no futuro. Muitos parceiros que criaram suas integrações usando Data Connectors já migraram essas integrações para o Adobe Exchange, com mais parceiros planejando fazê-lo.

## Por que a integração do DFA está entrando no fim da vida útil?

Em [Janeiro de 2020, o Google anunciou](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html) que eliminará os cookies de terceiros no Chrome até 2022. Isso segue os padrões do setor que a Apple e o Mozilla definiram para seus navegadores Safari e Firefox, respectivamente. A integração do DFA depende de cookies de terceiros e, portanto, se tornará ineficaz e obsoleta com a remoção de cookies de terceiros nos três principais navegadores da Internet. O Google [reforçou essa posição em março de 2021](https://blog.google/products/ads-commerce/a-more-privacy-first-web) ao anunciar que não lançará uma solução alternativa.

Infelizmente, é improvável que o Google — que é proprietário da integração do DFA — replique-a na plataforma Adobe Exchange. Portanto, estamos avançando sob o pressuposto de que, uma vez que os Data Connectors ficarem offline, a integração existente deixará de funcionar e não terá uma substituição produzida.

Um fator importante e adicional é o recurso de &quot;view-throughs&quot; da integração do DFA. Ela permite que o Adobe Analytics rastreie casos em que um usuário visualizou um anúncio de exibição, não clicou, mas depois visitou o site. Os &quot;view-throughs&quot; são baseados em cookies de terceiros, que continuarão a ser eliminados gradualmente ao longo de 2021. Trata-se de uma questão de mercado, não apenas de Adobe. Por enquanto, não existem alternativas para replicar esses dados.

## Quais alternativas existem para você?

Para clientes interessados em integrar dados de anúncios de exibição (sem &quot;view-throughs&quot;) ao Adobe Analytics, temos atualmente as seguintes opções:

* Os clientes do Adobe Advertising Cloud DSP podem aproveitar [uma integração produzida com o Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations) para definir os dados de anúncios de exibição do Google para o Adobe Analytics. Essa integração é nossa melhor alternativa e seria nossa recomendação para os clientes. O Ad Cloud DSP permite que os clientes forneçam experiências conectadas em todos os canais de publicidade, incluindo pesquisa paga, exibição, vídeo e outros. Saiba mais [aqui](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction). No entanto, a DSP do Ad Cloud também será afetada pela perda de cookies de terceiros.
* Adobe Experience Platform e [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en), que fornecem recursos sobre a integração de anúncios de exibição com outras fontes de dados. Os clientes podem baixar os dados de exibição do provedor de pesquisa pago e fazer upload desses dados para o Experience Platform. Em seguida, eles trazem os dados diretamente para o CJA para analisar ao lado de seus outros conjuntos de dados.
* A Adobe Consulting (Arquitetos de engenharia) pode criar uma solução personalizada para assimilar métricas de anúncios de exibição no Adobe Analytics. Essa solução ainda está em desenvolvimento e todos os clientes interessados em ingressar na beta são bem-vindos a participar. Mais detalhes sobre recursos, disponibilidade e custo serão fornecidos à medida que forem sendo disponibilizados.
* Você pode gerenciar sua própria integração de anúncios de exibição, usando a funcionalidade Fontes de dados, bem como Classificações no Adobe Analytics. Importe sua pesquisa paga e exiba os dados manualmente usando as Fontes de Dados e as Classificações [conforme descrito aqui](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases). (Observação: este documento se refere à pesquisa paga, mas o caso de uso e o conceito são os mesmos e podem ser aplicados à exibição).

Para dúvidas ou suporte adicionais, entre em contato com o [Adobe Customer Care](https://helpx.adobe.com/br/contact/enterprise-support.ec.html).