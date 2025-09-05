---
description: Saiba como implementar a marcação de vários relatórios a fim de enviar uma solicitação de imagem para vários conjuntos de relatórios.
title: Implementação de marcação de vários relatórios
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 93%

---

# Implementação de marcação de vários relatórios

A [marcação de vários relatórios](/help/admin/tools/manage-rs/rollup-report-suite.md) permite enviar solicitações de imagem não apenas para um conjunto de relatórios global, mas também para conjuntos de relatórios secundários individuais, de modo que você possa fornecer subconjuntos de dados do conjunto de relatórios global de sua empresa a diferentes usuários finais.

Para implementar a marcação de vários relatórios, você deve incluir a ID de conjunto de relatórios (RSID) para o conjunto de relatórios global e também as RSIDs para os conjuntos de relatórios filhos aplicáveis no código de rastreamento de suas páginas da web e aplicativos.

* Para implementações de tags da Adobe Experience Platform, especifique cada um dos conjuntos de relatórios para a [[!DNL Analytics] extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=pt-BR).

* Para implementações do JavaScript legado e do Mobile SDK, separe as RSIDs com vírgulas e sem espaços (`rsid1,rsid2,rsid3` e assim por diante).

* Para outros tipos de implementação, use a sintaxe necessária para listar várias RSIDs.

>[!TIP]
>
> A prática recomendada é listar primeiro o conjunto de relatórios global ou a ID de conjunto de relatórios.

A marcação de vários relatórios incorre em várias chamadas de servidor para cada solicitação de imagem: uma chamada principal para o conjunto de relatórios global e uma chamada secundária para cada conjunto de relatórios filho.

>[!NOTE]
>
> Os [conjuntos de relatórios virtuais](/help/components/vrs/vrs-about.md), que também permitem fornecer subconjuntos de dados do conjunto de relatórios global da sua empresa para diferentes usuários finais, não incorrem em chamadas de servidor secundárias.

## Devo implementar a marcação de vários relatórios ou conjuntos de relatórios virtuais?

Usar conjuntos de relatórios virtuais em vez da marcação de vários relatórios geralmente é uma prática recomendada, mas são suas necessidades empresariais que determinam a melhor abordagem de conjunto de relatórios para a sua organização.

Para entender se os conjuntos de relatórios virtuais são a melhor abordagem, consulte &quot;[Considerações sobre conjuntos de relatórios virtuais e marcação de vários relatórios](/help/components/vrs/vrs-considerations.md)&quot;. Consulte também &quot;[Conjuntos de relatórios virtuais vs. , marcação de vários relatórios](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; para obter uma comparação entre a marcação de vários relatórios e a funcionalidade do conjunto de relatórios virtual.
