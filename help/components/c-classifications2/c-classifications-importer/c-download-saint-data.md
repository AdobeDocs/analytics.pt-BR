---
description: (Opcional) Antes de importar classificações para relatórios de marketing, é possível baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalhos de coluna e, em seguida, organiza o conjunto de dados do relatórios nos cabeçalhos de classificação apropriados.
subtopic: Classifications
title: Modelo de classificação
topic: Admin tools
uuid: 4edd411b-164c-4b4d-a872-b57a3163ca72
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Modelo de classificação

(Opcional) Antes de importar classificações para relatórios de marketing, é possível baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalhos de coluna e, em seguida, organiza o conjunto de dados do relatórios nos cabeçalhos de classificação apropriados.

## Modelo de classificação {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Opcional) Antes de importar classificações para relatórios de marketing, é possível baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalhos de coluna e, em seguida, organiza o conjunto de dados do relatórios nos cabeçalhos de classificação apropriados.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

| Elemento | Descrição |
|---|---|
| Selecione o Conjunto de relatórios | Selecione o conjunto de relatórios a ser usado no modelo. O conjunto de relatórios e o conjunto de dados devem corresponder. |
| Conjunto de dados a ser classificado | Selecione o tipo de dados para o arquivo de dados. O menu inclui todos os relatórios em seus conjuntos de relatórios configurados para classificações. |
| Exportar Numérico 2 | É possível importar classificações numéricas 2 para o sistema por meio do importador. As classificações numéricas 2 são úteis para variáveis que mudam ao longo do tempo para itens diferentes, como valores de custo e orçamento do [!UICONTROL Marketing Channel] relatório. Consulte [Classificações numéricas 2](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md) para obter mais informações sobre como fazer upload de dados usando as classificações numéricas 2. |
| Codificação | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8. |
| Baixar | Faz o download do arquivo de modelo. |

O modelo inclui as classificações atualmente definidas (cabeçalhos de coluna) de um conjunto de dados específico sem incluir os dados associados a cada classificação.

>[!NOTE] O método Modelo limita o download de dados de classificação para um único conjunto de relatórios.

Para obter mais informações sobre a estrutura do arquivo de dados, consulte [Sobre arquivos de dados de classificação](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

## Fazer download de um modelo de dados de classificações (opcional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

O modelo fornece o formato de arquivo que deve ser seguido para as classificações.

>[!NOTE] O método Modelo limita o download de dados a um único conjunto de relatórios.

1. Clique em **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md).
1. Clique em **[!UICONTROL Download]**.
1. Salve o arquivo de modelo em seu sistema local.

   O arquivo de modelo é um arquivo de dados delimitado por tabulação (extensão de arquivo [!DNL .tab]) que a maioria dos aplicativos de planilha eletrônica suporta.

