---
description: (Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.
title: Modelo de classificação
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 99%

---

# Modelo de classificação (herdado)

{{classification-importer-deprecation}}

(Opcional) Antes de importar classificações para relatórios e projetos, você pode baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

## Modelo de classificação {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Opcional) Antes de importar as classificações para os relatórios de marketing, é possível fazer o download de um modelo que ajude você a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

**[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.

| Elemento | Descrição |
| --- | ---|
| Selecione o Conjunto de relatórios | Selecione o conjunto de relatórios que será usado no modelo. O conjunto de relatórios deve corresponder ao conjunto de dados. |
| Conjunto de dados a ser classificado | Selecione o tipo de dados para o arquivo de dados. O menu inclui todos os relatórios em seus conjuntos de relatórios configurados para classificações. |
| Exportar numérico 2 | **Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |
| Codificação | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |
| Baixar | Faz o download do arquivo modelo. |

O modelo inclui as classificações atualmente definidas (cabeçalhos de coluna) de um conjunto de dados específico, sem incluir os dados associados a cada classificação.

>[!NOTE]
>
>O método Modelo limita o download de dados de classificação para um único conjunto de relatórios.

Para obter mais informações sobre a estrutura do arquivo de dados, consulte [Sobre arquivos de dados de classificação](/help/components/classifications/importer/c-saint-data-files.md).

## Fazer download de um modelo de dados de classificações (opcional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

O modelo fornece o formato de arquivo que deve ser seguido para as classificações.

>[!NOTE]
>
>O método Modelo limita o download de dados a um único conjunto de relatórios.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.
1. Na guia **[!UICONTROL Download de modelo]**, especifique a [configuração do modelo de dados](/help/components/classifications/importer/c-download-saint-data.md).
1. Clique em **[!UICONTROL Baixar]**.
1. Salve o arquivo de modelo em seu sistema local.

   O arquivo de modelo é um arquivo de dados delimitado por tabulação (extensão de arquivo [!DNL .tab]) que a maioria dos aplicativos de planilha eletrônica suporta.
