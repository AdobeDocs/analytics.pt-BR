---
description: Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.
subtopic: Processing rules
title: Preencher termos de pesquisa interna usando um parâmetro da cadeia de caracteres de consulta
feature: Admin Tools
role: Admin
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%

---

# Preencher termos de pesquisa interna usando um parâmetro da cadeia de caracteres de consulta

Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.

Os valores de sequência de consulta precisam estar codificados em unicode ou UTF-8 para serem lidos pelas regras de processamento.

| Conjunto de regras | Valor |
|---|---|
| Condição | Se o parâmetro da string de consulta q estiver definido |
| Ação | Substitui o valor dos temos de pesquisa interna por parâmetro da string de consulta q |

Por exemplo:

![](assets/populate-internal-search-terms.png)
