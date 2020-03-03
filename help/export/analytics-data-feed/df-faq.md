---
description: Perguntas frequentes sobre feeds de dados
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Perguntas frequentes sobre feeds de dados
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Perguntas frequentes sobre feeds de dados

Perguntas frequentes sobre feeds de dados.

## Qual é a diferença entre colunas com um prefixo `post_` e colunas sem um prefixo `post_`?

As colunas sem o prefixo `post_` contêm dados exatamente como foram enviados para a coleta de dados. As colunas com um prefixo `post_` contêm o valor após o processamento. Exemplos que podem alterar um valor são persistência de variáveis, regras de processamento, regras VISTA, conversão de moeda ou outra lógica do lado do servidor aplicada pela Adobe. A Adobe recomenda usar a versão `post_` de uma coluna, quando possível.

Se uma coluna não tiver uma versão `post_` (por exemplo, `visit_num`), ela pode ser considerada uma coluna posterior.

## Como os feeds de dados lidam com distinção entre maiúsculas e minúsculas?

No Adobe Analytics, a maioria das variáveis não diferencia maiúsculas de minúsculas para fins de relatório. Por exemplo, &#39;neve&#39;, &#39;Neve&#39;, &#39;NEVE&#39; e &#39;nEve&#39; são considerados o mesmo valor. A diferenciação entre maiúsculas e minúsculas é mantida nos feeds de dados.

Se você vir variações de maiúsculas e minúsculas diferentes do mesmo valor entre colunas que sejam ou não de publicação (por exemplo, &quot;neve&quot; na coluna anterior e &quot;Neve&quot; na coluna posterior), sua implementação usa valores em maiúsculas e minúsculas no site. A diferenciação entre maiúsculas e minúsculas na coluna posterior foi transmitida e armazenada no cookie virtual ou processada ao mesmo tempo que o conjunto de relatórios.