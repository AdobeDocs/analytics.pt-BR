---
description: Informações sobre caracteres especiais usados no feed de dados.
keywords: Feed de dados;tarefa;caracteres especiais;hit_data;variáveis de valores múltiplos;events_list;products_list;mvvars
subtopic: data feeds
title: Caracteres especiais em feeds de dados
feature: Data Feeds
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
source-git-commit: 6e59ee3cb3eb59b025053603cd1357c5a2709d00
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 94%

---

# Caracteres especiais em feeds de dados

A Adobe usa a lógica de escape para garantir que os valores enviados para os servidores de coleta de dados não corrompam ou negam os arquivos de feed de dados. Os seguintes caracteres são reservados pela Adobe para os seguintes fins em `hit_data.tsv`.

## Caracteres especiais em qualquer coluna

| Caractere | Descrição |
|--- |--- |
| `\t` | Representa uma guia. Marca o fim de uma coluna ou campo de dados. |
| `\n` | Representa uma nova linha. Marca o fim de uma linha ou ocorrência. |
| `\` | Barra invertida. Escapa caracteres quando enviados como parte da coleta de dados. |

Quando esses valores reservados são precedidos por uma barra invertida, eles são enviados como parte da coleta de dados.

| Caractere | Descrição |
|--- |--- |
| `\\t` | O valor &#39;`\t`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |
| `\\n` | O valor &#39;`\n`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |
| `\\` | O valor &#39;`\`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |

Por exemplo, um visitante do site usa pesquisa interna e pesquisa por `"search\nstring"`. Você preenche o eVar1 com `"search\nstring"`e envie esse valor para Adobe. A Adobe recebe essa ocorrência e escapa da nova linha incluída na string. O valor real colocado nos dados brutos é `"search\\nstring"`.

## Caracteres especiais em variáveis de vários valores (events_list, products_list, mvvars)

Os caracteres a seguir têm um significado especial em colunas que podem conter vários valores.

| Caractere | Descrição |
|--- |--- |
| `,` | Vírgula. Representa o final de um valor individual. Separa strings de produto, IDs de evento ou outros valores. |
| `;` | Ponto e vírgula. Representa o final de um valor individual em `product_list`. Separa campos em uma única sequência de produtos. |
| `=` | Sinal de igual. Atribui um valor a um evento na `product_list`. |
| `^` | Acento circunflexo. Escapa caracteres quando enviados como parte da coleta de dados. |

Quando esses valores reservados são precedidos por um sinal de interpolação, eles são enviados como parte da coleta de dados.

| Caractere | Descrição |
|--- |--- |
| `^,` | O valor &#39;`,`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |
| `^;` | O valor &#39;`;`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |
| `^=` | O valor &#39;`=`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |
| `^^` | O valor &#39;`^`&#39; foi enviado durante a coleta de dados, escapado pela Adobe. |
