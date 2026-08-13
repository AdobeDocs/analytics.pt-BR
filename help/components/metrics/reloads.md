---
title: Recargas
description: O número de vezes que a página foi recarregada.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 21%

---

# Recargas

A [métrica](overview.md) de &quot;Recargas&quot; mostra o número de vezes que um item de dimensão foi apresentado durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências nas quais a dimensão [Página](../dimensions/page.md) contém o mesmo valor da ocorrência anterior.

O conceito de recarregamento se aplica à dimensão Página, independentemente da dimensão usada nos relatórios. Por exemplo, se você usar [eVar1](../dimensions/evar.md) como uma dimensão e Recarregar como uma métrica, a tabela mostrará o número de vezes que cada valor de eVar foi apresentado durante um recarregamento (dois valores de página consecutivos). Ela não mostra o número de vezes que dois valores eVar1 consecutivos estavam presentes.
