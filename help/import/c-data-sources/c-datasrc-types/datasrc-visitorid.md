---
description: As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).
seo-description: As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).
seo-title: ID do visitante
solution: Analytics
subtopic: Fontes de dados
title: ID de visitante
topic: Desenvolvedor e implementação
uuid: 4 e 9 ce 675-72 c 2-42 a 4-8 f 2 e -25140 df 19539
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID do visitante

As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).

See [Integrate Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

<p class="head"> <b>Dimensões da ID do visitante</b> </p>

| Nome da coluna | Descrição |
|--- |--- |
| ID do visitante | (Obrigatório) Valor exclusivo que representa um cliente tanto no sistema online como no offline. |
| Data | Use o seguinte formato de data: MM/DD/AAAA/HH/mm/SS (por exemplo, 07/14/2017/06/00/00) |
| Código de Acompanhamento | Nome do código de acompanhamento. |
| Categoria | Nome da categoria.  Se você especificar uma categoria, você também deve selecionar um produto. |
| Canal | Nome do canal. |
| Evarn | Nome do evarn. Valores válidos para n são inteiros entre 1 - 75. |
| Produto | Nome do produto. |
| Estado | Nome do estado. |
| CEP | Nome do CEP. |

**Métrica da ID do visitante**

| Nome da coluna | Descrição |
|--- |--- |
| Cliques | Total de visualizações do código de acompanhamento. |
| Adições ao Carrinho | Total de adições ao carrinho. |
| Aberturas do Carrinho | Total de aberturas do carrinho. |
| Remoções do Carrinho | Total de remoções do carrinho. |
| Exibições do Carrinho | Total de exibições do carrinho. |
| Finalizações | Total de finalizações. |
| Evento n | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 100.  Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. |
| Exibições do evarn | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 75. |
| Preço | Preço do produto. |
| Ordens | Total de pedidos feitos. |
| Exibições do Produto | Total de exibições do produto. |
| Quantidade | Total de unidades vendidas. |