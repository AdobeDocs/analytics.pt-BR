---
title: Número da visita
description: A nona visita do visitante.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 100%

---

# Número da visita

A [dimensão](overview.md) “Número da visita” informa em qual visita o visitante está atualmente. Quando uma nova visita é iniciada, esse item de dimensão aumenta em uma unidade. Essa dimensão é útil quando você deseja entender como os visitantes estão envolvidos ao retornar ao seu site. É uma dimensão baseada em visita, o que significa que ela contém o mesmo valor para toda a visita e não pode ser alterada. Ela se aplica à duração do visitante, independentemente do intervalo de datas do projeto.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem a string `"Visit number"` seguida pela representação numérica da visita na qual o visitante está no momento. Por exemplo, se o visitante nunca esteve em seu site antes, sua primeira visita pertence ao item de dimensão `"Visit number 1"`. Se essa for a 13ª visita do visitante ao seu site, ela pertencerá ao item de dimensão `"Visit number 13"`.
