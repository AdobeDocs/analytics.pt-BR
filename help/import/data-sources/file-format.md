---
title: Formato de arquivo da fonte de dados
description: Gerar corretamente um arquivo para uso em fontes de dados.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 7%

---

# Formato de arquivo da fonte de dados

Os arquivos da fonte de dados têm as seguintes propriedades:

* O arquivo está em `.txt` formato.
* As linhas comentadas começam com &#39;`#`&#39;, e são opcionais.
* A primeira linha não comentada contém os cabeçalhos do arquivo.
* O primeiro valor de cada linha é a data, que usa o formato . `MM/DD/YYYY` ou `MM/DD/YYYY/HH/mm/SS`.
* Os valores em cada linha, incluindo cabeçalhos, são delimitados por tabulação.
* Cada linha deve ter pelo menos uma dimensão e uma métrica.

## Comentários

Qualquer linha que comece com &#39;`#`&#39; é um comentário. Ao baixar um arquivo de modelo da fonte de dados, as duas primeiras linhas são comentários.

* O primeiro comentário indica o tipo de modelo que você configurou para a fonte de dados, a ID do usuário de backend que criou a fonte de dados e a ID da fonte de dados.
* O segundo comentário fornece nomes amigáveis para cada um dos cabeçalhos incluídos no arquivo de modelo.

Todas as linhas de comentário são ignoradas pelo Adobe quando o arquivo é processado, de modo que você pode remover os comentários do modelo ou adicionar as suas próprias linhas ao longo do arquivo. Apenas linhas completas podem ser comentadas; não é possível comentar campos individuais ou linhas parciais.

## Cabeçalhos

Ao carregar arquivos de fonte de dados, os cabeçalhos das colunas são necessários. Esses cabeçalhos de coluna não fazem distinção entre maiúsculas e minúsculas, mas os espaços necessários são necessários (Por exemplo, `eVar1` é um cabeçalho inválido, enquanto `EVAR 1` é válido). Os cabeçalhos das colunas se aplicam a todos os conjuntos de relatórios. Use as tabelas a seguir para garantir que cada cabeçalho no arquivo de fonte de dados esteja definido corretamente.

>[!TIP]
>
>É possível criar um arquivo de fontes de dados do zero se você incluir os cabeçalhos corretos no arquivo de fonte de dados. Não há limite para o número de cabeçalhos que podem ser incluídos em um único arquivo; no entanto, cada linha só pode ter um máximo de 4096 bytes.

| Dimensão | Cabeçalho da fonte de dados |
| --- | --- |
| [Categoria](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Canal de marketing](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Detalhes do canal de marketing](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Produto](/help/components/dimensions/product.md) | `Product` |
| [Código de rastreamento](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID da transação](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Código postal](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimension e métricas vão para a mesma linha de cabeçalho.

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

O Adobe não é compatível com fontes de dados de nenhuma outra dimensão ou métrica. Se forem necessárias variáveis além das listadas nas tabelas acima, considere usar a variável [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) em vez disso.

## Data

O primeiro valor em cada linha **must** seja a data. O formato de data deve estar em um dos seguintes formatos:

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

A omissão de horas/minutos/segundos define automaticamente o carimbo de data e hora como 12 PM desse dia.

Um único arquivo de fonte de dados suporta até 90 dias exclusivos. Se quiser incluir mais de 90 dias exclusivos em um upload, divida seus dados em vários arquivos.

## Dimension e dados de métrica

Os valores subsequentes após a data em cada linha contêm os dados que você deseja carregar. Cada linha corresponde ao respectivo carimbo de data e hora. Verifique se o mesmo número de guias existe em cada linha. As colunas podem estar em qualquer ordem; verifique se os dados em cada linha estão alinhados com os cabeçalhos na parte superior. A quantidade máxima de dados que uma única linha pode ter é de 4096 bytes.

Os dados de Dimension não podem conter ponto e vírgula (`;`). As linhas que contêm ponto e vírgula são ignoradas.

## Próximas etapas

[Upload de arquivo](file-upload.md): Saiba mais sobre o processo para carregar um arquivo de fontes de dados para assimilação pelo Adobe.
