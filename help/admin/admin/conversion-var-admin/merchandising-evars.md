---
title: eVars de merchandising e métodos de descoberta de produtos
description: Um aprofundamento dos conceitos por trás das eVars de comercialização e como elas processam e alocam dados.
source-git-commit: 746c2cfd3236df7ec7498749015ddf75c1e558f5
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# eVars de merchandising e métodos de descoberta de produtos

Este documento explica os conceitos por trás das eVars de comercialização, que processam e alocam dados de forma diferente das eVars padrão. Também explica como as eVars de merchandising estão relacionadas aos Métodos de descoberta de produtos.

Embora a maioria dos sites de varejo tenha muitas maneiras de encontrar produtos, o Adobe considera que os seguintes são os métodos fundamentais para encontrar produtos que cada cliente de varejo deve rastrear no Adobe Analytics:

* Palavras-chave de pesquisa interna
* Códigos de rastreamento de campanha interna
* Categorias de merchandising/navegação
* Links de venda cruzada

Para os fins deste documento, vamos mapear algumas eVars para as soluções da seguinte maneira:

* eVar2: Palavras-chave de pesquisa interna
* eVar3: Códigos de rastreamento de campanha interna
* eVar4: Categorias de merchandising/navegação
* eVar5: Links de venda cruzada

Podemos usar um eVar adicional para medir o desempenho de todos os métodos de busca de produtos em relação uns aos outros. Além dos métodos de descoberta descritos acima, o eVar incluirá outros métodos de descoberta, como links para páginas de detalhes do produto de sites externos, em sua comparação.

* eVar1: Métodos para encontrar produtos

Você não deve configurar nenhuma dessas variáveis para serem eVars padrão, mas deve configurá-las para serem eVars de merchandising.  Usar eVars de merchandising permite alocar qualquer atividade bem-sucedida nos valores capturados pelas eVars em um nível *por produto* em vez de um nível *por visita/por pedido*. Vou esclarecer a diferença entre a atribuição por produto e por encomenda ao longo do resto deste documento.

