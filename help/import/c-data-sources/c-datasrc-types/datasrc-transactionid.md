---
description: As IDs de transação podem ser integradas selecionando a categoria Genérica (ID de transação).
seo-description: As IDs de transação podem ser integradas selecionando a categoria Genérica (ID de transação).
seo-title: ID da transação
solution: Analytics
subtopic: Fontes de dados
title: ID da transação
topic: Desenvolvedor e implementação
uuid: f 3370 bb 7-3 f 28-460 b-a 20 d-c 9 e 58 d 7301 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID da transação

As IDs de transação podem ser integradas selecionando a categoria Genérica (ID de transação).

See [Integrating Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensões da ID da transação**

| Nome da coluna | Descrição |
|--- |--- |
| ID da transação | (Obrigatório) Valor exclusivo que representa uma transação on-line que resultou em uma atividade off-line. |
| Data | Use o seguinte formato de data: MM/DD/AAAA/HH/mm/SS (por exemplo, 01/01/2015/06/00/00) |
| Código de Acompanhamento | Nome do código de acompanhamento. |
| Categoria | Nome da categoria.  Se você especificar uma categoria, você também deve selecionar um produto. |
| Canal | Nome do canal. |
| Evarn | Nome do evarn. Valores válidos para n são inteiros entre 1 - 250. |
| Produto | Nome do produto. |
| Estado | Nome do estado. |
| CEP | Nome do CEP. |

<p class="head"> <b> Métrica da ID da transação</b> </p>



| Nome da coluna | Descrição |
|--- |--- |
| Cliques | Total de visualizações do código de acompanhamento. |
| Adições ao Carrinho | Total de adições ao carrinho. |
| Aberturas do Carrinho | Total de aberturas do carrinho. |
| Remoções do Carrinho | Total de remoções do carrinho. |
| Exibições do Carrinho | Total de exibições do carrinho. |
| Finalizações | Total de finalizações. |
| Evento n | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 1000.  Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. |
| Exibições do evarn | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 250. |
| Preço | Preço do produto. |
| Ordens | Total de pedidos feitos. |
| Exibições do Produto | Total de exibições do produto. |
| Quantidade | Total de unidades vendidas. |