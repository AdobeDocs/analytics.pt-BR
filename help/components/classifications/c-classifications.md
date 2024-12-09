---
title: Visão geral das classificações
description: Personalizar o agrupamento de itens de dimensão.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 62%

---

# Visão geral das classificações

Uma classificação é uma forma de categorização de dados variáveis do Analytics, que exibe os dados de diferentes maneiras quando você gera os relatórios. Você estabelece uma relação entre um valor de variável e os metadados relacionados a esse valor. As classificações podem ser usadas na maioria das dimensões personalizadas, como [Código de rastreamento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) e [eVars](/help/components/dimensions/evar.md).

A Adobe oferece várias maneiras de classificar os dados. Todos os dados de classificação operam da mesma forma nos relatórios, e você pode combinar os métodos que funcionam melhor em sua organização. A Adobe recomenda usar os **conjuntos de classificação**.

* **Conjuntos de classificação**: crie e gerencie classificações e suas regras em uma única interface simplificada.
* **Regras de classificação**: crie regras que atribuem um determinado item de dimensão a um item de dimensão de classificação. Esse método para classificar dados é melhor quando uma dimensão encontra frequentemente novos valores únicos ou quando as classificações manuais são frequentes e trabalhosas.
* **Importador de classificação**: exporte uma planilha modelo com itens de dimensão em cada linha. As colunas representam cada classificação de uma dimensão. Esse método de classificar dados é melhor quando todos os itens de dimensão são conhecidos e não necessitam de atualização frequente.

Uma única dimensão pode ter múltiplas dimensões de classificação. Por exemplo, é possível classificar [!UICONTROL IDs de produto] com outros atributos de produto, como nome do produto, cor, tamanho, descrição e SKU. Cada um desses atributos seria uma dimensão de classificação separada pertencente à mesma dimensão principal. O aumento de seus relatórios com esses atributos oferece oportunidades de relatórios mais profundas e complexas. Quando uma dimensão contém dados de classificação, ela fica disponível no relatório que contém somente itens de dimensão de classificação. Qualquer item de dimensão pai que não contenha um valor de classificação está agrupado em [Não especificado](/help/technotes/unspecified.md)
