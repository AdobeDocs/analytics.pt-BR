---
description: Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.
subtopic: Processing rules
title: Preencher termos de pesquisa interna usando um parâmetro da cadeia de caracteres de consulta
feature: Admin Tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '115'
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
