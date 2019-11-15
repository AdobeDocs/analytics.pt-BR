---
description: Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.
solution: Analytics
subtopic: Processing rules
title: Preencher termos de pesquisa interna usando um parâmetro da cadeia de caracteres de consulta
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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

