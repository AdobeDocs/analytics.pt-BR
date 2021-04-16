---
description: Perguntas frequentes sobre feeds de dados
keywords: Feed de dados, tarefa, coluna anterior, coluna posterior, distinção entre maiúsculas e minúsculas
title: Perguntas frequentes sobre feeds de dados
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 58%

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

Os feeds de dados não incluem bots filtrados pelas [regras de bot do Admin Console](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Por que vejo vários valores `000` na coluna `event_list` ou `post_event_list` do feed de dados?

Alguns editores de planilhas, especialmente o Microsoft Excel, arredondam automaticamente números muito grandes. A coluna `event_list` contém muitos números delimitados por vírgulas, às vezes fazendo com que o Excel a trate como um número grande. Ele arredonda os últimos vários dígitos para `000`.

O Adobe recomenda não abrir automaticamente arquivos `hit_data.tsv` no Microsoft Excel. Em vez disso, use a caixa de diálogo Importar dados do Excel e verifique se todos os campos são tratados como texto.

## Por que não posso extrair arquivos &quot;por hora&quot; de dados que têm mais de 7 dias?

Para dados com mais de 7 dias, os arquivos &quot;Por hora&quot; de um dia são combinados em um único arquivo &quot;Diariamente&quot;.

Exemplo: Um novo Feed de dados é criado em 9 de março de 2021, e os dados de 1º de janeiro de 2021 a 9 de março são entregues como &quot;Por hora&quot;. No entanto, os arquivos &quot;por hora&quot; anteriores a 2 de março de 2021 são combinados em um único arquivo &quot;diário&quot;. Você pode extrair arquivos &quot;por hora&quot; somente de dados com menos de 7 dias a partir da data de criação. Nesse caso, de 2 de março a 9 de março.
