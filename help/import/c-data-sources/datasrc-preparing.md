---
description: Etapas que você pode adotar como preparação para usar as fontes de dados
subtopic: Data sources
title: Preparação para usar as Fontes de dados
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Preparação para usar as Fontes de dados

Etapas que você pode adotar como preparação para usar as fontes de dados

* [Identificar e nomear as métricas](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [Identificação das Dimensões de Dados](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [Código de rastreamento de campanha](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [ID da transação](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [Identificação de um Intervalo de Datas Válido para Dados da Fonte de Dados](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## Identificar e nomear as métricas {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

É importante conhecer as métricas ou medidas contidas nas fontes de dados, como *`Off-line Sales Revenue by Product`*, *`Returns by Product`* ou *`Ad Impressions by Campaign`*. Esses são os nomes que você pode associar às métricas do relatório (eventos, props e eVars).

Depois de determinar os mapeamentos adequados de métrica para evento para os dados das Fontes de dados, renomeie os eventos com os nomes descritivos apropriados para a métrica das Fontes de dados associada.

Consulte Eventos [de](https://marketing.adobe.com/resources/help/pt_BR/reference/success_event.html) sucesso na Ajuda das Ferramentas administrativas.

>[!NOTE] A Adobe recomenda utilizar eventos novos e vazios com os dados de Fontes de dados, mas, em raros casos, pode fazer sentido usar um evento preexistente.

## Identificação das Dimensões de Dados {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

Identifique e colete os dados (relatórios) que deseja usar para detalhar as métricas importadas por meio das Fontes de Dados. Esses dados são conhecidos como *`data dimensions`*.

Por exemplo, se uma métrica da Fonte de dados mede impressões de anúncios, a dimensão de dados provavelmente será um Código de rastreamento da campanha. Se você estiver medindo vendas off-line, talvez queira usar o código do produto (ou SKU) como sua dimensão de dados.

É possível definir diversas dimensões de dados para uma métrica, mas cada métrica deve fornecer um valor relevante, ou combinação de valores, para cada dimensão de dados associada. Por exemplo, se você importar uma métrica de Vendas offline e associá-la a dimensões de dados *`Product`* e *`Partner`*, a métrica de vendas offline deverá ser relevante para cada combinação de produto e parceiro (por exemplo, Receita total).

>[!NOTE] É possível importar Métricas totais que não podem ser analisadas por qualquer dimensão de dados.

Depois de definir as dimensões de dados a serem usadas com uma fonte de dados, integre os dados de dimensões nos relatórios de marketing mapeando-os para uma variável. Use os relatórios padrão (por exemplo, Produto, Código de rastreamento, Palavra-chave de Pesquisa) ou as variáveis de Tráfego e Conversão (eVars).

Ao usar eVars, você pode usar eVars existentes ou novas eVars como dimensões de dados. Depois de selecionar uma eVar para receber uma dimensão de dados das Fontes de Dados, certifique-se de nomeá-las apropriadamente.

Consulte Eventos [de](https://marketing.adobe.com/resources/help/pt_BR/reference/success_event.html) sucesso na Ajuda do Analytics.

## Código de rastreamento de campanha {#section_468222796FF449ABAA90D88EB3264CB1}

Além de importar eventos bem-sucedidos, é possível, opcionalmente, importar valores eVar associados. Por exemplo, se acompanha atividades online com um Código de rastreamento de campanha, e tem códigos de acompanhamento de campanha para as métricas offline, você pode importar as métricas com os códigos de acompanhamento de campanha. Essa abordagem permite que você visualização métricas online e offline em relatórios de Campanha.

Se você não importar métricas de Fontes de Dados com um valor eVar associado, não será possível visualização métricas de Fonte de Dados detalhadas por eVars. Em vez disso, você só pode ver as métricas totais.

## ID da transação {#section_D9513C1204B7496C9B738C5B12CCCFC7}

A ID de transação é usada para conectar um evento on-line a um evento off-line.

## Identificação de um Intervalo de Datas Válido para Dados da Fonte de Dados {#section_03AAB1291BDC4403BDC50905A78FDB71}

Depois de definir as métricas das Fontes de Dados (Eventos Personalizados) e as dimensões de dados (eVars), reveja o intervalo de datas dos dados da Fonte de Dados que deseja importar. Não é possível importar Fontes de Dados que estejam fora do intervalo de seus dados de relatórios existentes.

Por exemplo, não é possível importar dados da Fonte de Dados antes de implementar o rastreamento de dados on-line. Os dados das Fontes de Dados devem ser analisados por dia.
