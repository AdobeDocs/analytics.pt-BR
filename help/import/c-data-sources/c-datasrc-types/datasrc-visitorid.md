---
description: As IDs de visitante podem ser integradas selecionando a categoria Genérica (ID de transação).
subtopic: Data sources
title: ID de visitante
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: a7a116ddc9eddc500a52111e9c002bdbee3e4a56
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 81%

---

# VisitorID

As IDs de visitante podem ser integradas selecionando o [!UICONTROL Dados da central de atendimento] categoria .

Consulte [Integrar dados offline](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## Dimension VisitorID

| Nome da coluna | Descrição |
|--- |--- |
| [!UICONTROL VisitorID] | (Obrigatório) Valor único que representa um cliente tanto no sistema online como no offline. |
| [!UICONTROL Data] | Use o seguinte formato de data: `MM/DD/YYYY/hh/mm/ss` (por exemplo, 14/07/2017/06/00/00) |
| [!UICONTROL Código de rastreamento] | Nome do Código de rastreamento. |
| [!UICONTROL Categoria] | Nome da categoria. Se você especificar uma categoria, você também deve selecionar um produto. |
| [!UICONTROL Canal] | Nome do canal. |
| [!UICONTROL eVar ]*n* | Nome do eVar *n*. Valores válidos para *n* são inteiros entre 1 - 75. |
| [!UICONTROL Produto] | Nome do produto. |
| [!UICONTROL Estado] | Nome do estado. |
| [!UICONTROL Zip] | Nome do CEP. |

## Métrica da ID do visitante

| Nome da coluna | Descrição |
| --- | --- |
| [!UICONTROL Click-throughs] | Total de visualizações do Código de rastreamento. |
| [!UICONTROL Adições ao carrinho] | Total de adições ao carrinho. |
| [!UICONTROL Aberturas do carrinho] | Total de aberturas do carrinho. |
| [!UICONTROL Remoções do carrinho] | Total de remoções do carrinho. |
| [!UICONTROL Exibições do carrinho] | Total de exibições do carrinho. |
| [!UICONTROL Check-outs] | Total de finalizações. |
| *Evento n* | Número de vezes par *n* ocorreu. Valores válidos para n são inteiros entre 1 - 100.  Se você especificar uma [!UICONTROL Exibir] , você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. |
| [!UICONTROL Exibições do eVar ]*n*. | Total de vezes que o evento *n* ocorreu. Valores válidos para *n* são inteiros entre 1 - 75. |
| [!UICONTROL Preço] | Preço do produto. |
| [!UICONTROL Pedidos] | Total de pedidos feitos. |
| [!UICONTROL Exibições do produto] | Total de exibições do produto. |
| [!UICONTROL Quantidade] | Total de unidades vendidas. |
