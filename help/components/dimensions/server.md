---
title: Servidor
description: O nome do servidor.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 92%

---

# Servidor

A [dimensão](overview.md) &#39;Servidor&#39; geralmente lista o nome de host do site. Para conjuntos de relatórios que combinam vários domínios ou subdomínios, essa dimensão é útil para analisar quais domínios ou subdomínios têm o melhor desempenho.

Essa dimensão está relacionada às dimensões [Página](page.md) e [Seções do site](site-section.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`server` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável [`server`](/help/implement/vars/page-vars/server.md).

## Itens de dimensão

Os itens de dimensão incluem servidores no site. A organização escolhe quais itens de dimensão específicos quer utilizar. Algumas organizações utilizam `window.location.hostname`, enquanto outras formulam valores personalizados. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).
