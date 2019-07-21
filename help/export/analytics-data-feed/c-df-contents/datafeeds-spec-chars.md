---
description: Informações sobre caracteres especiais usados no feed de dados.
keywords: Feed de dados; tarefa; caracteres especiais; hit_ data; variáveis de vários valores; events_ list; products_ list; mvvars
seo-description: Informações sobre caracteres especiais usados no feed de dados.
seo-title: Caracteres especiais
solution: Analytics
subtopic: feed de dados
title: Caracteres especiais
topic: Reports and Analytics
uuid: 5 efe 019 b -39 e 6-4226-a 936-88202 a 02 f 5 e 6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Caracteres especiais

Informações sobre caracteres especiais usados no feed de dados.

* [Caracteres especiais no arquivo hit_data](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [Caracteres especiais nas variáveis com vários valores (events_list, products_list, mvvars)](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [Amostra de fluxo de trabalho](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## Caracteres especiais no arquivo hit_data {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

Os caracteres a seguir têm um significado especial no arquivo hit_data:

| Caractere | Significado | Descrição |
|--- |--- |--- |
| \t (caractere de tabulação) | Fim da coluna | Marca o fim de um campo de dados. |
| \n (caractere de nova linha) | Fim da linha | Marca o fim de uma linha de dados. |
| \  (caractere de barra invertida) | Caractere de escape | Retira tabulação, nova linha e barra invertida quando o caractere for parte do valor enviado durante a coleta de dados. |

Quando um caractere especial for precedido por uma barra invertida, representará um caractere literal.

| Caractere | Significado | Descrição |
|--- |--- |--- |
| \\t | Tabulação | Caractere de tabulação literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |
| \\n | Nova linha | Nova linha literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |
| \\ | Barra invertida | Caractere de barra invertida literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |

## Caracteres especiais em variáveis de vários valores (events_list, products_list, mvvars) {#section_056F8D540FFC4F24A001DC74331C2AAC}

Os caracteres a seguir têm um significado especial em variáveis de vários valores:

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractere </th> 
   <th colname="col02" class="entry"> Significado </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> , </code> (caractere de vírgula) </td> 
   <td colname="col02"> Fim do valor </td> 
   <td colname="col2"> <p>Separa sequências de produto, IDs de evento ou outros valores em variáveis de vários valores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> ; </code> (caractere de ponto e vírgula) </td> 
   <td colname="col02"> Fim de subvalor em um valor de produto individual </td> 
   <td colname="col2"> <p>Separa valores associados a um produto individual na <code>product_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> = </code> (caractere de igual) </td> 
   <td colname="col02"> Atribuição de valor </td> 
   <td colname="col2"> <p>Atribui um valor a um evento na <code>event_list </code>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Quando um caractere especial for precedido por um sinal de interpolação, representará um caractere literal.

| Caractere | Significado | Descrição |
|--- |--- |--- |
| ^, | Vírgula | Caractere de vírgula literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |
| ^; | Ponto e vírgula | Caractere de ponto e vírgula literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |
| ^= | Igual | Caractere de igual literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |
| ^^ | Sinal de interpolação | Caractere de sinal de interpolação literal. Esse caractere era parte de um valor enviado durante a coleta de dados. |

## Amostra do fluxo de trabalho {#section_97F8C2925A35433DA2E7E8BE60037E37}

Se uma coluna no seu feed de dados tiver dados enviados pelo usuário, você deverá verificar se há caracteres especiais antes de separar os dados por coluna ou linha usando `split` ou `readLine`, ou semelhante.

Considere os seguintes dados:

| Largura da janela do navegador | Altura da janela do navegador | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\tstring | en |

Durante a exportação, os caracteres de nova linha e de tabulação nos valores da eVar1 são removidos. O feed de dados para essas linhas aparece da seguinte maneira:

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

Para evitar isso, use uma solução como a que segue:

1. Começando pelo início do arquivo, leia até encontrar um caractere de tabulação, nova linha, barra invertida ou sinal de interpolação.
1. Execute uma ação com base no caractere especial encontrado:

   * Tabulação: insira a sequência até esse ponto em uma célula de armazenamento de dados e prossiga.
   * Nova linha: preencha a linha de armazenamento de dados.
   * Barra invertida: leia o caractere a seguir, insira a sequência adequada literal e prossiga.
   * Sinal de interpolação: leia o caractere a seguir, insira a sequência adequada literal e prossiga.

