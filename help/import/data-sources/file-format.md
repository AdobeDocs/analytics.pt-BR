---
title: Formato de arquivo da fonte de dados
description: Gerar corretamente um arquivo para uso em fontes de dados.
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 5%

---

# Formato de arquivo da fonte de dados

Os arquivos de origem de dados têm as seguintes propriedades:

* O arquivo está em `.txt` formato.
* As linhas comentadas começam com &quot;`#`&#39; e são opcionais.
* A primeira linha não comentada contém os cabeçalhos do arquivo.
* O primeiro valor de cada linha é a data, que usa o formato `MM/DD/YYYY` ou `MM/DD/YYYY/HH/mm/SS`.
* Os valores em cada linha, incluindo cabeçalhos, são delimitados por tabulação.
* Cada linha deve ter pelo menos uma dimensão e uma métrica.

## Comentários

Qualquer linha que comece com &#39;`#`&#39; é um comentário. Ao baixar um arquivo de modelo de fonte de dados, as duas primeiras linhas são comentários.

* O primeiro comentário indica o tipo de modelo configurado para a fonte de dados, o ID de usuário de back-end que criou a fonte de dados e o ID da fonte de dados.
* O segundo comentário fornece nomes amigáveis para cada um dos cabeçalhos incluídos no arquivo de modelo.

Todas as linhas de comentário são ignoradas pelo Adobe quando o arquivo é processado, para que você possa remover os comentários do modelo ou adicionar os seus próprios comentários em todo o arquivo. Somente linhas completas podem ser comentadas; não é possível comentar campos individuais ou linhas parciais.

## Cabeçalhos

Ao fazer upload de arquivos de origem de dados, os cabeçalhos de coluna são obrigatórios. Esses cabeçalhos de coluna não diferenciam maiúsculas de minúsculas, mas os espaços necessários são necessários (Por exemplo, `eVar1` é um cabeçalho inválido, enquanto `EVAR 1` é válido). Os cabeçalhos de coluna se aplicam a todos os conjuntos de relatórios. Use as tabelas a seguir para verificar se cada cabeçalho no arquivo de origem de dados está definido corretamente.

>[!TIP]
>
>Você pode criar um arquivo de fontes de dados do zero se incluir os cabeçalhos corretos no arquivo de fonte de dados. Não há limite para o número de cabeçalhos que podem ser incluídos em um único arquivo; no entanto, cada linha pode ter no máximo 4096 bytes.

| Dimensão | Cabeçalho da fonte de dados |
| --- | --- |
| [Categoria](/help/components/dimensions/category.md) | `Category` |
| [eVar 1 - eVar 250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Canal de marketing](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Detalhes do canal de marketing](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Produto](/help/components/dimensions/product.md) | `Product` |
| [Código de rastreamento](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID da transação](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Código postal](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimension e métricas entram na mesma linha de cabeçalho.

| Métrica | Cabeçalho da fonte de dados |
| --- | --- |
| [Adições ao carrinho](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [Remoções do carrinho](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [Exibições do carrinho](/help/components/metrics/cart-views.md) | `Cart Views` |
| [Carrinhos](/help/components/metrics/carts.md) | `Cart Opens` |
| [Check-outs](/help/components/metrics/checkouts.md) | `Checkouts` |
| [Eventos Personalizados](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [Pedidos](/help/components/metrics/orders.md) | `Orders` |
| [Receita](/help/components/metrics/revenue.md) | `Price` |
| [Unidades](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

O Adobe não oferece suporte a fontes de dados para outras dimensões ou métricas. Se forem necessárias variáveis além das listadas nas tabelas acima, considere o uso de [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) em vez disso.

## Data

O primeiro valor em cada linha **deve** ser a data. O formato de data deve estar em um dos seguintes formatos:

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

A omissão de horas/minutos/segundos define automaticamente o carimbo de data e hora para as 12 PM desse dia.

Um único arquivo de fonte de dados suporta até 90 dias únicos. Se quiser incluir mais de 90 dias únicos em um upload, divida seus dados em vários arquivos.

## dados de Dimension e métrica

Valores subsequentes à data em cada linha contêm os dados que você deseja fazer upload. Cada linha corresponde a esse respectivo carimbo de data e hora. Verifique se existe o mesmo número de guias em cada linha. As colunas podem estar em qualquer ordem; verifique se os dados em cada linha estão alinhados aos cabeçalhos na parte superior. A quantidade máxima de dados que uma única linha pode ter é de 4096 bytes.

Os dados de Dimension não podem conter ponto e vírgula (`;`). As linhas que contêm ponto e vírgula são ignoradas.

## Próximas etapas

[Upload de arquivo](file-upload.md): saiba mais sobre o processo para carregar um arquivo de fontes de dados para assimilação por Adobe.
