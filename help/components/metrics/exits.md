---
title: Saídas
description: Um exemplo do último valor em uma visita.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 88%
---
# Saídas

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como as saídas funcionam como uma métrica. Para obter informações sobre como as saídas funcionam como uma dimensão, consulte [Dimensões de Saída](../dimensions/exit-dimensions.md).*

>[!ENDSHADEBOX]

A [métrica](overview.md) de &quot;Saídas&quot; mostra o número de vezes que um determinado item de dimensão é capturado como o último valor em uma visita. Essa métrica ajuda a entender melhor sobre a última coisa que os visitantes veem antes de sair do site. Ver os últimos valores de uma dimensão pode ajudar a entender e otimizar a experiência que um visitante recebe antes de sair.

## Como essa métrica é calculada

Depois que uma [visita](visits.md) for concluída, registre o item de dimensão mais recente como uma saída. Existe apenas uma saída por dimensão por visita. Não é necessariamente o último hit da visita se a dimensão foi definida em hits anteriores. É uma métrica com base em visitas; ela se aplica retroativamente a todos os hits na visita.

>[!TIP]
>
>Se essa métrica for visualizada em relação a uma dimensão que nem sempre está definida para todas as visitas, é possível ocultar o item de dimensão “Não especificado” no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
