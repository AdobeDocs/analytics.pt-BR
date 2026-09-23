---
title: Dias desde a última visita
description: O número de dias entre o hit atual e a última visita.
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
TQID: https://experienceleague.adobe.com/VOkdvehFSgp1xBEq49W5FIphzHi8ZCbrsoMnI7rgQMs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 57%
---
# Dias desde a última visita

A [dimensão](overview.md) de &quot;Dias desde a última visita&quot; mede o tempo decorrido entre a ocorrência atual do visitante e sua visita anterior (se houver). Essa dimensão ajuda você a entender o comportamento que os visitantes têm após visitar seu site. Alguns exemplos:

* Com que frequência os usuários visitam novamente o site?
* Como a frequência de retorno está correlacionada com a conversão? Os compradores recorrentes visitam com frequência ou pouca frequência?
* Os usuários que clicam nas campanhas retornam com frequência?

Novos visitantes não são incluídos nessa dimensão.

## Preencher esta dimensão com dados

O Adobe calcula essa dimensão do lado do servidor a partir do histórico de visitas do visitante. Não há variável a ser definida; isso funciona imediatamente em todas as implementações.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (calculado pela Adobe) |
| **Web SDK / campo XDM** | Nenhum (calculado pela Adobe) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a última visita de um visitante e o hit atual. Cada número de dias é um item de dimensão separado, com `"Same day"` ocorrendo quando a última visita e o hit atual acontecem no mesmo dia.
