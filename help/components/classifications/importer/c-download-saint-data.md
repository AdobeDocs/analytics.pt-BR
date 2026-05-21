---
description: (Opcional) Antes de importar classificações para relatórios de marketing, você pode baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.
title: Modelo de classificação
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
TQID: https://experienceleague.adobe.com/OR9THCLd93iUl58npPiinO4yAsK8KG3FU8qmBILHioY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 355
ht-degree: 61%

---

# Modelo de classificação (herdado)

{{classification-importer-deprecation}}

(Opcional) Antes de importar classificações para relatórios e projetos, você pode baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

## Modelo de classificação {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Opcional) Antes de importar classificações para relatórios de marketing, você pode baixar um modelo que ajuda a criar um arquivo de dados de classificações. O arquivo de dados usa suas classificações desejadas como cabeçalho de coluna, e então organiza o conjunto de dados do relatório dentro dos cabeçalhos de classificação apropriados.

**[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.

| Elemento | Descrição |
| --- | ---|
| Selecione o Conjunto de relatórios | Selecione o conjunto de relatórios a ser usado no modelo. O conjunto de relatórios e o conjunto de dados devem corresponder. |
| Conjunto de dados a ser classificado | Selecione o tipo de dados para o arquivo de dados. O menu inclui todos os relatórios em seus conjuntos de relatórios configurados para classificações. |
| Exportar numérico 2 | **Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |
| Codificação | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova Arquitetura de Classificação. |
| Baixar | Baixa o arquivo de modelo. |

O modelo inclui as classificações definidas no momento (títulos de coluna) de um conjunto de dados específico sem incluir os dados associados a cada classificação.

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
