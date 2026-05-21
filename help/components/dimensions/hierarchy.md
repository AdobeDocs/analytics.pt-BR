---
title: Hierarquia
description: (Desativado) Uma dimensão personalizada que você pode usar nos relatórios.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 86%

---

# Hierarquia

>[!IMPORTANT]
>
>Esta dimensão foi removida e não é uma [dimensão](overview.md) disponível no Analysis Workspace. Em vez disso, a Adobe recomenda usar [eVars](evar.md) e classificações.

As hierarquias são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas não persistem além da ocorrência definida. Até 5 hierarquias estarão disponíveis se seu contrato com a Adobe permitir.

## Preencher hierarquias com dados

Cada hierarquia coleta dados da [`h1` - `h5` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, o parâmetro da sequência de consulta `h1` coleta dados para Hierarquia 1, enquanto o parâmetro da sequência de consulta `h4` coleta dados para Hierarquia 4.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `hier1` - `hier5`. Consulte [hier](/help/implement/vars/page-vars/hier.md) no guia de usuário Implementar para obter diretrizes de implementação.

## Itens de dimensão

Como as hierarquias contêm strings personalizadas na implementação, sua organização determina quais itens de dimensão são para cada hierarquia. Registre a finalidade de cada hierarquia e os itens de dimensão típicos em um [documento de design de solução](/help/implement/prepare/solution-design.md).
