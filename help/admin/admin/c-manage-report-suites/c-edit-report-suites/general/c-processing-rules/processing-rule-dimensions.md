---
description: As dimensões e métricas disponíveis que você pode ler e gravar usando as regras de processamento.
subtopic: Processing rules
title: Dimensões disponíveis para as regras de processamento
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 02fea12d1286fdf2b8cd075c8bcccca0d196cad2
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 13%

---

# Dimension e métricas disponíveis para as regras de processamento

As dimensões e métricas disponíveis que você pode ler e gravar usando as regras de processamento.

## Valores personalizados e dados de contexto

| Valor | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| Valor personalizado | Somente leitura | Texto personalizado ou valores digitados diretamente na ação de uma regra de processamento. |
| Valor concatenado | Somente leitura | Valores que são criados pela combinação de dois valores. Por exemplo, canal e nome de página podem ser combinados para criar uma subcategoria. |

## Atributos de ocorrência

| Atributo | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| URL da página | Leitura + gravação | A dimensão [URL da Página](/help/components/dimensions/page-url.md). As ocorrências de rastreamento de link removem essa dimensão antes de atingir as regras de processamento. Se você inserir novamente um valor de URL de página usando regras de processamento, a ocorrência será considerada uma [Exibição de página](/help/components/metrics/page-views.md), em vez de um [Evento de página](/help/components/metrics/page-events.md). O Adobe recomenda verificar um valor na dimensão da página antes de modificá-la. |
| Nome da página | Leitura + gravação | A dimensão [Página](/help/components/dimensions/page.md). As ocorrências de rastreamento de link removem essa dimensão antes de atingir as regras de processamento. Se você inserir novamente um valor de página usando regras de processamento, a ocorrência será considerada uma [Exibição de página](/help/components/metrics/page-views.md), em vez de um [Evento de página](/help/components/metrics/page-events.md). O Adobe recomenda verificar um valor na dimensão da página antes de modificá-la. |
| ID do conjunto de relatórios | Somente leitura | O conjunto de relatórios no qual a regra de processamento é executada. Esse conjunto de relatórios pode ser diferente do conjunto de relatórios enviado originalmente pelo AppMeasurement, como ao usar as regras VISTA. |
| Versão do código de AppMeasurement | Somente leitura | A versão da biblioteca de AppMeasurements usada para gerar a solicitação de imagem. |
| Endereço IP | Somente leitura | O endereço IP do visitante. |
| Agente do usuário | Somente leitura | O agente do usuário do visitante. |
| Referenciador | Somente leitura | A dimensão [Referenciador](/help/components/dimensions/referrer.md). |
| Query string Parameter | Somente leitura | O valor de um parâmetro da string de consulta especificado no URL atual. |
| Parâmetro da sequência de consulta de referência | Somente leitura | O valor de um parâmetro da string de consulta especificado no URL de referência, ou uma string vazia se não existir nenhuma. |
| Domínio de referência | Somente leitura | O domínio de página do URL de referência, incluindo subdomínios. |
| Domínio raiz de referência | Somente leitura | O domínio de página do URL de referência, excluindo subdomínios. |
| Sequência de consulta da página | Somente leitura | Todos os parâmetros de cadeia de caracteres de consulta e seus valores no URL atual. |
| Sequência de consulta de referência | Somente leitura | Todos os parâmetros da cadeia de caracteres de consulta e seus valores no URL de referência. |
| Caminho da página | Somente leitura | O caminho da página do URL atual. O caminho da página não inclui parâmetros de protocolo, domínio ou sequência de consulta. |
| Domínio da página | Somente leitura | O domínio de página do URL atual, incluindo subdomínios. O domínio da página não inclui o caminho da página ou os parâmetros da sequência de consulta. |
| Domínio raiz da página | Somente leitura | O domínio de página do URL atual, excluindo subdomínios. |
| Perspectiva do cliente | Leitura + gravação | Um sinalizador que determina se a ocorrência é uma ocorrência em segundo plano móvel. |

## Variáveis de conversão

| Variável | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| eVar 1-250 | Leitura + gravação | [eVar](/help/components/dimensions/evar.md) dimensões. |
| Campanha | Leitura + gravação | A dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). |
| ID de compra | Leitura + gravação | A variável de implementação [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| Estado | Leitura + gravação | A variável de implementação [`state`](/help/implement/vars/page-vars/state.md) foi removida. |
| CEP | Leitura + gravação | A dimensão [CEP](/help/components/dimensions/zip-code.md). |
| Código de moeda | Leitura + gravação | A variável de implementação [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). IMPORTANTE: se você definir essa variável com um valor inválido, a ocorrência será descartada. |
| ID da transação | Leitura + gravação | A variável de implementação [`transactionID`](/help/import/data-sources/transactionid.md). |

>[!NOTE]
>O Adobe não oferece suporte à configuração da variável de implementação [`products`](/help/implement/vars/page-vars/products.md) usando regras de processamento.

## Variáveis de tráfego

| Variável | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| Prop 1-75 | Leitura + gravação | [Prop](/help/components/dimensions/prop.md) dimensões. |
| Hierarquia 1-5 | Leitura + gravação | [Hierarquia](/help/components/dimensions/hierarchy.md) dimensões. |
| Servidor | Leitura + gravação | A dimensão [Servidor](/help/components/dimensions/server.md). |
| Canal | Leitura + gravação | A dimensão [Seção do site](/help/components/dimensions/site-section.md). |

## Variáveis de contexto

Todas as [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) que este conjunto de relatórios viu em solicitações de imagem anteriores. Se as regras de processamento não colocarem os dados de contexto em outra variável, esses dados serão perdidos permanentemente. Consulte [Copiar uma variável de dados de contexto para um eVar](processing-rules-examples/processing-rules-copy-context-data.md) e [Definir um evento usando uma variável de dados de contexto](processing-rules-examples/processing-rules-copy-context-data-event.md) para obter exemplos de uso.

## Eventos bem-sucedidos

As regras de processamento podem definir eventos, mas não podem lê-los como condições. Defina a lista suspensa de ações da regra como **[!UICONTROL Definir evento]** para ver as métricas disponíveis para incremento.

| Variável | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| Pedidos | Somente gravação | A métrica [Pedidos](/help/components/metrics/orders.md). |
| Carrinhos | Somente gravação | A métrica [Carrinhos](/help/components/metrics/carts.md). |
| Visualizações do carrinho | Somente gravação | A métrica [Exibições do carrinho](/help/components/metrics/cart-views.md). |
| Check-outs | Somente gravação | A métrica [Check-outs](/help/components/metrics/checkouts.md). |
| Adições ao carrinho | Somente gravação | A métrica [Adições ao carrinho](/help/components/metrics/cart-additions.md). |
| Remoções do carrinho | Somente gravação | A métrica [Remoções do carrinho](/help/components/metrics/cart-removals.md). |
| Evento 1-1000 | Somente gravação | [Eventos personalizados](/help/components/metrics/custom-events.md). |
| Visualizações de produto | Somente gravação | A métrica [Exibições de produto](/help/components/metrics/product-views.md). |

