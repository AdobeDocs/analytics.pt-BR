---
title: Visão geral das classificações
description: Personalizar o agrupamento de itens de dimensão.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 2e07f1b9495801383b030b2396e5468c39299f50
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 71%

---

# Visão geral das classificações

Uma classificação é uma forma de categorização de dados variáveis do Analytics, que exibe os dados de diferentes maneiras quando você gera os relatórios. Você estabelece uma relação entre um valor de variável e os metadados relacionados a esse valor. As classificações podem ser usadas na maioria das dimensões personalizadas, como [Código de rastreamento](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) e [eVars](/help/components/dimensions/evar.md).

* **Conjuntos de classificação** são os componentes principais para classificar dados. Os [conjuntos de classificação](/help/components/classifications/sets/overview.md) permitem criar e gerenciar classificações em uma única interface simplificada.

* As **classificações legadas** documentam os métodos de classificação legados para classificar dados. Esses métodos serão descontinuados em breve e não estarão mais acessíveis.

   * [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md): crie regras que atribuem um determinado item de dimensão a um item de dimensão de classificação. Esse método para classificar dados é melhor quando uma dimensão encontra frequentemente novos valores únicos ou quando as classificações manuais são frequentes e trabalhosas. Essa funcionalidade será substituída após 28 de fevereiro de 2027.

   * [Importador de classificação](/help/components/classifications/importer/c-working-with-saint.md): exporte uma planilha modelo com itens de dimensão em cada linha. As colunas representam cada classificação de uma dimensão. Esse método para classificar dados é melhor quando todos os itens de dimensão são conhecidos e não requer atualização frequente. Essa funcionalidade será substituída após 31 de agosto de 2026. Com a descontinuação, não será mais possível importar classificações usando o FTP padrão.

Uma única dimensão pode ter múltiplas dimensões de classificação. Por exemplo, você pode classificar [!UICONTROL IDs de produto] com atributos de produto adicionais, como nome do produto, cor, tamanho, descrição e SKU. Cada um desses atributos seria uma dimensão de classificação separada pertencente à mesma dimensão principal. A inclusão desses atributos em seus relatórios proporciona oportunidades de geração de relatórios mais abrangentes e complexos. Quando uma dimensão contém dados de classificação, uma nova dimensão é disponibilizada no relatório, a qual contém somente itens de dimensão de classificação. Qualquer item de dimensão principal que não tenha um valor de classificação é agrupado em [Não especificado](/help/technotes/unspecified.md)
