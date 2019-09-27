---
description: Etapas que você pode adotar como preparação para usar as fontes de dados
seo-description: Etapas que você pode adotar como preparação para usar as fontes de dados
seo-title: Preparação para usar as Fontes de dados
solution: Analytics
subtopic: Data sources
title: Preparação para usar as Fontes de dados
topic: Desenvolvedor e implementação
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Preparar para usar as Fontes de Dados

Etapas que você pode adotar como preparação para usar as fontes de dados

* [Identificar e nomear as métricas](../../import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identificar as dimensões dos dados](../../import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Código de rastreamento de campanha](../../import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID da transação](../../import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identificar um intervalo de datas válido para dados da fonte de dados](../../import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identificar e nomear as métricas  {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

It is important to understand the metrics or measurements that are contained in your data sources, such as *`Off-line Sales Revenue by Product`*, *`Returns by Product`*, or *`Ad Impressions by Campaign`*. Esses são os nomes que você associará às métricas do relatório (events, props e eVars).

Depois de determinar os mapeamentos adequados de métrica para eventos para os dados da Fonte de dados, renomeie os eventos com os nomes descritivos adequados à métrica das Fontes de dados associada.

Consulte [Eventos de sucesso](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html) na Ajuda das Ferramentas administrativas.

>[!NOTE]
>
>Adobe strongly recommends using new, empty events with Data Sources data, but in rare cases it might make sense to use a pre-existing event.

## Identificação das Dimensões de Dados {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identifique e colete os dados (relatórios) que deseja usar para analisar as métricas importadas por meio das Fontes de dados. Esses dados são conhecidos como *`data dimensions`*.

Por exemplo, se uma métrica da Fonte de dados mede impressões de anúncios, a dimensão de dados provavelmente será um código de acompanhamento da campanha. Se você estiver medindo vendas off-line, convém usar o código do produto (ou SKU) como sua dimensão de dados.

É possível definir diversas dimensões de dados para uma métrica, mas cada métrica deve fornecer um valor relevante, ou combinação de valores, para cada dimensão de dados associada. Por exemplo, se você importar uma métrica de Vendas offline e associá-la a dimensões de dados  *`Product`* and *`Partner`* data dimensions, the Off-line Sales metric must be relevant for each combination of product and partner (for example, Total Revenue).

>[!NOTE]
>
>É possível importar métricas totais que não podem ser analisadas por qualquer dimensão de dados.

Após definir as dimensões dos dados para usar com uma fonte de dados, integre os dados de dimensões aos relatórios de marketing por mapeá-los na variável. Use os relatórios padrão (por exemplo, Produto, Código de Acompanhamento, Palavra-chave de Pesquisa) ou as variáveis de Tráfego e Conversão (eVars).

No caso das eVars, é possível usar tanto eVars existentes como novas, como dimensões de dados. Após selecionar uma eVar para receber uma dimensão de dados das Fontes de dados, não deixe de nomeá-la adequadamente.

Consulte [Eventos de sucesso](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html) na Ajuda do Analytics.

## Código de rastreamento de campanha {#section_468222796FF449ABAA90D88EB3264CB1}

Além de importar eventos de sucesso, opcionalmente, é possível optar por importar valores eVar associados. Por exemplo, se acompanha atividades online com um Código de acompanhamento de campanha, e tem códigos de acompanhamento de campanha para as métricas offline, você pode importar as métricas com os códigos de acompanhamento de campanha. Isso permitirá que você veja tanto as métricas online como offline nos relatórios da campanha.

Se você não importar métricas das Fontes de dados com um valor eVar associado, não será possível ver as métricas da Fonte de dados analisadas por eVars. Será possível ver apenas as métricas totais.

## ID da transação {#section_D9513C1204B7496C9B738C5B12CCCFC7}

A ID de transação é utilizada para conectar um evento on-line a um evento off-line.

## Identificação de um Intervalo de Datas Válido para Dados da Fonte de Dados {#section_03AAB1291BDC4403BDC50905A78FDB71}

Depois de definir as métricas das suas Fontes de dados (Eventos personalizados) e dimensões de dados (eVars), reveja o intervalo de datas dos dados da Fonte de dados que deseja importar. Não é possível importar fontes de dados que não estejam no intervalo dos dados existentes no relatório.

Por exemplo, não é possível importar dados da Fonte de dados que tenham data anterior à data de implantação do acompanhamento de dados online. Os dados das Fontes de dados devem ser analisados por dia.
