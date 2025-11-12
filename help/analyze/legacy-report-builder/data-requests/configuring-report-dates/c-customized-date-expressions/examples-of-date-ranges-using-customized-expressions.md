---
description: Exemplos, observações e notas de sintaxe sobre o uso de intervalos de datas em expressões personalizadas.
title: Exemplos de intervalos de datas usando expressões personalizadas
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: User, Admin
exl-id: d936dd4e-d330-4ed9-a979-3273397d7d92
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 21%

---

# Exemplos de intervalos de datas usando expressões personalizadas

{{legacy-arb}}

Exemplos, observações e notas de sintaxe sobre o uso de intervalos de datas em expressões personalizadas.

A tabela presume que a data de hoje seja segunda-feira, 10 de novembro de 2011, usando o calendário gregoriano.

| Exemplo | Intervalo de datas | Personalizar expressão | Intervalo de datas do relatório |
|---|---|---|---|
|  | | **De** | **Para** |
| 1 | Há duas semanas | `cw-2w  \| cw-1w-1d` | de 26 de outubro a 1 de novembro |
| 2 | Primeiros 3 dias do quinto mês do ano passado | `cy-1y+4m  \| cy-1y+4m+2d` | De 1 de maio a 3 de maio de 2010 |
| 3 | Uma semana inteira, começando há 4 semanas atrás | `cw-4w  \| cw-3w-1d` | de 12 a 18 de outubro |
| 4 | Semana passada do ano anterior | `cw-53w  \| cw-52w-1d` | de novembro a 9 de novembro de 2010 |
| 5 | Um mês começando 2 meses atrás | `cm-2m  \| cm-1m-1d` | De 1 de setembro a 30 de setembro |
| 6 | Há 12 meses no ano anterior | `cm-12m  \| cm-11m-1d` | de 1 de novembro a 30 de novembro de 2010 |

## Observações sobre exemplos {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Exemplo 1**

Se hoje for segunda-feira, 10 de novembro de 2011, use a data atual e subtraia uma semana para obter a última semana completa de outubro.

**Exemplo 2**

Adicione quatro meses ao início do ano (o mês de janeiro) para obter o mês de maio; adicione dois dias ao primeiro dia do mês para obter o terceiro dia do mês.

## Notas de sintaxe {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Expressões personalizadas que abrangem a maioria dos intervalos de datas podem ser criadas vinculando-se dois termos por meio de um operador. Um termo é uma combinação de um multiplicador inteiro e uma abreviação de período. Um exemplo de termo é 18d. Um exemplo de operador é +.

* Não é permitido espaço em branco entre operadores e termos.
* Use apenas estas abreviações: cd cw cm cq cy d w m q y
* A prática recomendada é usar a mesma referência de data na data inicial e na data final: cd, cd ou cw, cw ou cy, cy. A combinação de referências de data pode levar a datas inválidas em determinados momentos do ano.
* Múltiplos válidos das abreviaturas d w m q y são formados por meio de números inteiros ( 1 2 3 ... ) anexados à abreviação, como 53d 3w 5q 9m 2y
* Não são permitidos números não inteiros.
* Não coloque a abreviação apenas com um zero. Por exemplo, 0w não é permitido.
* Os seguintes operadores são usados para concatenar abreviações: + -
* Como os intervalos de datas devem ser calculados em relação ao período atual, o primeiro termo em uma expressão sempre começa com c.
