---
description: Práticas recomendadas do Power BI.
title: Práticas recomendadas
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# Práticas recomendadas

## Preservar referências nas visualizações do Power BI

Quando você cria uma solicitação, ela sempre terá a mesma referência no Power BI. Mas caso exclua uma solicitação, a referência será usada por uma nova solicitação que for criada para a mesma dimensão.

Se você excluir uma solicitação da sua pasta de trabalho, certifique-se de que não há uma visualização apontando para ela no Power BI; caso contrário, a visualização falhará.

* Se for possível, não exclua solicitações que você tenha criado no Report Builder
* Caso exclua solicitações no Report Builder, certifique-se também de excluir a visualização correspondente no Power BI.
* Caso não tenha certeza: exclua solicitações que não serão mais necessárias, republique-as e acesse o Power BI para ver quais visualizações foram quebradas
