---
description: (Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.
seo-description: (Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.
seo-title: Modelo de classificação
solution: Analytics
subtopic: Classificações
title: Modelo de classificação
topic: Ferramentas administrativas
uuid: 4edd411b-164c-4b4d-a872-b57a3163ca72
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Modelo de classificação

(Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

## Modelo de classificação {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

**[!UICONTROL Admin]** &gt; Importador **[!UICONTROL de classificação]**.

| Elemento | Descrição |
|---|---|
| Selecionar o Conjunto de relatórios | Selecione o conjunto de relatórios que será usado no modelo. O conjunto de relatórios deve corresponder ao conjunto de dados. |
| Conjunto de dados a ser classificado | Selecione o tipo de dados para o arquivo de dados. O menu inclui todos os relatórios em seus conjuntos de relatórios configurados para classificações. |
| Exportar numérico 2 | É possível importar classificações numéricas 2 para o sistema por meio do importador. As classificações numéricas 2 são úteis para variáveis que mudam ao longo do tempo para itens diferentes, como valores de custo e orçamento para o relatório [!UICONTROL Canal de Marketing]. See [Numeric 2 Classifications](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) for information about uploading data using numeric 2 classifications. |
| Codificação | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8. |
| Baixar | Faz o download do arquivo modelo. |

O modelo inclui as classificações atualmente definidas (cabeçalhos de coluna) de um conjunto de dados específico, sem incluir os dados associados a cada classificação.

> [!NOTE] O método Modelo limita o download de dados de classificação para um único conjunto de relatórios.

Para obter mais informações sobre a estrutura do arquivo de dados, consulte [Sobre arquivos](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)de dados de classificação.

## Fazer download de um modelo de dados de classificações (opcional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

O modelo fornece o formato de arquivo que deve ser seguido para as classificações.

> [!NOTE] O método Modelo limita o download de dados para um único conjunto de relatórios.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).
1. Clique em **[!UICONTROL Baixar]**.
1. Salve o arquivo de modelo em seu sistema local.

   The template file is a tab-delimited data file ( [!DNL .tab] filename extension) that most spreadsheet applications support.

