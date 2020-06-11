---
title: eVar (merchandising)
description: Variáveis personalizadas que se vinculam à dimensão de produtos.
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 25%

---


# eVar (merchandising)

*Esta página de ajuda descreve como as eVars de comercialização funcionam como uma dimensão. Para obter informações sobre como implementar eVars de comercialização, consulte[eVars](/help/implement/vars/page-vars/evar.md)no guia Implementar usuário.*

Ao medir o êxito de campanhas externas ou termos de pesquisa externos, normalmente você deseja um único valor para receber crédito por qualquer evento bem-sucedido que possa ocorrer. Por exemplo, se um cliente clica em um link de uma campanha de email para visitar seu site, todas as compras efetuadas como resultado devem ser creditadas à campanha.

E quanto aos eventos que são impulsionados pela pesquisa interna ou pela navegação por categorias quando um cliente procura por vários itens? For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![Exemplo de óculos](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to the to their cart:

![Exemplo de casaco](assets/merch-example-coat.png)

Quando o visitante concluir essa compra, você terá uma pesquisa interna por `"winter coat"` creditada com a compra de um par de óculos (considerando que a eVar usa a alocação padrão de &quot;Mais recente&quot;). Good for `"winter coat"`, but bad for marketing decisions:

| Termo de pesquisa interna | Receita |
|---|---|
| casaco de inverno | $157 |

## Como as variáveis de comercialização resolver esse problema

As eVars de comercialização permitem que você atribua o valor atual de uma eVar a um produto no momento em que um evento bem-sucedido ocorre. Este valor permanece vinculado ao produto, mesmo se um ou mais valores novos forem definidos posteriormente para essa eVar específica.

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is tied to the snow goggles, and the search term `"winter coat"` is tied to the down jacket. As eVars de comercialização alocam receita no nível do produto, de modo que cada termo recebe crédito pela quantia de receita do produto ao qual o termo foi associado:

| Termo de pesquisa interna | Receita |
|---|---|
| casaco de inverno | $119 |
| óculos | $38 |

Consulte eVars [de comercialização](/help/implement/vars/page-vars/evar-merchandising.md) para obter instruções de implementação.

## Instâncias em variáveis de merchandising

A métrica [Instâncias](../metrics/instances.md) não é recomendada para uso em variáveis de comercialização.

* Para variáveis de comercialização que usam sintaxe de produto, as instâncias não são aumentadas.
* Para variáveis de comercialização que usam a sintaxe de variável de conversão, as instâncias são contadas cada vez que a eVar é definida. No entanto, ele atribui ao valor da dimensão, a menos `"None"` que tudo o seguinte ocorra na mesma ocorrência:
   * A eVar de comercialização é definida com um valor.
   * A `products` variável é definida com um valor.
   * Um evento de vinculação está configurado.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Como a maioria dos casos de uso para a sintaxe de variável de conversão requer a eVar e a variável products em ocorrências diferentes, o uso da métrica &#39;Instâncias&#39; não é realista.
