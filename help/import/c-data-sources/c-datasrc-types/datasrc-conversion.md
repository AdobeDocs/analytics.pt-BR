---
description: As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.
seo-description: As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.
seo-title: Conversão
solution: Analytics
subtopic: Fontes de dados
title: Conversão
topic: Desenvolvedor e implementação
uuid: 5 e 7907 b 1-6 c 9 c -4073-876 b -410 f 3 a 29767 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conversão

As Fontes de dados oferecem suporte às seguintes dimensões e métricas de dados de conversão para os tipos de dados que são processados como conversão.

## Dimensões e métricas de conversão {#section_FA1731B232B246DABEDF5A5D84159084}

Se você especificar um evento de exibição, você também deve especificar a dimensão de dados correspondente (eVar). Por exemplo, se você incluir exibições eVar2, você deve listar eVar2 com um valor. O total de eventos personalizados e exibições eVar apoiados por um report suite depende de contrato, e varia de acordo com cada empresa.

<p class="head"> <b> Dimensões de conversão</b> </p>

| Nome da coluna | Descrição |
|--- |--- |
| Código de Acompanhamento |  Nome do código de acompanhamento. |
| Data | Use o seguinte formato de data: MM/DD/AAAA/HH/mm/SS (por exemplo, 01/01/2015/06/00/00) |
| Categoria | Nome da categoria.  Se você especificar uma categoria, você também deve selecionar um produto. |
| Canal | Nome do canal. |
| Evarn | Nome do evarn. Valores válidos para n são inteiros entre 1 - 75. |
| Produto | Nome do produto. |
| Estado | Nome do estado. |
| CEP | Nome do CEP. |

<p class="head"> <b>Métricas de Conversão</b> </p>

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