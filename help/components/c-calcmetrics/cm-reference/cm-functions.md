---
title: Funções básicas
description: Saiba mais sobre funções básicas de métricas calculadas.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 92%

---

# Funções básicas


O [Construtor de métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) permite aplicar funções matemáticas e estatísticas. Este artigo documenta uma lista em ordem alfabética das funções e suas definições.

>[!NOTE]
>
>Sempre que [!DNL metric] for definida como um argumento em uma função, outras expressões de métricas também serão permitidas. Por exemplo, [COLUMN MAXIMUM(metrics)](#column-maximum) também permite [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Funções de tabela versus funções de linha

Uma função de tabela exibe um resultado igual para cada linha da tabela. Uma função de linha exibe um resultado diferente para cada linha da tabela.

Quando aplicável e relevante, uma função é anotada com o tipo de função: [!BADGE Tabela]{type="Neutral"} ou [!BADGE Linha]{type="Neutral"}

## O que significa o parâmetro “incluir zeros”?

Informa se os zeros devem ou não ser incluídos no cálculo. Às vezes, zero significa *nada*, mas em alguns casos, pode ser importante.

Por exemplo, se você possuir uma métrica Receita e adicionar a métrica Visualizações de página ao relatório, aparecerão mais linhas com valores iguais a zero na sua receita. Você provavelmente não vai querer que essa métrica adicional afete qualquer **[MÉDIA](cm-functions.md#mean)**, **[MÍNIMO DA LINHA](cm-functions.md#row-min)**, **[QUARTIL](cm-functions.md#quartile)** e outros cálculos que você tenha na coluna receita. Neste caso, você deverá marcar o parâmetro `include-zeros`.

Um cenário alternativo é o que você tem duas métricas de interesse e uma tem uma média ou um mínimo mais alto porque algumas das linhas são zeros.  Nesse caso, você pode optar por não marcar o parâmetro para incluir zeros



## Valor absoluto {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="Valor absoluto"
>abstract="Retorna o valor absoluto de um número. O valor absoluto de um número é o número com um valor positivo."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Linha]{type="Neutral"} Retorna o valor absoluto de um número. O valor absoluto de um número é o número com um valor positivo.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja obter o valor absoluto. |


## Máximo da coluna {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="Máximo da coluna"
>abstract="Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. O MAXV é avaliado verticalmente em uma única coluna (métrica) nos elementos de dimensão."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. O MAXV é avaliado verticalmente em uma única coluna (métrica) nos elementos de dimensão.

| Argumento | Descrição |
|---|---|
| métrica | Precisa de pelo menos uma métrica, mas pode usar quantas métricas forem necessárias como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Mínimo da coluna {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="Mínimo da coluna"
>abstract="Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. O MINV é avaliado verticalmente em uma única coluna (métrica) nos elementos de dimensão."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. O MINV é avaliado verticalmente em uma única coluna (métrica) nos elementos de dimensão.

| Argumento | Descrição |
|---|---|
| métrica | Precisa de pelo menos uma métrica, mas pode usar quantas métricas forem necessárias como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Soma da coluna {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="Soma da coluna"
>abstract="Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão)."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão).

| Argumento | Descrição |
|---|---|
| métrica | Precisa de pelo menos uma métrica, mas pode usar quantas métricas forem necessárias como parâmetros. |


## Contagem {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="Contagem"
>abstract="Retorna o número, ou contagem, de valores diferentes de zero de uma métrica em uma coluna (o número de elementos únicos informados em uma dimensão)."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Tabela]{type="Neutral"} Retorna o número ou a contagem de valores diferentes de zero para uma métrica em uma coluna (o número de elementos exclusivos relatados em uma dimensão).

| Argumento | Descrição |
|---|---|
| métrica | A métrica que deseja contar. |


## Expoente {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="Expoente"
>abstract="Retorna e elevado à potência de um determinado número. A constante e é igual a 2,71828182845904, a base do logaritmo natural. EXPONENT é o inverso de LN, o logaritmo natural de um número."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE Linha]{type="Neutral"} Retorna e elevado à potência de um determinado número. A constante e é igual a 2,71828182845904, a base do logaritmo natural. EXPONENT é o inverso de LN, o logaritmo natural de um número.

| Argumento | Descrição |
|---|---|
| métrica | O exponente aplicado à base e. |


## Média {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="Média"
>abstract="Retorna a média aritmética, ou média, de uma métrica em uma coluna"

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Retorna a média aritmética, ou a média, de uma métrica em uma coluna.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja obter a média. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Mediana {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="Mediana"
>abstract="Retorna a mediana de uma métrica em uma coluna. A mediana é o número no meio de um conjunto de números. Ou seja, metade dos números tem valores maiores ou iguais à mediana e metade é menor ou igual à mediana."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Retorna a mediana de uma métrica em uma coluna. A mediana é o número no meio de um conjunto de números. Ou seja, metade dos números tem valores maiores ou iguais à mediana e metade é menor ou igual à mediana.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja obter a mediana. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Módulo {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="Módulo"
>abstract="Retorna o resto após dividir x por y usando a divisão euclidiana. "

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Retorna o resto após dividir x por y usando a divisão euclidiana.

| Argumento | Descrição |
|---|---|
| metric_X | A primeira métrica que você deseja dividir. |
| metric_Y | A segunda métrica que você deseja dividir. |

### Exemplos

O valor retornado tem o mesmo sinal que a entrada (ou é zero).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Para obter sempre um número positivo, use

```
MODULO(MODULO(x,y)+y,y)
```

## Percentil {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="Percentil"
>abstract="Retorna o enésimo percentual, que é um valor entre 0 e 100. Quando n &lt; 0, a função usa zero. Quando n > 100, a função retorna 100."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Retorna o enésimo percentual, que é um valor entre 0 e 100. Quando n &lt; 0, a função usa zero. Quando n > 100, a função retorna 100.

| Argumento | Descrição |
|---|---|
| métrica | O valor do percentil no intervalo de 0 a 100, incluso. |
| k | A coluna de métrica que define a posição relativa. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |



## Operador de potência {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="Operador de potência"
>abstract="Retorna x elevado à potência y."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

Retorna x elevado à potência y.

| Argumento | Descrição |
|---|---|
| metric_X | A métrica que você deseja elevar à potência metric_Y. |
| metric_Y | A potência à qual você deseja elevar a metric_X. |


## Quartil {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="Quartil"
>abstract="Retorna o quartil de valores de uma métrica. Por exemplo, os quartis podem ser usados para encontrar a porcentagem de 25% dos produtos com maior receita. "

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Retorna o quartil dos valores de uma métrica. Por exemplo, os quartis podem ser usados para encontrar a porcentagem de 25% dos produtos com maior receita. [MÍNIMO DA COLUNA](#column-minimum), [MEDIANA](#median) e [MÁXIMO DA COLUNA](#column-maximum) retornam o mesmo valor que [QUARTIL](#quartile) quando o quartil é igual a `0` (zero), `2` e `4`, respectivamente.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja obter o valor do quartil. |
| quartil | Indica qual valor de quartil retornar. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Arredondar {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="Arredondar"
>abstract="Arredondar sem um parâmetro *numérico* é igual a arredondar com um parâmetro *numérico* de 0, ou seja, arredondar para o número inteiro mais próximo. Com um parâmetro *numérico*, ARREDONDAR retorna os dígitos *numéricos* à direita do separador decimal.  Se o *número* for negativo, retornará zeros à esquerda do separador decimal."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

Arredondar sem um parâmetro *numérico* é igual a arredondar com um parâmetro *numérico* de 0, ou seja, arredondar para o número inteiro mais próximo. Com um parâmetro *numérico*, ARREDONDAR retorna os dígitos *numéricos* à direita do separador decimal.  Se o *número* for negativo, retornará zeros à esquerda do separador decimal.

| Argumento | Descrição |
|---|---|
| metric | A métrica que deseja arredondar. |
| número | Quantos dígitos à direita do separador decimal devem retornar. (Se negativo, retorna zeros à esquerda do separador decimal). |

### Exemplos

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## Contagem de linhas {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="Contagem de linhas"
>abstract="Retorna a contagem de linhas referente a uma determinada coluna (o número de elementos únicos relatados em uma dimensão). *Únicos excedidos* é contado como 1."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

Retorna a contagem de linhas referente a uma determinada coluna (o número de elementos únicos relatados em uma dimensão). *Únicos excedidos* é contado como 1.


## Máx. de linhas {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="Máx. de linhas"
>abstract="O máximo de colunas de cada linha."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

O máximo de colunas de cada linha.

| Argumento | Descrição |
|---|---|
| métrica | Precisa de pelo menos uma métrica, mas pode usar quantas métricas forem necessárias como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Mín. de linhas {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="Mín. de linhas"
>abstract="O mínimo de colunas de cada linha."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

O mínimo de colunas de cada linha.

| Argumento | Descrição |
|---|---|
| métrica | Precisa de pelo menos uma métrica, mas pode usar quantas métricas forem necessárias como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |



## Soma da linha {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="Soma da linha"
>abstract="A soma das colunas em cada linha."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

A soma das colunas em cada linha.

| Argumento | Descrição |
|---|---|
| métrica | Precisa de pelo menos uma métrica, mas pode usar quantas métricas forem necessárias como parâmetros. |


## Raiz quadrada {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="Raiz quadrada"
>abstract="Retorna a raiz quadrada positiva de um número. A raiz quadrada de um número é o valor desse número elevado à potência de 1/2."

<!-- markdownlint-enable MD034 -->


![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Linha]{type="Neutral"} Retorna a raiz quadrada positiva de um número. A raiz quadrada de um número é o valor desse número elevado à potência de 1/2.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja obter a raiz quadrada. |


## Desvio padrão {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="Desvio padrão"
>abstract="Retorna o desvio padrão, ou a raiz quadrada da variação, baseada em uma amostra da população de dados."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Retorna o desvio padrão, ou a raiz quadrada da variação, com base em uma população de dados de exemplo.

| Argumento | Descrição |
|---|---|
| | A métrica para a qual você deseja obter o desvio padrão. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Variância {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="Variância"
>abstract="Retorna a variância baseada em uma amostra da população de dados."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Retorna a variação com base em uma população de dados de exemplo.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja obter a variação. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


A equação de VARIAÇÃO é:

![](assets/variance_eq.png){width="100"}

Onde *x* é a média da amostra, [MEAN(*metric*)](#mean), e *n* é o tamanho da amostra.


Para calcular uma variação, considere uma coluna inteira de números. Nessa lista de números, calcule primeiro a média. Após obter a média, analise cada entrada e faça o seguinte:

1. Subtraia a média do número.

1. Eleve o resultado ao quadrado.

1. Adicione-o ao total.

Quando você iterar por toda a coluna, terá um total único. Depois, divida o total pelo número de itens na coluna. Esse número é a variação da coluna. É um número único. No entanto, é exibido como uma coluna de números.

No exemplo da seguinte coluna de três itens:

| coluna |
|:---:|
| 1 |
| 2 |
| 3 |

A média dessa coluna é 2. A variação da coluna será ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->