---
title: Aceitação no gerenciamento de Consentimento
description: Veja em quais configurações de privacidade um visitante optou por participar.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
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
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 90%

---

# Aceitação no gerenciamento de Consentimento

A [dimensão](overview.md) da &#39;Aceitação no Gerenciamento de consentimento&#39; exibe as configurações de privacidade para as quais um visitante optou. Você pode usar essa dimensão para filtrar dados com base nas configurações de privacidade ou ver os motivos mais comuns de aceitação de privacidade.

## Preencher esta dimensão com dados

Essa dimensão coleta dados das seguintes [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` quando definido como `Y`. Se `opt.dmp` igual a `N`, a dimensão [Recusa do gerenciamento de consentimento](cm-opt-out.md) é preenchida.
* `contextData.['opt.sell']` quando definido como `Y`. Se `opt.sell` igual a `N`, a dimensão [Recusa do gerenciamento de consentimento](cm-opt-out.md) é preenchida.

Sua organização determina a lógica para implementar essas variáveis de dados de contexto. Eles não persistem além da ocorrência em que estão definidos, portanto, é necessário definir cada variável de dados de contexto em cada página.

## Itens de dimensão

Os itens de dimensão incluem os dois valores a seguir:

* **`DMP`**: o visitante optou por compartilhar nas plataformas de gerenciamento de dados. Esse item de dimensão está presente quando a variável de dados de contexto `opt.dmp` é igual a `Y`.
* **`SELL`**: o visitante optou por compartilhar ou vender os dados a terceiros. Essa dimensão está presente quando a variável de dados de contexto `opt.sell` é igual a `Y`.
