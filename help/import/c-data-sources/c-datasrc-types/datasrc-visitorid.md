---
description: As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).
seo-description: As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).
seo-title: ID de visitante
solution: Analytics
subtopic: Fontes de dados
title: ID de visitante
topic: Desenvolvedor e implementação
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# ID de visitante

As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).

Consulte [Integrar dados](/help/import/c-data-sources/datasrc-integrating-offline-data.md)offline.

<p class="head"> <b>Dimensões da ID do visitante</b> </p>

| Nome da coluna | Descrição |
|--- |--- |
| Visitor ID | (Obrigatório) Valor exclusivo que representa um cliente tanto no sistema online como no offline. |
| Data | Use o seguinte formato de data: MM/DD/AAAA/HH/mm/SS (por exemplo, 07/14/2017/06/00/00) |
| Código de Acompanhamento | Nome do código de acompanhamento. |
| Categoria | Nome da categoria.  Se você especificar uma categoria, você também deve selecionar um produto. |
| Canal | Nome do canal. |
| eVarn | Nome do eVarn. Valores válidos para n são inteiros entre 1 - 75. |
| Produto | Nome do produto. |
| Estado | Nome do estado. |
| Zip | Nome do CEP. |

**Métrica da ID do visitante**

| Nome da coluna | Descrição |
|--- |--- |
| Cliques | Total de visualizações do código de acompanhamento. |
| Adições ao Carrinho | Total de adições ao carrinho. |
| Aberturas do Carrinho | Total de aberturas do carrinho. |
| Remoções do Carrinho | Total de remoções do carrinho. |
| Exibições do carrinho | Total de exibições do carrinho. |
| Finalizações | Total de finalizações. |
| Evento n | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 100.  Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. |
| Exibições do eVarn | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 75. |
| Preço | Preço do produto. |
| Pedidos | Total de pedidos feitos. |
| Exibições do produto | Total de exibições do produto. |
| Quantidade | Total de unidades vendidas. |
