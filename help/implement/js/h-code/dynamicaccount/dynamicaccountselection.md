---
title: dynamicAccountSelection
description: A variável dynamicAccountSelection habilita ou desabilita a seleção de conta dinâmica.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
TQID: 'https://experienceleague.adobe.com/tne4K1ppeYbWGckTmuJy0f8Bjdw9WvGbjrOSKs4RXlk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%
---
# dynamicAccountSelection

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas AppMeasurement atuais ou com a Coleção de dados da Adobe Experience Platform.

A variável `dynamicAccountSelection` é um booleano que determina se a seleção dinâmica da conta é usada.

Se definida como `true`, o arquivo JavaScript procurará `dynamicAccountMatch` e `dynamicAccountList`.

Se definida como `false`, ou se essa variável não estiver definida, as variáveis `dynamicAccountMatch` e `dynamicAccountList` serão ignoradas.

Se essa variável não estiver definida, o valor padrão será `false`.

## Sintaxe

```js
s.dynamicAccountSelection = [boolean];
```

## Exemplo

```js
s.dynamicAccountSelection = true;
```
