---
description: Exemplos, observações e notas de sintaxe sobre o uso de intervalos de datas em expressões personalizadas.
seo-description: Exemplos, observações e notas de sintaxe sobre o uso de intervalos de datas em expressões personalizadas.
seo-title: Exemplos de intervalos de datas usando expressões personalizadas
solution: Analytics
title: Exemplos de intervalos de datas usando expressões personalizadas
topic: Construtor de relatórios
uuid: 3 f 46816 d -9 eee -4 b 2 d -83 be-bf 1 c 9 fb 97 fcf
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Exemplos de intervalos de datas usando expressões personalizadas

Exemplos, observações e notas de sintaxe sobre o uso de intervalos de datas em expressões personalizadas.

A tabela parte do princípio de que a data de hoje é segunda-feira, 10 de novembro de 2011, usando o calendário gregoriano.

| Exemplo | Intervalo de data | Expressão personalizada | Intervalo de datas do relatório |
|---|---|---|---|
|  |  | **De** | **Para** |  |
| 1 | Duas semanas atrás | cw-2w | cw-1w-1d | 26 de out. a 1º de nov. |
| 2 | Primeiros três dias do quinto mês do ano passado | cy-1y+4m | cy-1y+4m+2d | 1º de maio 3 de maio de 2010 |
| 3 | Uma semana inteira, começando quatro semanas atrás | cw-4w | cw-3w-1d | 12 de out. a 18 de out. |
| 4 | A semana passada no ano anterior | cw-53w | cw-52w-1d | de nov. a 9 de nov. 2010 |
| 5 | Um mês, começando dois meses atrás | cm-2m | cm-1m-1d | 1º de set. a 30 de set. |
| 6 | 12 meses atrás no ano passado | cm-12m | cm-11m-1d | 1º de nov. a 30 de nov. 2010 |

## Notes on examples {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Exemplo 1**

Se hoje for segunda-feira, 10 de novembro de 2011, tome a data atual e subtraia uma semana para obter a última semana completa de outubro.

**Exemplo 2**

Adicione quatro meses ao começo do ano (o mês de janeiro) para obter o mês de maio; adicione dois dias ao primeiro dia do mês para obter o terceiro dia do mês.

## Syntax notes {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Expressões personalizadas que abrangem a maioria dos intervalos de datas podem ser criadas vinculando-se dois termos por meio de um operador. Um termo é uma combinação de um multiplicador inteiro e uma abreviação de período. Um exemplo de termo é 18d; um exemplo de operador é +.

* Não é permitido que haja espaço em branco entre operadores e termos.
* Use somente estas abreviações: cd cw cm cq cy d w m q y
* A prática recomendada é usar a mesma referência de data nas datas de início e de fim: cd, cd, ou cw, cw, ou cy, cy. Misturar referências de datas pode levar a datas inválidas em determinadas épocas do ano.
* Múltiplos válidos das abreviações d w m q y são formados por meio de números inteiros (1 2 3 ...) prefixados à abreviação, como 53d 3w 5q 9m 2y

   * Números que não sejam inteiros não são permitidos.
   * Não anexe apenas um zero como prefixo da abreviação. Por exemplo, 0w não é permitido.

* Os operadores a seguir são usados para concatenar abreviações: + -
* Visto que os intervalos de datas precisam ser calculados em relação ao período atual, o primeiro termo em uma expressão sempre começa com c.

