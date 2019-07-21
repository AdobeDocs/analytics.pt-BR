---
description: Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.
seo-description: Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.
seo-title: Preencher termos de pesquisa interna usando um parâmetro da string de consulta
solution: Analytics
subtopic: Regras de processamento
title: Preencher termos de pesquisa interna usando um parâmetro da string de consulta
topic: Ferramentas administrativas
uuid: 05 ae 2 b 0 a -8797-468 c -8 f 59-643 beac 614 c 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Preencher termos de pesquisa interna usando um parâmetro da string de consulta

Se você usar uma variável comum, como q, para preencher termos de pesquisa, poderá usar regras de processamento para preencher o eVar de termos de pesquisa interna com esses valores.

Os valores de sequência de consulta precisam estar codificados em unicode ou UTF-8 para serem lidos pelas regras de processamento.

| Conjunto de regras | Valor |
|---|---|
| Condição | Se o parâmetro da string de consulta q estiver definido |
| Ação | Substitui o valor dos temos de pesquisa interna por parâmetro da string de consulta q |

Por exemplo:

![](assets/populate-internal-search-terms.png)

