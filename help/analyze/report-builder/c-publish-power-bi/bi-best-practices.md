---
description: Práticas recomendadas do Power BI.
title: Práticas recomendadas
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 97%

---

# Práticas recomendadas

## Preservar referências nas visualizações Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Quando você cria uma solicitação, ela sempre terá a mesma referência no Power BI. Mas caso exclua uma solicitação, a referência será usada por uma nova solicitação que for criada para a mesma dimensão.

Caso exclua uma solicitação da sua pasta de trabalho, tenha certeza de que não há uma visualização apontando para ela no Power BI, pois senão a visualização falhará.

* Se for possível, não exclua solicitações que você tenha criado no Report Builder
* Caso exclua solicitações no Report Builder, certifique-se também de excluir a visualização correspondente no Power BI.
* Caso não tenha certeza: exclua solicitações que não serão mais necessárias, republique-as e acesse o Power BI para ver quais visualizações foram quebradas
