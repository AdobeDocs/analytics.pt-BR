---
title: Esquema do conjunto de classificações
description: Saiba como visualizar e editar o esquema para um conjunto de classificações individual.
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: f34072ec42d62cef0a3e1fd4d63f6f39693cf0fd
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 4%

---

# Esquema do conjunto de classificação

O esquema é a lista de classificações que você deseja aplicar às dimensões principais definidas para o conjunto de classificações. Por exemplo, se você tiver definido o produto como a dimensão principal e esse campo contiver um SKU de produto, você usará o esquema para adicionar classificações como nome do produto, cor do produto, tamanho do produto e muito mais.

Para editar o esquema de um conjunto de classificações:


1. Selecione **[!UICONTROL Componentes]** na barra de menu superior do Adobe Analytics e selecione **[!UICONTROL Conjuntos de classificações]**.
1. Em **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Conjuntos de classificações]**.
1. No gerenciador **[!UICONTROL Conjuntos de classificações]**, selecione o conjunto de classificações no qual deseja editar o esquema.
1. Na caixa de diálogo **[!UICONTROL Conjunto de classificações: _nome do conjunto de classificações_]**, selecione a guia **[!UICONTROL Esquema]**. Essa guia consiste nos seguintes elementos de interface:

   ![Conjuntos de classificações - esquema](assets/classification-sets-schema.png)

   * [Lista de classificações](#classification-list)
   * [Pesquisar](#search)
   * [Ações](#actions)
   * [Barra de ação](#action-bar)

## Lista de classificações

A lista de classificações tem as seguintes colunas:

| Coluna | Descrição |
|---|---|
| **[!UICONTROL Nome da Classificação]** | O nome fornecido para a classificação. |
| **[!UICONTROL Nome da Identidade]** | O nome derivado do sistema para a classificação. É um valor somente leitura e você pode usar o nome de identidade |
| **[!UICONTROL Classificado por]** | Se usada, um link para o conjunto de classificações de pesquisa usado para classificar essa classificação. |


## Pesquisar

Você pode pesquisar rapidamente ![Pesquisar](/help/assets/icons/Search.svg) por uma ou mais classificações. Use ![CrossSize100](/help/assets/icons/CrossSize100.svg) para limpar a pesquisa.

## Ações

As seguintes ações estão disponíveis como botões na parte superior da lista de classificações:

| Ícone | Ação | Descrição |
|---|---|---|
| ![Adicionar](/help/assets/icons/Add.svg) | **[!UICONTROL Adicionar]** | [Adicionar uma classificação](#add) à lista. |
| ![CarregarParaNuvem](/help/assets/icons/UploadToCloud.svg) | **[!UICONTROL Carregar]** | [Carregar um arquivo JSON, CSV, TSV ou TAB](#upload). |
| ![Baixar](/help/assets/icons/Download.svg) | **[!UICONTROL Baixar]** | [Baixar dados de classificação](#download). |
| ![FragmentoDocumento](/help/assets/icons/DocumentFragment.svg) | **[!UICONTROL Modelo]** | [Baixe um modelo](#template) para dados de classificação. |
| ![Histórico](/help/assets/icons/History.svg) | **[!UICONTROL Histórico do Trabalho]** | Mostrar o [gerenciador de trabalhos do conjunto de classificações](/help/components/classifications/sets/job-manager.md), filtrado para o conjunto de classificações selecionado. |
| ![Engrenagem](/help/assets/icons/Gear.svg) | **[!UICONTROL Automatizar]** | [Automatize a assimilação de dados de classificação](#automate) por meio do uso de um local na nuvem. |


### Adicionar

Para adicionar uma nova classificação, selecione ![Adicionar](/help/assets/icons/Add.svg) **[!UICONTROL Adicionar]**.

![Conjuntos de classificações - Adicionar classificação ao esquema](assets/classification-sets-schema-add-classification.png)

Na caixa de diálogo **[!UICONTROL Adicionar uma nova classificação para _nome do conjunto de classificações_]**, digite o **[!UICONTROL Nome da Classificação]**e selecione **[!UICONTROL Adicionar]**. A classificação é adicionada à lista.



### Carregar

Para importar dados de classificação para o esquema de uma classificação, selecione ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) **[!UICONTROL Upload]**.


![Conjuntos de classificação - Carregamento de esquema um arquivo](assets/classification-sets-schema-upload-file.png)

1. Na caixa de diálogo **[!UICONTROL Adicionar novas classificações]**:

   * Arraste um arquivo que contenha dados de classificação e solte-o em **[!UICONTROL Arraste e solte aqui]**.
   * Selecione **[!UICONTROL Procurar]** e escolha um arquivo do computador ou da rede.

   Você vê uma **[!UICONTROL Visualização do esquema]** do conteúdo do arquivo. A visualização mostra as colunas de dados do arquivo. Para redimensionar uma coluna, selecione ![ChevronDownSize300](/help/assets/icons2/ChevronDownSize300.svg) e **[!UICONTROL Redimensionar coluna]**. É exibido um identificador que permite redimensionar a coluna.

   Quando nenhuma classificação é definida no conjunto de classificações de uma coluna, um alerta ![Alerta](/help/assets/icons/Alert.svg) é exibido. O alerta explica que uma classificação não está presente no conjunto de esquemas de classificação existente e será criada na importação.

1. Selecionar **[!UICONTROL Substituir dados em conflito?]** se desejar substituir os dados de classificação atuais pelos novos dados importados. Por exemplo:

   | | Chave | Cor atual do produto | Importar arquivo | Nova cor do produto |
   |---|---|---|---|---|
   | ![SelectBox](/help/assets/icons/SelectBox.svg) **[!UICONTROL Substituir dados em conflito?]** | 1234 | verde | azul | azul |
   | ![Quadrado](/help/assets/icons2/Square.svg) **[!UICONTROL Substituir dados em conflito?]** | 1234 | verde | azul | verde |

1. Selecione **[!UICONTROL Aplicar]**. Um alerta é exibido se as colunas não estiverem presentes como classificações no conjunto de esquemas existente. Essas colunas são adicionadas como novas classificações ao confirmar o upload.

   ![Conjunto de classificações - Carregar alerta de classificações](assets/classification-sets-schema-upload-file-preview-alert.png)

   Selecione **[!UICONTROL Confirmar carregamento]** para confirmar o carregamento. Selecione **[!UICONTROL Cancelar Carregamento]** para cancelar o carregamento.


### Baixar

Para baixar dados de classificação, selecione ![Baixar](/help/assets/icons/Download.svg) **[!UICONTROL Baixar]**.

![Conjuntos de classificação - Dados de classificação de download de esquema](assets/classification-sets-schema-download-file.png)

Na caixa de diálogo **[!UICONTROL Baixar dados para _nome do conjunto de classificações_]**:

1. Insira o número de **[!UICONTROL Linhas]** que você deseja baixar. Por exemplo: `10000`.
1. Para selecionar o período para o qual deseja baixar linhas de dados de classificação, insira dados de início e término para **[!UICONTROL Baixar linhas recebidas entre]**. Ou use o ![Calendário](/help/assets/icons/Calendar.svg) para usar um pop-up de calendário para selecionar o período.
1. Para selecionar quais dados retornar, selecione uma opção em **[!UICONTROL Dados Retornados]**.

   * **[!UICONTROL Todos os valores]** retorna todos os valores dos dados de classificação atuais.
   * **[!UICONTROL Qualquer coluna vazia]** retorna uma coluna com valores de chave para os dados de classificação existentes. E colunas sem valor para dados de classificação para os quais não existem valores.
   * **[!UICONTROL Todas as colunas vazias]** retorna uma coluna de chave com valores para os dados de classificação existentes. E colunas sem valor para dados de classificação.
1. Para selecionar o [formato de arquivo](/help/components/classifications/sets/data-files.md#general-file-requirements) dos dados de classificação baixados, selecione uma opção no menu suspenso **[!UICONTROL Formato de Arquivo]**. As opções são:

   * **[!UICONTROL JSON]**.
   * **[!UICONTROL Valores separados por vírgula]** (CSV).
   * **[!UICONTROL Valores separados por tabulação do Excel]** (TSV ou TAB).

1. Para selecionar a [codificação do arquivo](/help/components/classifications/sets/data-files.md#general-file-requirements) para quando o arquivo for baixado, selecione uma opção no menu suspenso Codificação de Arquivo. As opções são:

   * **[!UICONTROL UTF-8]**.
   * **[!UICONTROL Latino-1]**.


1. Selecione **[!UICONTROL Baixar]** para baixar os dados de classificação. Você pode encontrar o arquivo baixado no diretório de download padrão do seu navegador, e o arquivo é intitulado <code><i>Conjunto de classificações</i>.<i>json</i>|<i>csv</i>|<i>tsv</i></code>. Se o arquivo já existir, um número de sequência <code>(<i>x</i>)</code> é adicionado ao nome do arquivo.<br/>Se você tiver especificado opções que não retornam dados, verá uma caixa de diálogo **[!UICONTROL Aviso]** para informá-lo de alterar as opções de intervalo de datas e dados retornados.


### Modelo

Para baixar um modelo para dados de classificação, selecione ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) **[!UICONTROL Modelo]**.

![Esquema dos conjuntos de classificações - Baixar modelo](assets/classification-sets-schema-download-template.png)

Na caixa de diálogo **[!UICONTROL Baixar modelo para _nome do conjunto de classificações_]**:

1. Para selecionar o [formato de arquivo](/help/components/classifications/sets/data-files.md#general-file-requirements) dos dados de classificação baixados, selecione uma opção no menu suspenso **[!UICONTROL Formato de Arquivo]**. As opções são:

   * **[!UICONTROL Valores separados por vírgula]**.
   * **[!UICONTROL Valores separados por tabulação do Excel]**.

1. Para selecionar a [codificação do arquivo](/help/components/classifications/sets/data-files.md#general-file-requirements) para quando o arquivo for baixado, selecione uma opção no menu suspenso Codificação de Arquivo. As opções são:

   * **[!UICONTROL UTF-8]**.
   * **[!UICONTROL Latino-1]**.

1. Selecione **[!UICONTROL Baixar]** para baixar o modelo de dados de classificação. Você pode encontrar o arquivo baixado no diretório de download padrão do seu navegador, e ele é intitulado <code><i>Conjunto de classificações</i>.<i>csv</i>|<i>tsv</i></code>. Se o arquivo já existir, um número de sequência <code>(<i>x</i>)</code> é adicionado ao nome do arquivo.


### Automatizar {#automate}


>[!CONTEXTUALHELP]
>id="classificationsets_schema_automate_locationaccount"
>title="Conta de localização"
>abstract="Lista de contas de localização de tipos de conta que oferecem suporte à importação de dados de classificação. Selecione **[!UICONTROL Nova conta]** para criar uma nova conta de localização."
>additional-url="https://experienceleague.adobe.com/docs/analytics/components/locations/configure-import-accounts.html?lang=en" text="Configurar contas de importação e exportação na nuvem"


>[!CONTEXTUALHELP]
>id="classificationsets_schema_automate_location"
>title="Localização"
>abstract="Lista de locais na conta de localização selecionada que oferecem suporte à importação de dados de classificação. Selecione **[!UICONTROL Novo local]** para criar um novo local."
>additional-url="https://experienceleague.adobe.com/docs/analytics/components/locations/configure-import-locations.html?lang=en" text="Configurar locais de importação e exportação na nuvem"


Para automatizar a assimilação da classificação, selecione ![Engrenagem](/help/assets/icons/Gear.svg) **[!UICONTROL Automatizar]**.

![Esquema dos conjuntos de classificações - Automatizar](assets/classification-sets-schema-automate.png)

Na caixa de diálogo **[!UICONTROL Associar / Atualizar Local de Assimilação para _nome do conjunto de classificações_]**:

1. Para selecionar um local da nuvem, selecione uma opção em **[!UICONTROL Conta da Localização]**. Somente [contas de localização de tipos de conta com suporte que permitem a importação de dados de classificação](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts) são mostradas. Para criar uma nova conta, selecione **[!UICONTROL Nova conta]**.
1. Para selecionar um local, selecione uma opção de **[!UICONTROL Local]**. Somente os locais dos tipos de conta selecionados para a importação de dados de classificação são mostrados. Para criar um novo local, selecione **[!UICONTROL Novo local]**.

   >[!IMPORTANT]
   >
   >O local que você criar ou selecionar deve conter um **[!UICONTROL Prefixo]** (pasta) no **[!UICONTROL Bloco]** para hospedar os arquivos de dados de classificação. Por exemplo, uma pasta chamada `files`. A hospedagem de arquivos na raiz de um bucket não funciona com a maioria dos locais da nuvem.
   >

1. Para selecionar um delimitador, selecione uma opção no menu suspenso **[!UICONTROL Delimitador de lista]**. As opções são:
   * **[!UICONTROL Vírgula,]**
   * **[!UICONTROL Ponto e vírgula ;]**
   * **[!UICONTROL Dois-pontos:]**
   * **[!UICONTROL Barra vertical |]**
   * **[!UICONTROL Espaço]**
   * **[!UICONTROL Guia]**
1. Para selecionar a [codificação do arquivo](/help/components/classifications/sets/data-files.md#general-file-requirements) quando o arquivo for baixado, selecione uma opção no menu suspenso **[!UICONTROL Codificação do Arquivo]**. As opções são:

   * **[!UICONTROL UTF-8]**.
   * **[!UICONTROL Latino-1]**.

1. Para notificar os usuários sobre a conclusão dos trabalhos de assimilação, insira endereços de email, separados por vírgula, para **[!UICONTROL Email(s) a notificar quando os trabalhos de assimilação forem concluídos (separados por vírgula)]**.
1. Selecione **[!UICONTROL Validar]**. A conexão com o local da nuvem é validada.
1. Se a validação for bem-sucedida, você verá uma mensagem em caixa de informações que mostra ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Location validation successful. Conexão com o armazenamento em nuvem verificada.]**<br/>Selecione**[!UICONTROL  Salvar ]**se tiver criado a conexão com a nuvem. Caso contrário, selecione**[!UICONTROL  Atualizar ]**. Ou selecione**[!UICONTROL  Cancelar ]**para cancelar a configuração do local da nuvem.

Ao fazer upload de arquivos no local da nuvem, em 15 minutos o arquivo é detectado e enviado como um trabalho de importação. O resultado desse trabalho de importação é relatado no [Gerenciador de trabalhos de classificações](/help/components/classifications/sets/job-manager.md). Se você for adicionado à lista de usuários para notificar sobre a conclusão de trabalhos de assimilação, também receberá mensagens de email.

Por exemplo:

![Conjuntos de classificações - email de validação do trabalho](assets/job-failed-validation.png){width="400"}


## Barra de ação

A barra de ações mostra as ações disponíveis para a classificação selecionada. As opções disponíveis são:

| Ícone | Ação | Descrição |
|---|---|---|
| ![Procurar](/help/assets/icons/Browse.svg) | **[!UICONTROL Adicionar Pesquisa]** | Adicione um conjunto de classificações como uma pesquisa (subclassificação).<br/>Na tabela **[!UICONTROL Anexar pesquisa]**: <ol><li>Selecione uma classificação de pesquisa no menu suspenso **[!UICONTROL Nome da Classificação]**.</li><li>Selecione **[!UICONTROL Adicionar]**.</li></ol>A classificação de pesquisa é adicionada à classificação e listada na coluna **[!UICONTROL Classificado por]** usando a ID interna. |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) | **[!UICONTROL Remover Pesquisa]** | Remova um conjunto de classificações como uma pesquisa. Para excluir a pesquisa permanentemente da classificação, na caixa de diálogo de confirmação **[!UICONTROL Remover _conjunto de classificações_ da _classificação_]**, selecione **[!UICONTROL Excluir]**. |
| ![Renomear](/help/assets/icons/Rename.svg) | **[!UICONTROL Renomear]** | Renomeie o **[!UICONTROL Nome da Classificação]** de uma classificação. Na caixa de diálogo **[!UICONTROL Renomear: _nome da classificação_]**, digite um novo nome e selecione **[!UICONTROL Renomear]**. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Excluir uma classificação. A caixa de diálogo **[!UICONTROL Excluir _nome da classificação_]**é exibida. Selecione **[!UICONTROL Excluir]**para excluir a classificação. |


<!--

View currently configured classification dimensions for this classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Click the desired classification set name > **[!UICONTROL Schema]**

![classification set schema UI](../../assets/classification-set-schema.png)

The following buttons are available:


* **[!UICONTROL Upload]**: Manually upload classification data for a classification dimensions. `JSON`, `CSV`, `TSV`, and `TAB` files are supported. Uploading a valid file shows a table preview of data to classify.
  * **[!UICONTROL File encoding]**: Select the correct file encoding using this drop-down. Valid options include [!UICONTROL UTF-8] and [!UICONTROL Latin1].
  * **[!UICONTROL List delimiter]**: Select the correct list delimiter. If using a downloaded file or template file, make sure that the [!UICONTROL List delimiter] here matches the [!UICONTROL List delimiter] when the file was downloaded.
  * **[!UICONTROL Apply]**: Save the uploaded classification data to the classification set.

  ![Classification set upload](../../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: Download key values and their classification columns.
  * **[!UICONTROL Rows]**: The maximum number of rows to include in the download file.
  * **[!UICONTROL Download rows received between]**: A calendar date picker that allows you to filter key values by when they appear in reporting. If a key value was not collected in this date range, it does not appear in the downloaded file.
  * **[!UICONTROL Data returned]**: A drop-down list that lets you filter key values included in the downloaded file based on their associated classification data.
    * **[!UICONTROL All classified values]**: Includes rows where classification data is included in at least one column.
    * **[!UICONTROL All unclassified values]**: Includes rows where classification data is missing in at least one column.
  * **[!UICONTROL File format]**: A drop-down list that determines the file format that the download file is in. Options include [!UICONTROL JSON], [!UICONTROL Comma separated values], and [!UICONTROL Excel tab separated values].
  * **[!UICONTROL File encoding]**: A drop-down list that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.

  ![Classification set download](../../assets/classification-set-download.png)

* **[!UICONTROL Template]**: Download a template file. This file is similar to the [!UICONTROL Download] button, except it does not contain any classification data or key values.
  * **[!UICONTROL File format]**: A drop-down list that determines the file format that the template file is in. Options include [!UICONTROL Comma separated values], and [!UICONTROL Excel tab separated values].
  * **[!UICONTROL File encoding]**: A drop-down list that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.
  * **[!UICONTROL List delimiters]**: A drop-down list that determines the list delimiter separating classification columns on each row.

  ![Classification set template](../../assets/classification-set-template.png)

* **[!UICONTROL Job history]**: A shortcut link that takes you to the [Job manager](../job-manager.md), showing jobs only for this classification set.
* **[!UICONTROL Automate]**: Automatically ingest data from external storage locations.
  * **[!UICONTROL Location account]**: A drop-down list showing existing location accounts that your organization has configured. If your organization hasn't already configured a location account, you can configure one by selecting [!UICONTROL **Create a new account**].
    
    For information about configuring the location account, see [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md).

  * **[!UICONTROL Location]**: A drop-down list showing existing locations that your organization has configured. If your organization hasn't already configured a location, you can configure one by selecting [!UICONTROL **Create a new location**]. 

    For information about configuring a location, see [Configure cloud import and export locations](/help/components/locations/configure-import-locations.md). 

  * **[!UICONTROL Delimiter]**: The column delimiter for uploaded files. Options include [!UICONTROL Comma], [!UICONTROL Semicolon], [!UICONTROL Colon], [!UICONTROL Vertical bar], [!UICONTROL Space], [!UICONTROL Forward slash], [!UICONTROL Backward slash], [!UICONTROL Dash], or [!UICONTROL Underscore].

  * **[!UICONTROL Encoding]**: A drop-down list that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.

The following actions are available only after selecting a classification.

* **Add lookup**: A lookup table is a classification of a classification. It is metadata about a classification value, rather than the variable itself. For example, the Product variable might have a classification of "color code". A lookup table of "color name" might be attached to "color code" to explain what the colors are.

  ![Attach lookup table](../../assets/lookup.png)

* **Rename**: Lets you rename the classification.

* **Delete**: Lets you delete the classification.
-->