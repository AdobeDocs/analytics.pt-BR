---
description: As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.
subtopic: Data sources
title: Conversão
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 00450ad4-7148-4cf1-bdba-5d1732dd0fd3
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 100%

---

# Conversão

As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.

## Dimensões e métricas de conversão {#section_FA1731B232B246DABEDF5A5D84159084}

Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. O total de eventos personalizados e exibições eVar apoiados por um conjunto de relatórios depende de contrato, e varia de acordo com cada empresa.

<p class="head"> <b>Dimensões de conversão</b> </p>

| Nome da coluna | Descrição |
|--- |--- |
| Código de rastreamento | Nome do Código de rastreamento. |
| Data | Use o seguinte formato de data: MM/DD/AAAA/HH/mm/SS (por exemplo, 01/01/2015/06/00/00) |
| Categoria | Nome da categoria.  Se você especificar uma categoria, você também deve selecionar um produto. |
| Canal | Nome do canal. |
| eVarn | Nome da eVarn. Valores válidos para n são inteiros entre 1 - 250. |
| Produto | Nome do produto. |
| Estado | Nome do estado. |
| CEP | Nome do CEP. |

<p class="head"> <b>Métricas de Conversão</b> </p>

| Nome da coluna | Descrição |
|--- |--- |
| Click-throughs | Total de visualizações do Código de rastreamento. |
| Adições ao carrinho | Total de adições ao carrinho. |
| Aberturas do carrinho | Total de aberturas do carrinho. |
| Remoções do carrinho | Total de remoções do carrinho. |
| Visualizações do carrinho | Total de visualizações do carrinho. |
| Check-outs | Total de check-outs. |
| Evento n | Total de vezes que o evento n ocorreu. Valores válidos para n são inteiros entre 1 - 100.  Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. |
| Exibições da eVarn | Total de vezes que o eVar n foi visualizado. Valores válidos para n são inteiros entre 1 - 250. |
| Preço | Preço do produto. |
| Pedidos | Total de pedidos feitos. |
| Visualizações de produto | Total de visualizações do produto. |
| Quantidade | Total de unidades vendidas. |
