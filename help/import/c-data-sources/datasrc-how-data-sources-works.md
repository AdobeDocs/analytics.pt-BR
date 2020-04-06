---
description: Informações sobre a maneira pela qual a Adobe fornece acesso às Fontes de dados.
subtopic: Data sources
title: Como a Fonte de dados funciona
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Como a Fonte de dados funciona

Informações sobre a maneira pela qual a Adobe fornece acesso às Fontes de dados.

>[!NOTE] Após carregar os dados por meio das Fontes de dados, os dados importados tornam-se indistinguíveis dos dados do relatório obtidos por outros meios (JavaScript beacon, ActionSource, API de inserção de dados etc.). Não é possível remover os dados depois de importados.

![](assets/data_sources_overview.png)

Dois métodos estão disponíveis para enviar dados:

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Você pode criar e gerenciar fontes de dados baseadas em FTP por meio de relatórios de marketing, que usam a transferência de arquivos FTP para importar arquivos de dados para as Fontes de Dados. Após criar uma fonte de dados, o Adobe oferece a você um local FTP que você pode usar para carregar arquivos da Fonte de Dados. Após serem carregados, as Fontes de Dados automaticamente os localiza e processa. Depois de processados, os dados ficam disponíveis para relatórios de marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

A Adobe oferece uma API de Fontes de dados que permite que você vincule, de maneira programática, seus aplicativos nas Fontes de dados. Isso elimina a necessidade de um servidor FTP intermediário e transfere dados via HTTP, SOAP e REST.

Consulte Documentação [da API das Fontes](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)de Dados.
