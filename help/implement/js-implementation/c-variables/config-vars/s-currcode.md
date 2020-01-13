---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.currencyCode

A variável determina a taxa de conversão a ser aplicada na receita.

Todos os valores monetários são armazenados em uma moeda de sua escolha. Se essa moeda for a mesma especificada em *`currencyCode`* ou se *`currencyCode`* estiver vazia, nenhuma conversão será aplicada.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/D | cc | Conversão &gt; Compras &gt; Receita  Todos os relatórios de conversão mostrando valores monetários ou Receita | "USD" |

Se seu site permite que visitantes comprem em várias moedas, você deverá usar a variável  *`currencyCode`* para garantir que a receita seja armazenada na moeda apropriada. Por exemplo, se a moeda base do conjunto de relatórios for USD e você vender um item por 40 euros, preencha o *`currencyCode`* com "EUR" na página HTML. Assim que a coleta de dados receber os dados, usará a taxa de conversão atual para converter os 40 euros no valor equivalente em dólares americanos.

Se você vende em várias moedas, é recomendável preencher a variável  *`currencyCode`* na página HTML, em vez de no arquivo JavaScript. Se você quiser usar suas próprias taxas de conversão, em vez das taxas de conversão usadas pela Adobe, defina a *`currencyCode`* para igualar a moeda base do conjunto de relatórios. Em seguida, converta toda a receita antes de enviá-la para o [!DNL Analytics].

A conversão de moeda se aplica a receita e a qualquer evento de moeda. Esses são eventos usados para somar valores semelhantes à receita, como impostos e remessa. Os eventos de receita e moeda são especificados na string dos produtos. Para obter informações sobre produtos, consulte  [events](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/analytics-basics/ref-events.html).

## Sintaxe e valores possíveis

```js
s.currencyCode="currency_code"
```

## Exemplos

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## Configurações

O Adobe [!DNL Customer Care] pode alterar a configuração padrão de moeda de seu conjunto de relatórios. Quando você altera a moeda de base de um conjunto de relatórios, a receita existente no sistema não é convertida. Todos os novos valores de receita serão convertidos apropriadamente.

## Armadilhas, dúvidas e dicas

* Se você notar valores de receita surpreendentemente grandes nos relatórios, verifique se a variável *`currencyCode`* e a moeda base do conjunto de relatórios estão definidas corretamente.
* A variável *`currencyCode`* não é persistente, o que significa que a variável deve ser transmitida na mesma solicitação de imagem que qualquer receita ou outra métrica relacionada à moeda.
* Os eventos de moeda não devem ser usados para fins não relacionados a moeda. Se você precisar contar valores arbitrários ou dinâmicos que não são moeda, use o tipo de evento [!UICONTROL numérico].
* Quando a variável  *`currencyCode`* estiver em branco, nenhuma conversão será aplicada.

Para obter mais informações, consulte [Códigos de moeda](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/currency.html).
