---
title: Java habilitado
description: Determina se o Java está habilitado no navegador.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '249'
ht-degree: 51%
---
# Java habilitado

A [dimensão](overview.md) &#39;Java ativado&#39; determina se o navegador tem Java ativado no momento. É útil nos casos em que você deseja introduzir a funcionalidade baseada em Java no seu site e deseja saber quantos visitantes já têm o Java habilitado. Para aqueles que têm o Java desabilitado, você pode fornecer uma alternativa ou instruções sobre como habilitá-lo.

## Preencher esta dimensão com dados

Java ativado é coletado automaticamente, no lado do cliente: o AppMeasurement detecta se o Java está ativado no navegador e relata &quot;Y&quot; ou &quot;N&quot;. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir. Se você coletar dados fora do AppMeasurement ou da Web SDK (por exemplo, por meio da API), envie &quot;Y&quot; ou &quot;N&quot; para usar essa dimensão.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | Nenhum (coletado automaticamente) |
| **Parâmetro de consulta** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 1 byte |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão são “Habilitado”, “Desabilitado” e “Desconhecido”.

* **Habilitado**: o Java está habilitado no navegador. A sequência de consulta `v` continha o valor “Y”.
* **Desativado**: o Java está desativado no navegador ou o navegador não é compatível com o Java. A sequência de consulta `v` continha o valor “N”.
* **Desconhecido**: o AppMeasurement não pôde determinar a compatibilidade com o Java. A sequência de consulta `v` não estava presente na solicitação de imagem.
