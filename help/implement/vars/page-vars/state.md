---
title: estado
description: (Desativado) Preencheu o "Relatório de estado do visitante", que não está mais disponível.
feature: Appmeasurement Implementation
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
TQID: https://experienceleague.adobe.com/3GhnJJj6gxEt0Qiefd4siS6-YzDbOw4hdY4IsNhwYDU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 87%

---

# estado

>[!IMPORTANT]
>
>Essa variável foi removida e não é uma dimensão disponível no Analysis Workspace. Em vez disso, use a dimensão [Estados dos EUA](/help/components/dimensions/us-states.md), que a AppMeasurement coleta automaticamente com base na localização do visitante.

Em versões anteriores do Adobe Analytics, a variável `state` era usada quando os visitantes preenchiam as informações de envio em sites de varejo. É funcionalmente idêntica a uma prop, mas não está disponível no Analysis Workspace.

## Estado usando a extensão do Adobe Analytics

Você pode definir o estado ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Estado].

Você pode definir o estado como qualquer valor do tipo string ou elemento de dados.

## s.state no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.state` é uma string que normalmente contém o estado ou província do visitante. Nomes completos de estados ou códigos de duas letras são válidos. A variável tem um valor máximo de 50 bytes; valores mais longos são truncados. Seu valor padrão é uma string vazia.

```js
s.state = "Utah";
```
