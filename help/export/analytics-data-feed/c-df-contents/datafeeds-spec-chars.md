---
description: Informações sobre caracteres especiais usados no feed de dados.
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: Caracteres especiais em feeds de dados
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Caracteres especiais em feeds de dados

A Adobe usa a lógica de escape para garantir que os valores enviados para os servidores de coleta de dados não corrompam ou negam os arquivos de feed de dados. Os seguintes caracteres são reservados pela Adobe para os seguintes fins em `hit_data.tsv`.

## Caracteres especiais em qualquer coluna

| Caractere | Descrição |
|--- |--- |
| `\t` | Representa uma guia. Marca o fim de uma coluna ou de um campo de dados. |
| `\n` | Representa uma nova linha. Marca o fim de uma linha ou ocorrência. |
| `\` | Barra invertida. Escapa caracteres quando enviados como parte da coleta de dados. |

Quando esses valores reservados são precedidos por uma barra invertida, eles são enviados como parte da coleta de dados.

| Caractere | Descrição |
|--- |--- |
| `\\t` | O valor '`\t`' foi enviado durante a coleta de dados, escapado pela Adobe. |
| `\\n` | O valor '`\n`' foi enviado durante a coleta de dados, escapado pela Adobe. |
| `\\` | O valor '`\`' foi enviado durante a coleta de dados, escapado pela Adobe. |

Por exemplo, um visitante do site usa pesquisa interna e pesquisa por "busca\nstring". Preencha a eVar1 com "search\nstring" e envie esse valor para a Adobe. A Adobe recebe essa ocorrência e escapa da nova linha incluída na string. O valor real colocado nos dados brutos é "search\\nstring".

## Caracteres especiais em variáveis de vários valores (events_list, products_list, mvvars)

Os caracteres a seguir têm um significado especial em colunas que podem conter vários valores.

| Caractere | Descrição |
|--- |--- |
| `,` | Vírgula. Representa o final de um valor individual. Separa strings de produto, IDs de evento ou outros valores. |
| `;` | Dois pontos. Representa o final de um valor individual em `product_list`. Separa campos em uma única sequência de produtos. |
| `=` | É igual a sinal. Assigns a value to an event in `product_list`. |
| `^` | Acento circunflexo. Escapa caracteres quando enviados como parte da coleta de dados. |

Quando esses valores reservados são precedidos por um sinal de interpolação, eles são enviados como parte da coleta de dados.

| Caractere | Descrição |
|--- |--- |
| `^,` | O valor '`,`' foi enviado durante a coleta de dados, escapado pela Adobe. |
| `^;` | O valor '`;`' foi enviado durante a coleta de dados, escapado pela Adobe. |
| `^=` | O valor '`=`' foi enviado durante a coleta de dados, escapado pela Adobe. |
| `^^` | O valor '`^`' foi enviado durante a coleta de dados, escapado pela Adobe. |
