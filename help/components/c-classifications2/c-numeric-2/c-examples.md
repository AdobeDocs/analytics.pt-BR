---
description: Exemplo para fornecer orientação para a importação de classificações numéricas 2.
seo-description: Exemplo para fornecer orientação para a importação de classificações numéricas 2.
seo-title: Exemplos
solution: Analytics
subtopic: Classificações
title: Exemplos
topic: Ferramentas administrativas
uuid: 0553 d 07 f -87 c 1-4372-90 ce -7118 a 6393 a 01
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Exemplos

Exemplo para fornecer orientação para a importação de classificações numéricas 2.

<!-- 

c_example_1__rate.xml

 -->

Neste caso, você criou a classificação no gerenciador [!UICONTROL Conversão de Classificação] e deseja importar os valores de janeiro:

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | receita | receita |
| 2010/01/01 - 2010/01/31 | receita | receita |

In January, Product1 had a cost of 20% of its revenue (shown in `~MyCost^~value~`) and Product2 had a cost of 30% of its revenue. Because you are importing a new row, `~MyCost^~id~` is blank.

## Resultado {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Um exemplo de saída do relatório é mostrado aqui:

Período: jan 2010

Relatório: produtos

| Produtos | Receita | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | receita | receita |
| 2010/01/01 - 2010/01/31 | receita | receita |
| 2010/02/01 - 2010/02/28 | receita | receita |
| 2010/02/01 - 2010/02/28 | receita | receita |

Em fevereiro, o custo do usuário para o Produto 1 reduziu para 15% da receita, e o Produto 2 reduziu para 25% de sua receita.

## Resultado {#section_23DF5353AC1B478C88647F222703352C}

Um exemplo de saída do relatório é mostrado aqui:

Período: jan 2010

Relatório: produtos

| Produtos | Receita | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

Período: fev 2010

Relatório: produtos

| Produtos | Receita | MyCost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

Período: 1 de jan de 2010 - 28 de fev de 2010

Relatório: produtos

| Produtos | Receita | MyCost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

Você, portanto, importa os seguintes dados:

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixo | nenhum |
| 2010/03/01 - 2010/03/31 | fixo | nenhum |

## Resultado {#section_674B57ADB8284B878F9E670038C31464}

Um exemplo de saída do relatório é mostrado aqui:

Período: mar 2010

Relatório: produtos

| Produtos | Receita | MyCost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

Neste exemplo, é possível adicionar uma cobrança de transporte de $500 para o Produto 1 para janeiro, e de $600 para fevereiro.

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | receita | receita |
| 2010/01/01 - 2010/01/31 | fixo | nenhum |
| 01/02/2010 - 31/01/2010 | receita | receita |
| 01/02/2010 - 31/01/2010 | fixo | nenhum |

As linhas que foram anteriormente importadas têm uma ID que indica que elas não são novos custos.

## Resultado {#section_2096084176614B9AA60F97D5853CB9EA}

Um exemplo de saída do relatório é mostrado aqui:

Período: jan 2010

Relatório: produtos

| Produtos | Receita | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

>[!NOTE]
>
>Esse recurso é para usuários avançados a fim de aproximar valores. As informações resultantes não devem ser tratadas como valores exatos.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

As informações a seguir ilustram este exemplo:

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | pedido | pedido |

## Resultado {#section_39E24ECCC3B34C9AADC25572662750E5}

Um exemplo de saída do relatório é mostrado aqui:

Período: mar 2010

Relatório: produtos por página

| Produtos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| Página inicial | 600 | $600 |
| Carrinho de Compras | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixo | nenhum |
| 2010/03/01 - 2010/03/31 | fixo | nenhum |

## Resultado {#section_7F5F5970077D4E14A5DC91495E23540D}

Um exemplo de saída do relatório é mostrado aqui:

Período: mar 2010

Relatório: produtos por página

| Produtos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Página inicial | 600 | 0 |
| Carrinho de Compras | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

Nesse caso, você importa os seguintes dados:

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixo | receita |
| 2010/03/01 - 2010/03/31 | fixo | receita |

## Resultado {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Um exemplo de saída do relatório é mostrado aqui:

Período: mar 2010

Relatório: produtos por página

| Produtos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Página inicial | 600 | $1800.00 |
| Carrinho de Compras | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

Nesse caso, você importa os seguintes arquivo de dados:

| Chave | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | pedido | receita |

## Resultado {#section_6E2604D9A3B0455585EFF0F80FF54127}

Um exemplo de saída do relatório é mostrado aqui:

Período: mar 2010

Relatório: produtos por página

| Produtos por página | Pedidos | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Página inicial | 600 | $1,000.00 |
| Carrinho de Compras | 400 | $2,000.00 |

