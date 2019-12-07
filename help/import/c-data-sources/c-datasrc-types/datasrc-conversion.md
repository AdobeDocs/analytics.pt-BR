---
description: As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.
subtopic: Data sources
title: Conversão
topic: Developer and implementation
uuid: 5e7907b1-6c9c-4073-876b-410f3a29767d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conversão

As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.

## Dimensões e métricas de conversão {#section_FA1731B232B246DABEDF5A5D84159084}

Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. O total de eventos personalizados e exibições eVar apoiados por um report suite depende de contrato, e varia de acordo com cada empresa.

<p class="head"> <b>Dimensões de conversão</b> </p>

| Nome da coluna | Descrição |
|--- |--- |
| Código de Acompanhamento |  Nome do código de acompanhamento. |
| Data | Use o seguinte formato de data: MM/DD/AAAA/HH/mm/SS (por exemplo, 01/01/2015/06/00/00) |
| Categoria | Nome da categoria.  Se você especificar uma categoria, você também deve selecionar um produto. |
| Canal | Nome do canal. |
| eVarn | Nome do eVarn. Valores válidos para n são inteiros entre 1 - 75. |
| Produto | Nome do produto. |
| Estado | Nome do estado. |
| Zip | Nome do CEP. |

<p class="head"> <b>Métricas de Conversão</b> </p>

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
