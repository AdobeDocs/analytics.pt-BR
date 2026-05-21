---
description: As dimensões e métricas disponíveis que você pode ler e gravar usando as regras de processamento.
subtopic: Processing rules
title: Dimensões e métricas disponíveis para as regras de processamento
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
TQID: https://experienceleague.adobe.com/FFwTZQBj3LWLQdASF91ZwMis12EuOP5a1VhHyxUqXm0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 721
ht-degree: 15%

---

# Dimensões e métricas disponíveis para as regras de processamento

As dimensões e métricas disponíveis que você pode ler e gravar usando as regras de processamento.

## Valores personalizados e dados de contexto

| Valor | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| **Valor personalizado** | Somente leitura | Texto personalizado ou valores digitados diretamente na ação de uma regra de processamento. |
| **Valor concatenado** | Somente leitura | Valores que são criados pela combinação de dois valores. Por exemplo, canal e nome de página podem ser combinados para criar uma subcategoria. |

## Atributos de ocorrência

| Atributo | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| **URL da página** | Leitura + gravação | A dimensão [URL da página](/help/components/dimensions/page-url.md). As ocorrências de rastreamento de link removem essa dimensão antes de atingir as regras de processamento. Se você inserir novamente um valor de URL de página usando regras de processamento, a ocorrência será considerada uma [Exibição de página](/help/components/metrics/page-views.md), em vez de um [Evento de página](/help/components/metrics/page-events.md). A Adobe recomenda verificar se há um valor na dimensão da página antes de modificá-la. |
| **Nome da página** | Leitura + gravação | A dimensão [Página](/help/components/dimensions/page.md). As ocorrências de rastreamento de link removem essa dimensão antes de atingir as regras de processamento. Se você inserir novamente um valor de página usando regras de processamento, a ocorrência será considerada uma [Exibição de página](/help/components/metrics/page-views.md), em vez de um [Evento de página](/help/components/metrics/page-events.md). A Adobe recomenda verificar se há um valor na dimensão da página antes de modificá-la. |
| **ID do conjunto de relatórios** | Somente leitura | O conjunto de relatórios no qual a regra de processamento é executada. Esse conjunto de relatórios pode ser diferente do conjunto de relatórios enviado originalmente pelo AppMeasurement, como ao usar as regras VISTA. |
| **Versão do código AppMeasurement** | Somente leitura | A versão da biblioteca de AppMeasurement usada para gerar a solicitação de imagem. |
| **Endereço IP** | Somente leitura | O endereço IP do visitante. |
| **Agente do usuário** | Somente leitura | O agente do usuário do visitante. |
| **Referenciador** | Somente leitura | A dimensão [Referenciador](/help/components/dimensions/referrer.md). |
| **Parâmetro da cadeia de consulta** | Somente leitura | O valor de um parâmetro da string de consulta especificado no URL atual. |
| **Parâmetro da cadeia de caracteres de consulta de referência** | Somente leitura | O valor de um parâmetro da string de consulta especificado no URL de referência, ou uma string vazia se não existir nenhuma. |
| **Domínio de referência** | Somente leitura | O domínio de página do URL de referência, incluindo subdomínios. |
| **Domínio raiz de referência** | Somente leitura | O domínio de página do URL de referência, excluindo subdomínios. |
| **Sequência de consulta da página** | Somente leitura | Todos os parâmetros de cadeia de caracteres de consulta e seus valores no URL atual. |
| **Cadeia de consulta de referência** | Somente leitura | Todos os parâmetros da cadeia de caracteres de consulta e seus valores no URL de referência. |
| **Caminho da página** | Somente leitura | O caminho da página do URL atual. O caminho da página não inclui parâmetros de protocolo, domínio ou sequência de consulta. |
| **Domínio da página** | Somente leitura | O domínio de página do URL atual, incluindo subdomínios. O domínio da página não inclui o caminho da página ou os parâmetros da sequência de consulta. |
| **Domínio raiz da página** | Somente leitura | O domínio de página do URL atual, excluindo subdomínios. |
| **Perspectiva do cliente** | Leitura + gravação | Um sinalizador que determina se a ocorrência é uma ocorrência em segundo plano móvel. |

## Variáveis de conversão

| Variável | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| **eVar 1-250** | Leitura + gravação | Dimensões de [eVar](/help/components/dimensions/evar.md). |
| **Campaign** | Leitura + gravação | A dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). |
| **ID de compra** | Leitura + gravação | A variável de implementação [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| **Estado** | Leitura + gravação | (Descontinuado) A variável de implementação [`state`](/help/implement/vars/page-vars/state.md). |
| **CEP** | Leitura + gravação | A dimensão [Código postal](/help/components/dimensions/zip-code.md). |
| **Código de moeda** | Leitura + gravação | A variável de implementação [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). IMPORTANTE: se você definir essa variável com um valor inválido, a ocorrência será descartada. |
| **ID da transação** | Leitura + gravação | A variável de implementação [`transactionID`](/help/import/data-sources/transactionid.md). |

>[!NOTE]
>O Adobe não oferece suporte à configuração da variável de implementação [`products`](/help/implement/vars/page-vars/products.md) usando regras de processamento.

## Variáveis de tráfego

| Variável | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| **Prop 1-75** | Leitura + gravação | Dimensões [prop](/help/components/dimensions/prop.md). |
| **Hierarquia 1-5** | Leitura + gravação | (Desativado) [Hierarquia](/help/components/dimensions/hierarchy.md) dimensões. |
| **Servidor** | Leitura + gravação | A dimensão [Servidor](/help/components/dimensions/server.md). |
| **Canal** | Leitura + gravação | A dimensão [Seção do site](/help/components/dimensions/site-section.md). |

## Variáveis de contexto

Todas as [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) que este conjunto de relatórios viu nos últimos 30 dias. Consulte [Casos de uso de regras de processamento](pr-use-cases.md) para ver exemplos de uso.

>[!IMPORTANT]
>
>Se as regras de processamento não mapearem uma determinada variável de dados de contexto para outra variável (como uma prop ou eVar), o valor na variável de dados de contexto será perdido permanentemente.

## Eventos bem-sucedidos

As regras de processamento podem definir eventos, mas não podem lê-los como condições. Defina o menu suspenso de ações da regra como **[!UICONTROL Definir evento]** para ver as métricas disponíveis para incremento.

| Variável | Status de leitura/gravação | Descrição |
| --- | --- | --- |
| **Pedidos** | Somente gravação | A métrica [Pedidos](/help/components/metrics/orders.md). |
| **Carrinhos** | Somente gravação | A métrica [Carrinhos](/help/components/metrics/carts.md). |
| **Visualizações do carrinho** | Somente gravação | A métrica [Exibições do carrinho](/help/components/metrics/cart-views.md). |
| **Check-outs** | Somente gravação | A métrica [Check-outs](/help/components/metrics/checkouts.md). |
| **Adições ao carrinho** | Somente gravação | A métrica [Adições ao carrinho](/help/components/metrics/cart-additions.md). |
| **Remoções do carrinho** | Somente gravação | A métrica [Remoções do carrinho](/help/components/metrics/cart-removals.md). |
| **Evento 1-1000** | Somente gravação | [Eventos personalizados](/help/components/metrics/custom-events.md). |
| **Visualizações de produto** | Somente gravação | A métrica [Exibições de produto](/help/components/metrics/product-views.md). |
