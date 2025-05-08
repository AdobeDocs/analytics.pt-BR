---
title: Visão geral das classificações
description: Personalizar o agrupamento de itens de dimensão.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 39%

---

# Visão geral das classificações

Uma classificação é uma forma de categorização de dados variáveis do Analytics, que exibe os dados de diferentes maneiras quando você gera os relatórios. Você estabelece uma relação entre um valor de variável e os metadados relacionados a esse valor. As classificações podem ser usadas na maioria das dimensões personalizadas, como [Código de rastreamento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) e [eVars](/help/components/dimensions/evar.md).

**Os conjuntos de classificações** são a principal maneira de classificar dados. **Regras de classificação** e o **Importador de classificação** são métodos herdados para classificar dados. Todos os dados de classificação, em última análise, operam da mesma forma nos relatórios; você pode combinar qualquer um desses métodos para melhor se adequar ao fluxo de trabalho da sua organização.

* **Conjuntos de classificação**: crie e gerencie classificações e suas regras em uma única interface simplificada.
* **Regras de classificação** (herdadas): criam regras que atribuem um determinado item de dimensão a um item de dimensão de classificação. Esse método para classificar dados é melhor quando uma dimensão encontra frequentemente novos valores únicos ou quando as classificações manuais são frequentes e trabalhosas.
* **Importador de classificação** (herdado): exporte uma planilha de modelo com itens de dimensão em cada linha. As colunas representam cada classificação de uma dimensão. Esse método de classificar dados é melhor quando todos os itens de dimensão são conhecidos e não necessitam de atualização frequente.

Uma única dimensão pode ter múltiplas dimensões de classificação. Por exemplo, é possível classificar [!UICONTROL IDs de produto] com outros atributos de produto, como nome do produto, cor, tamanho, descrição e SKU. Cada um desses atributos seria uma dimensão de classificação separada pertencente à mesma dimensão principal. O aumento de seus relatórios com esses atributos oferece oportunidades de relatórios mais profundas e complexas. Quando uma dimensão contém dados de classificação, ela fica disponível no relatório que contém somente itens de dimensão de classificação. Qualquer item de dimensão pai que não contenha um valor de classificação está agrupado em [Não especificado](/help/technotes/unspecified.md)
