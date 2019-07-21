---
description: Etapas que descrevem como excluir ou remover dados da classificação.
seo-description: Etapas que descrevem como excluir ou remover dados da classificação.
seo-title: Excluir dados de classificação
solution: Analytics
subtopic: Classificações
title: Excluir dados de classificação
topic: Ferramentas administrativas
uuid: 5 b 1 b 0 ac 7-ee 52-4 fd 8-b 98 e -25283595 cf 0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Excluir dados de classificação

Etapas que descrevem como excluir ou remover dados da classificação.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. Selecione o conjunto de relatórios e o conjunto de dados dos quais deseja remover os dados de classificação.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. Esse comando trata a classificação como se nunca tivesse ocorrido na tecla especificada. Remove completamente a classificação e todos os dados da coluna nas tabelas de pesquisa.

   **Advertência**: Você precisa apenas de uma coluna contendo [!DNL ~excluirtecla~]. The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. Esse comando remove todos os metadados da linha. A Adobe interpreta isso como se a tecla nunca tivesse sido classificada e a exibe na [categoria](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF) Nenhum.

1. Salve o arquivo e faça upload utilizando a guia [!UICONTROL Importar arquivo.]

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **Propriedades desse comando**

* [!DNL ~vazio~] deve estar em letras minúsculas sem espaços. As entradas a seguir são inválidas:

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* Não é possível excluir os valores na coluna principal. Esses dados foram passados diretamente para o relatório e são permanentes.
* Se você estiver removendo um valor de classificação que possua subclassificações, eles também serão removidos. As classificações não podem existir sem um valor principal, e o pai de uma subclassificação é seu valor principal.
* É possível remover dados de subclassificação deixando sua classificação pai intacta.

