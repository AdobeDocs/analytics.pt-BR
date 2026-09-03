---
description: Práticas recomendadas do Power BI.
title: Práticas recomendadas
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
TQID: https://experienceleague.adobe.com/WXvRDft1TRz5qM9R8Psz-Yp2qY-AL-SrrXgXWRx55N0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 55%

---

# Práticas recomendadas

{{legacy-arb}}

## Preservar referências nas visualizações do Power BI

Depois de criar uma solicitação, ela sempre terá a mesma referência no Power BI. Mas se você excluir uma solicitação, a referência será usada por uma nova solicitação criada para a mesma dimensão.

Se você excluir uma solicitação da sua pasta de trabalho, certifique-se de que não há uma visualização apontando para ela no Power BI; caso contrário, a visualização falhará.

* Se for possível, não exclua solicitações que você tenha criado no Report Builder
* Caso exclua solicitações no Report Builder, certifique-se também de excluir a visualização correspondente no Power BI.
* Se não tiver certeza: exclua solicitações de que você não precisa mais, publique novamente e acesse o Power BI para ver quais visualizações foram corrompidas
