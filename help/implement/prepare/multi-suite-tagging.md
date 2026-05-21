---
description: Saiba como implementar a marcação de vários relatórios a fim de enviar uma solicitação de imagem para vários conjuntos de relatórios.
title: Implementação de marcação de vários relatórios
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/djrzQEjvc--wnh2wR1HNV-LVEn6RPcyiaLKLha5pfSY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c77ba355-6681-41fe-b719-563d3f507fdbid: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 302
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
