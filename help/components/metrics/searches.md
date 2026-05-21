---
title: Pesquisas
description: O número de vezes que uma ocorrência correspondeu aos critérios de pesquisa externa.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 88%

---

# Pesquisas

A [métrica](overview.md) de &quot;Pesquisas&quot; mostra o número de ocorrências que correspondem à detecção de pesquisa externa da Adobe. Essa métrica é útil quando você quer observar itens de dimensão que não sejam de pesquisa e ver como eles contribuíram para o tráfego do mecanismo de pesquisa.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem à detecção de pesquisa externa da Adobe. Ela deve corresponder ao seguinte:

* O valor do referenciador da ocorrência é um domínio de pesquisa reconhecido pela Adobe
* O URL do referenciador da ocorrência contém um parâmetro de sequência de consulta de palavra-chave. Devido às práticas modernas de privacidade, esse valor da sequência de consulta geralmente fica em branco. A Adobe reconhece sequências de consulta em branco como parte da detecção de pesquisa.
