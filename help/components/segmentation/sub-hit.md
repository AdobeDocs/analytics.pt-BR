---
title: Análise de sub-ocorrências
description: Saiba como a análise de sub-ocorrência permite filtrar produtos individuais em uma ocorrência no Adobe Analytics, eliminando a sangria de atribuição nos relatórios de produtos.
feature: Segmentation
hide: true
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 68469e0359deed0d642b1d00d55259c33c410fd4
workflow-type: tm+mt
source-wordcount: 808
ht-degree: 0%

---


# Análise de sub-ocorrência

A análise de sub-ocorrência permite analisar dados do produto em um nível mais granular do que o nível de ocorrência. Em vez de filtrar em ocorrências inteiras, você pode segmentar em produtos individuais nas ocorrências. Por exemplo, segmentar em uma categoria de produto específica sem incluir todos os outros produtos comprados na mesma ordem.


No Adobe Analytics, a [variável Produtos](/help/components/dimensions/product.md) pode capturar vários produtos em uma única ocorrência. Sem a análise de subocorrência, a segmentação em um atributo de produto retorna todas as ocorrências em que qualquer produto em uma ocorrência corresponde ao atributo de produto. O resultado é atribuição incorreta e métricas de receita infladas. A análise de sub-ocorrência atribui o escopo do filtro a linhas de produtos individuais em uma ocorrência e resolve esses problemas.

Na análise de sub-ocorrência, a lógica de exclusão se comporta de forma diferente da exclusão no nível de ocorrência padrão em relação à variável Products. Quando você exclui atributos de produto no contêiner [!UICONTROL Produto], o segmento retorna ocorrências que **têm produtos**, mas não correspondem aos seus critérios de exclusão. O segmento não retorna ocorrências sem produtos.

## Exemplo

Você deseja medir a receita online somente da categoria Homens. Sem a análise de sub-ocorrência, a aplicação de um segmento para Homens inclui a receita de cada produto em qualquer pedido (ocorrência) que contenha pelo menos um produto com a categoria Homens. Com a análise de subocorrência, você define o escopo do filtro para o nível do produto e retorna somente a receita para produtos da categoria Homens.

Também é possível medir a receita online de todas as outras categorias, exceto a categoria Homens.

>[!BEGINTABS]

>[!TAB Análise de ocorrência]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Incluir]** o **[!UICONTROL Dimension]** **[!UICONTROL Varejo: categoria de produto de moda]** **[!UICONTROL igual a]** **[!UICONTROL Homens]** no contêiner **[!UICONTROL Ocorrências]**.

![Painel que mostra a segmentação no nível de ocorrência para homens da categoria de produto](./assets/product-category-segmentation-hits.png)

Como resultado, todos os pedidos contendo pelo menos um **[!UICONTROL Homens]** **[!UICONTROL Varejo: categoria de produto de moda]** são considerados, e a receita de outros produtos nesses pedidos é incluída na métrica **[!UICONTROL Receita online]**.
Quando você relata as categorias, todos os outros valores para **[!UICONTROL Varejo: categoria de produto de moda]** são relatados como parte de um pedido que incluía um produto com a **[!UICONTROL Varejo]** **[!UICONTROL Categoria de produto de moda]**.

>[!TAB Análise de sub-ocorrência]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Incluir]** o **[!UICONTROL Dimension]** **[!UICONTROL Varejo: categoria de produto de moda]** **[!UICONTROL igual a]** **[!UICONTROL Homens]** no contêiner **[!UICONTROL Produtos]**.

![Painel que mostra a segmentação no nível de sub-ocorrência para homens da categoria de produto](./assets/product-category-segmentation-sub-hits.png)

Como resultado, todos os pedidos contendo pelo menos **[!UICONTROL Homens]** **[!UICONTROL Varejo: Categoria de Produto de Moda]** são considerados, e somente a receita de produtos pertencentes à **[!UICONTROL Homens]** **[!UICONTROL Varejo: Categoria de Produto de Moda]** são incluídos na métrica **[!UICONTROL Receita Online]**.
Quando você cria relatórios sobre categorias, somente os **[!UICONTROL Homens]** **[!UICONTROL Varejo: Categoria de Produto de Moda]** são relatados.

>[!TAB Análise de sub-ocorrência (excluir)]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Excluir]** o **[!UICONTROL Dimension]** **[!UICONTROL Varejo: categoria de produto de moda]** **[!UICONTROL igual a]** **[!UICONTROL Homens]** no contêiner **[!UICONTROL Produtos]**.

![Painel que mostra a segmentação no nível de sub-ocorrência para excluir homens da categoria de produto](./assets/product-category-segmentation-sub-hits-exclude.png)

Para excluir no nível do produto, as ocorrências que contêm pelo menos um produto são incluídas, então a exclusão no nível de subocorrência é aplicada dentro desse escopo. Essa exclusão é diferente da exclusão no nível da ocorrência, o que exclui toda a ocorrência.

>[!ENDTABS]

Na análise de sub-ocorrência do Adobe Analytics, aplica-se especificamente à variável **[!UICONTROL Products]**. A variável **[!UICONTROL Products]** é o único objeto de vários valores no Adobe Analytics que oferece suporte à análise de sub-ocorrências.


>[!WARNING]
>
>As seções a seguir serão movidas para os artigos relevantes (sobre o Construtor de segmentos, Segmento rápido, Histograma e muito mais) quando esse recurso for lançado. E esses artigos farão referência a este artigo para saber o que é a análise de sub-ocorrência. No momento, essa ação não é feita para não confundir os clientes enquanto o recurso não estiver disponível.

## Dedução automática do contêiner

Ao arrastar uma dimensão ou métrica de produto para o painel Construtor de segmentos ou Segmento rápido, o sistema seleciona automaticamente o contêiner **[!UICONTROL Produto]** e não usa o contêiner padrão **[!UICONTROL Ocorrência]**. Esse comportamento mantém o escopo do segmento para produtos individuais em vez da ocorrência inteira.

## Comportamento misto do contêiner

Se você arrastar os componentes de nível de produto e de nível de ocorrência para uma única regra de segmento, o sistema usará o contêiner de **[!UICONTROL Ocorrência]**, que é o contêiner compartilhado mais alto (menos granular). Se todos os componentes que fazem parte de uma regra de segmento forem de nível de produto, o contêiner **[!UICONTROL Produto]** será usado.

## Filtros de produto no painel esquerdo

O Construtor de segmentos inclui uma nova opção de filtro no painel esquerdo para exibir somente dimensões e métricas do produto. Isso facilita encontrar componentes no nível do produto ao criar segmentos de sub-ocorrência.

>[!NOTE]
>
>Essa opção de filtro está disponível somente no Construtor de segmentos. Não está disponível em outros painéis à esquerda, como painéis ou visualizações do Analysis Workspace.

## Visualização de histograma

A visualização do Histograma inclui um novo menu suspenso contêiner de subocorrência. Isso permite agrupar valores de métrica no nível do produto. Por exemplo, contar ocorrências de produto por pedido em vez de por ocorrência.

O Histograma é a única visualização que requer uma seleção de contêiner de sub-ocorrência. Todos os outros painéis e visualizações funcionam com dados de análise de sub-ocorrência sem configuração adicional.
