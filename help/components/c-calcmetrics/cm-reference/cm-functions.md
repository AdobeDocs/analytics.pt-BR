---
description: O Criador de métricas calculadas permite aplicar funções matemáticas e estatísticas para criar Métricas calculadas avançadas.
title: 'Referência: funções básicas'
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aeab78
translation-type: ht
source-git-commit: 83066f8e372fb5f8af3b7db2c165ab1cd8b76a10

---


# Referência: funções básicas

O Criador de métricas calculadas permite aplicar funções matemáticas e estatísticas para criar Métricas calculadas avançadas.

Veja uma lista em ordem alfabética das funções e suas definições.

> [!NOTE] Sempre que [!DNL metric] for definida como um argumento em uma função, outras expressões de métricas também serão permitidas. Por exemplo, [!DNL MAXV(metrics)] também permite [!DNL MAXV(PageViews + Visits).]

## Funções de tabela versus Funções de linha {#section_8977BE40A47E4ED79EB543A9703A4905}

Uma função de tabela exibe um resultado igual para cada linha da tabela. Uma função de linha exibe um resultado diferente para cada linha da tabela.

## Valor absoluto (Linha) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Retorna o valor absoluto de um número. O valor absoluto de um número é o número com um valor positivo.

```
ABS(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter o valor absoluto. |

## Máximo da coluna {#concept_B25518D717D24F82B65CDE49A153D3A3}

Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. MAXV avalia verticalmente em uma única coluna (métrica) nos elementos da dimensão.

```
MAXV(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | Uma métrica que você gostaria de avaliar. |

## Mínimo da coluna {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. MINV avalia verticalmente em uma única coluna (métrica) nos elementos da dimensão.

```
MINV(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | Uma métrica que você gostaria de avaliar. |

## Soma da coluna {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão).

```
SUM(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter o valor total ou soma. |

## Contagem (Tabela) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Retorna o número, ou contagem, de valores diferentes de zero de uma métrica em uma coluna (o número de elementos únicos informados em uma dimensão).

```
COUNT(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica que deseja contar. |

## Expoente (Linha) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Retorna *e* elevado à potência de um número especificado. A constante *e* é igual a 2,71828182845904, a base do logaritmo natural. EXP é o inverso de LN, o logaritmo natural de um número.

```
EXP(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O exponente aplicado à base *e*. |

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
| *metric* | A métrica para a qual você deseja obter a média. |

## Mediana (Tabela) {#concept_183EC31208524EDB8463D986DE2E895F}

Retorna a mediana de uma métrica em uma coluna. A mediana é o número presente no meio de um conjunto de números, ou seja, metade dos números apresentam valores maiores ou iguais à mediana e metade são menores ou iguais à mediana.

```
MEDIAN(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter a mediana. |

## Módulo {#concept_DE0825D7A51643219CB01F59667EA352}

O restante de col1/col2, usado a divisão euclidiana.

Retorna o resto da divisão de x por y.

```
x = floor(x/y) + modulo(x,y)
```

O valor retornado tem o mesmo sinal que a entrada (ou é zero).

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

Retorna o milésimo percentil dos valores de uma métrica. É possível usar esta função para estabelecer um limite de aceitação. Por exemplo, é possível analisar elementos de dimensão com pontuação acima do percentil 90.

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
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> A coluna de métrica que define a posição relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> O valor do percentil no intervalo de 0 a 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartil (Tabela) {#concept_BFD37F0F23A24AD181407142233FA151}

Retorna o quartil de valores de uma métrica. Por exemplo, os quartis podem ser usados para encontrar a porcentagem de 25% dos produtos com maior receita. MINV, MEDIAN, e MAXV retornam o mesmo valor que QUARTIL quando o quartil é igual a 0 (zero), 2 e 4, respectivamente.

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
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> A métrica para a qual você deseja obter o valor do quartil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indica o *valor a retornar. </td> 
  </tr> 
 </tbody> 
</table>

*Se *quart* = 0, QUARTIL retorna o valor mínimo. Se *quart* = 1, QUARTIL retorna o primeiro quartil (percentil 25). Se *quart* = 2, QUARTIL retorna o primeiro quartil (percentil 50). Se *quart* = 3, QUARTIL retorna o primeiro quartil (percentil 75). Se *quart* = 4, QUARTIL retorna o valor máximo.

## Arredondar {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Retorna o número inteiro mais próximo para um determinado valor. Por exemplo, caso você não queira relatar os decimais na receita e um produto apresentar um valor de US$569,34, use a fórmula Arredondar( *Receita*) para arredondar a receita para o número inteiro mais próximo; neste caso, US$569. Um produto de US$569,51 será arredondado para o valor inteiro mais próximo, ou seja, US$570.

```
ROUND(metric)
```

| Argumento | Descrição |
|---|---|
| *number* | A métrica que deseja arredondar. |

Arredondar sem um parâmetro de dígitos é igual a arredondar com um parâmetro de dígitos de 0; ou seja, arredondar para o número inteiro mais próximo. Com um parâmetro de dígitos, ele retorna o mesmo número de dígitos à direita da casa decimal. Se os dígitos forem negativos, retornará zeros à esquerda da casa decimal.

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

Retorna a raiz quadrada positiva de um número. A raiz quadrada de um número é o valor do número elevado à potência de 1/2.

```
SQRT(metric)
```

| Argumento | Descrição |
|---|---|
| *number* | A métrica para a qual você deseja obter a raiz quadrada. |

## Desvio padrão (Tabela) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Retorna o desvio padrão, ou a raiz quadrada da variação, baseada em uma amostra da população de dados.

A equação de STDEV é:

![](assets/std_dev.png)

onde x é a média da amostra (*métrica*), e *n* é o tamanho da amostra.

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
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> A métrica para a qual você deseja obter o desvio padrão. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variação (Tabela) {#concept_269751EDC5A34E689112AE16E04A11B0}

Retorna a variação baseada em uma amostra da população de dados.

A equação de VARIAÇÃO é:

![](assets/variance_eq.png)

onde x é a média da amostra, MÉDIA(*métrica*), e *n* é o tamanho da amostra.

```
VARIANCE(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter a variação. |

Para calcular uma variação, considere uma coluna inteira de números. Nessa lista de números, calcule primeiro a média. Após obter a média, faça o seguinte em cada entrada:

1. Subtraia a média do número.

2. Eleve o resultado ao quadrado.

3. Adicione-o ao total.

Quando você iterar na coluna inteira, terá um total único. Depois, divida o total pelo número de itens na coluna. Esse número é a variação da coluna. É um número único. No entanto, é exibido como uma coluna de números.

Por exemplo, digamos que você tenha uma coluna de três itens:

1

2

3

A média dessa coluna é 2. A variação da coluna será ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. Na Ad Hoc Analysis, isso terá a seguinte aparência:

1 2/3

2 2/3

3 2/3
