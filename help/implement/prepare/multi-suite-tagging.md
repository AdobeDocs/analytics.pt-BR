---
description: Saiba como implementar a marcação de vários conjuntos para enviar solicitação de imagem para vários conjuntos de relatórios.
title: Implementação de marcação de vários relatórios
exl-id: null
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Implementação de marcação de vários relatórios

[A ](/help/admin/c-manage-report-suites/rollup-report-suite.md) marcação de vários relatórios permite enviar solicitações de imagem não apenas para um conjunto de relatórios global, mas também para conjuntos de relatórios secundários individuais, de modo que você possa fornecer subconjuntos dos dados do conjunto de relatórios global da sua empresa para diferentes usuários finais.

Para implementar a marcação de vários conjuntos, você deve incluir a ID do conjunto de relatórios (RSID) para o conjunto de relatórios global e também os RSIDs para os conjuntos de relatórios secundários aplicáveis no código de rastreamento de suas páginas da Web e aplicativos.

* Para implementações do Adobe Experience Platform Launch, especifique cada um dos conjuntos de relatórios para a [[!DNL Analytics] extensão](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html).

* Para implementações herdadas do JavaScript e do SDK móvel, separe os RSIDs com vírgulas e sem espaços (`rsid1,rsid2,rsid3` e assim por diante).

* Para outros tipos de implementação, use a sintaxe necessária para listar vários RSIDs.

>[!TIP]
>
> A prática recomendada é listar o conjunto de relatórios global ou a ID do conjunto de relatórios primeiro.

A marcação de multiconjunto incorre em várias chamadas de servidor para cada solicitação de imagem: uma chamada primária para o conjunto de relatórios global e uma chamada secundária para cada conjunto de relatórios secundário.

>[!NOTE]
>
> [Os conjuntos](/help/components/vrs/vrs-about.md) de relatórios virtuais, que também permitem fornecer subconjuntos de dados do conjunto de relatórios global da sua empresa para diferentes usuários finais, não incorrem em chamadas de servidor secundárias.

## Devo implementar a marcação de vários conjuntos ou conjuntos de relatórios virtuais?

Usar conjuntos de relatórios virtuais em vez da marcação de vários conjuntos é frequentemente uma prática recomendada, mas suas necessidades empresariais determinam a melhor abordagem do conjunto de relatórios para sua organização.

Para entender se os conjuntos de relatórios virtuais são a melhor abordagem, consulte &quot;[Conjuntos de relatórios virtuais e considerações de marcação de vários conjuntos](/help/components/vrs/vrs-considerations.md)&quot;. Consulte também &quot;[Conjuntos de relatórios virtuais vs. Marcação de vários conjuntos](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; para obter uma comparação da funcionalidade de marcação de vários conjuntos e do conjunto de relatórios virtual.
