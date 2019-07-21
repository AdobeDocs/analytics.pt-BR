---
description: (Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.
seo-description: (Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.
seo-title: Modelo de classificação
solution: Analytics
subtopic: Classificações
title: Modelo de classificação
topic: Ferramentas administrativas
uuid: 4 edd 411 b -164 c -4 b 4 d-a 872-b 57 a 3163 ca 72
translation-type: tm+mt
source-git-commit: 1986561a83f22619b627d754376f7e936902a737

---


# Modelo de classificação

(Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

## Classification template {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

**[!UICONTROL Administração]** &gt; **[!UICONTROL Importador de classificação]**.

| Elemento | Descrição |
|---|---|
| Selecionar o Conjunto de relatórios | Selecione o conjunto de relatórios que será usado no modelo. O conjunto de relatórios deve corresponder ao conjunto de dados. |
| Conjunto de dados a ser classificado | Selecione o tipo de dados para o arquivo de dados. O menu inclui todos os relatórios em seus conjuntos de relatórios configurados para classificações. |
| Exportar numérico 2 | É possível importar classificações numéricas 2 para o sistema por meio do importador. As classificações numéricas 2 são úteis para variáveis que mudam ao longo do tempo para itens diferentes, como valores de custo e orçamento para o relatório [!UICONTROL Canal de Marketing]. See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications. |
| Codificação | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8. |
| Download | Faz o download do arquivo modelo. |

O modelo inclui as classificações atualmente definidas (cabeçalhos de coluna) de um conjunto de dados específico, sem incluir os dados associados a cada classificação.

>[!NOTE]
>
>O método Modelo limita o download de dados de classificação para um único conjunto de relatórios.

For more information about the data file structure, see [About Classification Data Files](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

## Fazer download de um modelo de dados de classificações (opcional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

O modelo fornece o formato de arquivo que deve ser seguido para as classificações.

>[!NOTE]
>
>O método Modelo limita o download de dados para um único conjunto de relatórios.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).
1. Clique em **[!UICONTROL Baixar]**.
1. Salve o arquivo de modelo em seu sistema local.

   The template file is a tab-delimited data file ( [!DNL .tab] filename extension) that most spreadsheet applications support.

