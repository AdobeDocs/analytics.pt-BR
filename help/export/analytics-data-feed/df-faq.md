---
description: Perguntas frequentes sobre feeds de dados
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Perguntas frequentes sobre feeds de dados
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 66%

---


# Perguntas frequentes sobre feeds de dados

Perguntas frequentes sobre feeds de dados.

## Qual é a diferença entre colunas com um prefixo `post_` e colunas sem um prefixo `post_`?

As colunas sem o prefixo `post_` contêm dados exatamente como foram enviados para a coleta de dados. As colunas com um prefixo `post_` contêm o valor após o processamento. Exemplos que podem alterar um valor são persistência de variáveis, regras de processamento, regras VISTA, conversão de moeda ou outra lógica do lado do servidor aplicada pela Adobe. A Adobe recomenda usar a versão `post_` de uma coluna, quando possível.

Se uma coluna não tiver uma versão `post_` (por exemplo, `visit_num`), ela pode ser considerada uma coluna posterior.

## Como os feeds de dados lidam com distinção entre maiúsculas e minúsculas?

No Adobe Analytics, a maioria das variáveis não diferencia maiúsculas de minúsculas para fins de relatório. Por exemplo, &#39;neve&#39;, &#39;Neve&#39;, &#39;NEVE&#39; e &#39;nEve&#39; são considerados o mesmo valor. A diferenciação entre maiúsculas e minúsculas é mantida nos feeds de dados.

Se você vir variações de maiúsculas e minúsculas diferentes do mesmo valor entre colunas que sejam ou não de publicação (por exemplo, &quot;neve&quot; na coluna anterior e &quot;Neve&quot; na coluna posterior), sua implementação usa valores em maiúsculas e minúsculas no site. A diferenciação entre maiúsculas e minúsculas na coluna posterior foi transmitida e armazenada no cookie virtual ou processada ao mesmo tempo que o conjunto de relatórios.

## Os bots são filtrados pelas regras de bot do Admin Console nos feeds de dados?

Os feeds de dados não incluem bots filtrados pelas regras [do robô do console](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html)de administração.

## Por que vejo vários `000` valores na coluna do feed de dados `event_list` ou `post_event_list` ?

Alguns editores de planilhas, especialmente o Microsoft Excel, arredondam automaticamente números muito grandes. A `event_list` coluna contém muitos números delimitados por vírgulas, às vezes fazendo com que o Excel a trate como um grande número. Ele arredonda os últimos dígitos para `000`.

O Adobe recomenda não abrir `hit_data.tsv` arquivos automaticamente no Microsoft Excel. Em vez disso, use a caixa de diálogo Importar dados do Excel e verifique se todos os campos são tratados como texto.
