---
title: Suporte a cookies
description: Determina se o navegador aceita cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 38%
---
# Suporte a cookies

A [dimensão](overview.md) de &#39;Suporte a cookies&#39; informa se o navegador aceita cookies para uma determinada ocorrência. É útil determinar a proporção de visitantes que usam navegadores que aceitam cookies e aqueles que os desabilitam intencionalmente.

## Preencher esta dimensão com dados

O suporte a cookies é coletado automaticamente, no lado do cliente: o AppMeasurement tenta definir um cookie chamado `s_cc`, e então relata se ele existe — `Y` se o navegador aceitar e tiver cookies habilitados ou `N` se os cookies estiverem desabilitados. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir. Se você coletar dados fora do AppMeasurement ou da Web SDK (por exemplo, por meio da API), envie `Y` ou `N` em cada ocorrência.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | Nenhum (coletado automaticamente) |
| **Parâmetro de consulta** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 1 byte |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: o navegador aceita cookies e os habilita.
* **`Disabled`**: o navegador não aceita cookies ou o visitante os desabilitou.
* **`Unknown`**: o AppMeasurement não pôde determinar o suporte a cookies. A sequência de consulta `k` não estava presente na solicitação de imagem.
