---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.currencyCode

A variável determina a taxa de conversão a ser aplicada na receita.

Todos os valores monetários são armazenados em uma moeda de sua escolha. Se essa moeda for a mesma que a especificada em *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | cc | Conversão &gt; Compras &gt; Receita Todos os relatórios de conversão mostrando valores monetários ou Receita | "USD" |

Se seu site permite que visitantes comprem em várias moedas, você deverá usar a variável *`currencyCode`* para garantir que a receita seja armazenada na moeda apropriada. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. Assim que a coleta de dados receber os dados, usará a taxa de conversão atual para converter os 40 euros no valor equivalente em dólares americanos.

Se você vende em várias moedas, é recomendável preencher a variável *`currencyCode`* na página HTML, em vez de no arquivo JavaScript. Se você quiser usar suas próprias taxas de conversão em vez das taxas de conversão usadas pela Adobe, defina a moeda *`currencyCode`* para igualar a moeda base do conjunto de relatórios. Em seguida, converta toda a receita antes de enviá-la para o [!DNL Analytics].

A conversão de moeda se aplica a receita e a qualquer evento de moeda. Esses são eventos usados para somar valores semelhantes à receita, como impostos e remessa. Os eventos de receita e moeda são especificados na string dos produtos. Para obter informações sobre produtos, consulte [events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

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

* Se você perceber valores surpreendentemente altos de receita nos relatórios, verifique se a variável *`currencyCode`* e a moeda de base do conjunto de relatórios estão definidas corretamente.
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* Os eventos de moeda não devem ser usados para fins não relacionados a moeda. Se você precisar contar valores arbitrários ou dinâmicos que não são moeda, use o tipo de evento [!UICONTROL numérico].
* Quando a variável *`currencyCode`* estiver em branco, nenhuma conversão será aplicada.

Para obter mais informações, consulte Códigos [de moeda](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html).
