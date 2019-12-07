---
description: Perguntas frequentes sobre feeds de dados
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Perguntas frequentes sobre feeds de dados
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Perguntas frequentes sobre feeds de dados

Perguntas frequentes sobre feeds de dados.

## Qual é a diferença entre colunas com um `post_` prefixo e colunas sem um `post_` prefixo?

As colunas sem o `post_` prefixo contêm dados exatamente como foram enviados para a coleta de dados. As colunas com um `post_` prefixo contêm o valor após o processamento. Exemplos que podem alterar um valor são persistência de variáveis, regras de processamento, regras VISTA, conversão de moeda ou outra lógica do lado do servidor aplicada pela Adobe. A Adobe recomenda usar a `post_` versão de uma coluna, quando possível.

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## Como os feeds de dados lidam com distinção entre maiúsculas e minúsculas?

No Adobe Analytics, a maioria das variáveis não diferencia maiúsculas de minúsculas para fins de relatório. Por exemplo, 'neve', 'Neve', 'NEVE' e 'sNow' são considerados o mesmo valor. A diferenciação entre maiúsculas e minúsculas é preservada nos feeds de dados.

Se você vir variações de maiúsculas e minúsculas diferentes do mesmo valor entre colunas que não sejam de publicação e posterior (por exemplo, "neve" na coluna anterior e "Neve" na coluna posterior), sua implementação usa valores em maiúsculas e minúsculas no site. A diferenciação entre maiúsculas e minúsculas na coluna posterior foi transmitida e armazenada no cookie virtual ou processada ao mesmo tempo que o conjunto de relatórios.