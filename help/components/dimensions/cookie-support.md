---
title: Suporte a cookies
description: Determina se o navegador aceita cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 92%

---

# Suporte a cookies

A [dimensão](overview.md) de &#39;Suporte a cookies&#39; informa se o navegador aceita cookies para uma determinada ocorrência. É útil determinar a proporção de visitantes que usam navegadores que aceitam cookies e aqueles que os desabilitam intencionalmente.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`k`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement tenta definir um cookie chamado `s_cc`, e então detecta se o cookie existe. O resultado é o valor do parâmetro da sequência de consulta `Y` (se o navegador aceitar e tiver cookies habilitados) ou `N` (se o navegador tiver cookies desabilitados). Se você utilizar o AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará automaticamente. Se você utilizar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o `k` parâmetro da sequência de consulta em cada ocorrência com um valor de `Y` ou `N`.

## Itens de dimensão

Os itens de dimensão incluem `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: o navegador aceita cookies e os habilita.
* **`Disabled`**: o navegador não aceita cookies ou o visitante os desabilitou.
* **`Unknown`**: o AppMeasurement não pôde determinar o suporte a cookies. A sequência de consulta `k` não estava presente na solicitação de imagem.
