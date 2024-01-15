---
description: Você pode fazer a correspondência de valores comparando-os a erros comuns de ortografia e atualizá-los para exibi-los corretamente nos relatórios.
subtopic: Processing rules
title: Limpar valores em um relatório
feature: Admin Tools
role: Admin
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 100%

---

# Limpar valores em um relatório

Você pode fazer a correspondência de valores comparando-os a erros comuns de ortografia e atualizá-los para exibi-los corretamente nos relatórios.

Para assegurar que você não corresponda a outros valores acidentalmente, use a opção de correspondência mais restritiva disponível. Você pode executar um relatório sobre a variável (prop1 no exemplo a seguir) e pesquisar os termos que seleciona para substituir e assegurar-se de que não ocorra a correspondência com valores não desejados. As comparações de strings não distinguem maiúsculas de minúsculas.

| Conjunto de regras | Valor |
|---|---|
| Condição | Se prop1 começar com compras |
| Ação | Substituir valor de prop1 como compra com valor personalizado |

Por exemplo:

![](assets/clean-up-values-in-report.png)
