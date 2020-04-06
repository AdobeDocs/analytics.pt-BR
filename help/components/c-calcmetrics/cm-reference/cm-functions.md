---
description: O Criador de métricas calculadas permite aplicar funções matemáticas e estatísticas para criar Métricas calculadas avançadas.
title: 'Referência: funções básicas'
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aeab78
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Referência: funções básicas

O Criador de métricas calculadas permite aplicar funções matemáticas e estatísticas para criar Métricas calculadas avançadas.

Veja uma lista em ordem alfabética das funções e suas definições.

>[!NOTE] Sempre que [!DNL metric] for definida como um argumento em uma função, outras expressões de métricas também serão permitidas. Por exemplo, [!DNL MAXV(metrics)] também permite [!DNL MAXV(PageViews + Visits).]

## Funções de tabela versus Funções de linha {#section_8977BE40A47E4ED79EB543A9703A4905}

Uma função de tabela é aquela em que a saída é a mesma para cada linha da tabela. Uma função de linha é aquela em que a saída é diferente para cada linha da tabela.

## Valor absoluto (Linha) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Retorna o valor absoluto de um número. O valor absoluto de um número é o número com um valor positivo.

```
ABS(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | A métrica para a qual você deseja o valor absoluto. |

## Máximo da coluna {#concept_B25518D717D24F82B65CDE49A153D3A3}

Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. O MAXV avalia verticalmente em uma única coluna (métrica) pelos elementos de dimensão.

```
MAXV(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | Uma métrica que você gostaria de avaliar. |

## Mínimo da coluna {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. O MINV avalia verticalmente em uma única coluna (métrica) pelos elementos de dimensão.

```
MINV(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | Uma métrica que você gostaria de avaliar. |

## Soma da coluna {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão).

```
SUM(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | A métrica para a qual você deseja obter o valor total ou a soma. |

## Contagem (Tabela) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Retorna o número, ou contagem, de valores diferentes de zero de uma métrica em uma coluna (o número de elementos únicos informados em uma dimensão).

```
COUNT(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | A métrica que você deseja contar. |

## Expoente (Linha) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | The exponent applied to the base *e*. |

## Exponenciação {#concept_941578534F1E4583B1BEB067C8113A21}

Operador de potência

<pre>
pow(x,y) = x <sup>y</sup> = x*x*x*... (y vezes)
</pre>

## Média (Tabela) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Retorna a média aritmética, ou média, de uma métrica em uma coluna.

```
MEAN(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | A métrica para a qual você deseja a média. |

## Mediana (Tabela) {#concept_183EC31208524EDB8463D986DE2E895F}

Retorna a mediana de uma métrica em uma coluna. A mediana é o número presente no meio de um conjunto de números, ou seja, metade dos números apresentam valores maiores ou iguais à mediana e metade são menores ou iguais à mediana.

```
MEDIAN(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | A métrica para a qual você deseja a mediana. |

## Módulo {#concept_DE0825D7A51643219CB01F59667EA352}

O restante de col1 / col2, usando a divisão Euclidiana.

Retorna o restante após dividir x por y.

```
x = floor(x/y) + modulo(x,y)
```

O valor de retorno tem o mesmo sinal que a entrada (ou é zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Para obter sempre um número positivo, use

```
modulo(modulo(x,y)+y,y)
```

## Percentil (Tabela) {#concept_51DF57B606D14F898E5010DBA61CA979}

Retorna o k-ésimo percentil dos valores de uma métrica. É possível usar essa função para estabelecer um limite de aceitação. Por exemplo, é possível analisar elementos de dimensão com pontuação acima do percentil 90.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> A coluna métrica que define a posição relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> O valor percentil no intervalo de 0 a 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartil (Tabela) {#concept_BFD37F0F23A24AD181407142233FA151}

Retorna o quartil de valores de uma métrica. Por exemplo, os quartis podem ser usados para encontrar os 25% principais dos produtos que geram a maior parte da receita. MINV, MEDIAN e MAXV retornam o mesmo valor como QUARTIL quando o quartil é igual a 0 (zero), 2 e 4, respectivamente.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>métrica</i> </td> 
   <td colname="col2"> A métrica para a qual você deseja o valor do quartil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quarto </p> </td> 
   <td colname="col2"> Indica qual *valor retornar. </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. Se *quart* = 1, QUARTIL retorna o primeiro quartil (percentil 25). Se *quart* = 2, QUARTIL retorna o primeiro quartil (percentil 50). Se *quart* = 3, QUARTIL retorna o primeiro quartil (percentil 75). Se *quart* = 4, QUARTIL retorna o valor máximo.

## Arredondar {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Retorna o número inteiro mais próximo para um determinado valor. Por exemplo, caso você não queira relatar os decimais na receita e um produto apresentar um valor de US$569,34, use a fórmula Arredondar( *Receita*) para arredondar a receita para o número inteiro mais próximo; neste caso, US$569. Um relatórios de produto de US$ 569,51 será arredondado para o dólar mais próximo, ou seja, US$ 570.

```
ROUND(metric)
```

| Argumento | Descrição |
|---|---|
| *número* | A métrica que deseja arredondar. |

Um número redondo sem um parâmetro de dígitos é igual a um número redondo com um parâmetro de dígitos igual a 0, arredondado para o número inteiro mais próximo.  Ele retorna, com um parâmetro de dígitos, a quantidade de dígitos à direita do decimal. Se o dígito for negativo, ele retorna os zeros à esquerda do decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Contagem de linhas {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Retorna a contagem de linhas de uma determinada coluna (o número de elementos únicos relatados em uma dimensão). Os valores &quot;únicos excedidos&quot; são contados como 1.

## Máx. da linha {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

O número máximo de colunas em cada linha.

## Mín. da linha {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

O número mínimo de colunas em cada linha.

## Soma da linha {#concept_E9EAB0FC5233498F907E7A078698A98E}

A soma das colunas em cada linha.

## Raiz quadrada (Linha) {#concept_6460DFA51EC24527A2317970FB76D404}

Retorna a raiz quadrada positiva de um número. A raiz quadrada de um número é o valor dele elevado à potência de 1/2.

```
SQRT(metric)
```

| Argumento | Descrição |
|---|---|
| *número* | A métrica para a qual você deseja a raiz quadrada. |

## Desvio padrão (Tabela) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Retorna o desvio padrão, ou a raiz quadrada da variação, baseada em uma amostra da população de dados.

A equação para STDEV é:

![](assets/std_dev.png)

onde x é a média da amostra (*métrica*) e *n* é o tamanho da amostra.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argumento</b> </td> 
   <td> <b> Descrição</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> métrica</i></b> </td> 
   <td> <p> A métrica para a qual você deseja o desvio padrão. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variação (Tabela) {#concept_269751EDC5A34E689112AE16E04A11B0}

Retorna a variação baseada em uma amostra da população de dados.

A equação para VARIANCE é:

![](assets/variance_eq.png)

onde x é a média da amostra, MEAN(*métrica*) e *n* é o tamanho da amostra.

```
VARIANCE(metric)
```

| Argumento | Descrição |
|---|---|
| *métrica* | A métrica para a qual você deseja a variação. |

Para calcular uma variação, você deve observar uma coluna inteira de números. A partir dessa lista de números, calculamos primeiro a média. Depois que você tiver a média, percorra cada entrada e faça o seguinte:

1. Subtraia a média do número.

2. Eleve o resultado ao quadrado.

3. Adicione-o ao total.

Depois de repetir a coluna inteira, você terá um único total. Em seguida, divida esse total pelo número de itens na coluna. Esse número é a variação da coluna. É um número único. No entanto, é exibido como uma coluna de números.

Por exemplo, digamos que você tenha uma coluna de três itens:

1

2

3

A média dessa coluna é 2. A variação da coluna será ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. Na Análise Ad Hoc, isso terá a seguinte aparência:

1 2/3

2 2/3

3 2/3
