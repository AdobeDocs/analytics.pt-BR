---
title: Esquema do conjunto de classificação
description: Exibir e editar o esquema para um conjunto de classificações individual.
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: a2a5e29eee46840d894ebf8d6184f8d6af9eee29
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 36%

---

# Esquema

Exibir dimensões de classificação configuradas no momento para este conjunto de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > Clique no nome do conjunto de classificações desejado > **[!UICONTROL Esquema]**

![interface do esquema do conjunto de classificações](../../assets/classification-set-schema.png)

Os seguintes botões estão disponíveis:

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Carregar]**: carregar manualmente os dados de classificação de uma dimensão de classificação. Há suporte para arquivos `JSON`, `CSV`, `TSV` e `TAB`. O upload de um arquivo válido mostra uma visualização em tabela dos dados que serão classificados.
   * **[!UICONTROL Codificação de arquivo]**: selecione a codificação de arquivo correta usando esta lista suspensa. As opções válidas incluem [!UICONTROL UTF-8] e [!UICONTROL Latin1].
   * **[!UICONTROL Delimitador de lista]**: selecione o delimitador de lista correto. Se estiver usando um arquivo baixado ou um arquivo de modelo, verifique se esse [!UICONTROL delimitador de lista] corresponde ao [!UICONTROL delimitador de lista] de quando o arquivo foi baixado.
   * **[!UICONTROL Aplicar]**: salvar os dados de classificação carregados no conjunto de classificações.

  ![Carregamento do conjunto de classificações](../../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: baixar os valores principais e suas colunas de classificação.
   * **[!UICONTROL Linhas]**: o número máximo de linhas a serem incluídas no arquivo de download.
   * **[!UICONTROL Baixar linhas recebidas entre]**: um seletor de datas do calendário que permite filtrar os valores principais baseado em quando eles aparecem no relatório. Se um valor principal não tiver sido coletado nesse intervalo de datas, ele não aparecerá no arquivo baixado.
   * **[!UICONTROL Dados retornados]**: uma lista suspensa que permite filtrar os valores principais incluídos no arquivo baixado com base nos dados de classificação associados.
      * **[!UICONTROL Todos os valores classificados]**: inclui linhas em que os dados de classificação estão incluídos em pelo menos uma coluna.
      * **[!UICONTROL Todos os valores não classificados]**: inclui linhas em que os dados de classificação estão ausentes em pelo menos uma coluna.
   * **[!UICONTROL Formato de arquivo]**: uma lista suspensa que determina o formato do arquivo baixado. As opções incluem [!UICONTROL JSON], [!UICONTROL Valores separados por vírgula (CSV)] e [!UICONTROL Valores separados por tabulação do Excel].
   * **[!UICONTROL Codificação de arquivo]**: uma lista suspensa que determina a codificação do arquivo. As opções incluem [!UICONTROL UTF-8] e [!UICONTROL Latin1]. É recomendado usar UTF-8.

  ![Download do conjunto de classificações](../../assets/classification-set-download.png)

* **[!UICONTROL Modelo]**: baixar um arquivo de modelo. Esse arquivo é semelhante ao botão [!UICONTROL Download], exceto por não conter dados de classificação ou valores principais.
   * **[!UICONTROL Formato de arquivo]**: uma lista suspensa que determina o formato do arquivo de modelo. As opções incluem [!UICONTROL Valores separados por vírgula (CSV)] e [!UICONTROL Valores separados por tabulação do Excel].
   * **[!UICONTROL Codificação de arquivo]**: uma lista suspensa que determina a codificação do arquivo. As opções incluem [!UICONTROL UTF-8] e [!UICONTROL Latin1]. É recomendado usar UTF-8.
   * **[!UICONTROL Delimitadores de lista]**: uma lista suspensa que determina o delimitador da lista que separa as colunas de classificação em cada linha.

  ![Modelo do conjunto de classificações](../../assets/classification-set-template.png)

* **[!UICONTROL Histórico de trabalhos]**: um link de atalho que direciona você ao [Gerenciador de trabalhos](../job-manager.md), mostrando os trabalhos somente para este conjunto de classificações.
* **[!UICONTROL Automatizar]**: assimilar dados automaticamente de locais de armazenamento externo.
   * **[!UICONTROL Conta de localização]**: uma lista suspensa que mostra as contas de localização existentes que sua organização configurou. Se sua organização ainda não tiver configurado uma conta de localização, você poderá configurar uma selecionando [!UICONTROL **Criar uma nova conta**].

     Para obter informações sobre como configurar a conta de localização, consulte [Configurar contas de importação e exportação da nuvem](/help/components/locations/configure-import-accounts.md).

   * **[!UICONTROL Local]**: uma lista suspensa que mostra locais existentes que sua organização configurou. Se sua organização ainda não tiver configurado um local, você poderá configurar um selecionando [!UICONTROL **Criar um novo local**].

     Para obter informações sobre como configurar um local, consulte [Configurar locais de importação e exportação da nuvem](/help/components/locations/configure-import-locations.md).

   * **[!UICONTROL Delimitador]**: o delimitador de coluna para arquivos carregados. As opções incluem [!UICONTROL Vírgula], [!UICONTROL Ponto e vírgula], [!UICONTROL Dois-pontos], [!UICONTROL Barra vertical], [!UICONTROL Espaço], [!UICONTROL Barra inclinada], [!UICONTROL Barra invertida], [!UICONTROL Traço] ou [!UICONTROL Sublinhado].

   * **[!UICONTROL Codificação]**: uma lista suspensa que determina a codificação do arquivo. As opções incluem [!UICONTROL UTF-8] e [!UICONTROL Latin1]. É recomendado usar UTF-8.

As ações a seguir estão disponíveis somente após selecionar uma classificação.

* **Adicionar pesquisa**: uma tabela de pesquisa é uma classificação de uma classificação. São metadados sobre um valor de classificação, em vez da própria variável. Por exemplo, a variável Product pode ter uma classificação de &quot;código de cor&quot;. Uma tabela de pesquisa de &quot;nome da cor&quot; pode ser anexada ao &quot;código de cor&quot; para explicar quais são as cores.

  ![Anexar tabela de pesquisa](../../assets/lookup.png)

* **Renomear**: permite renomear a classificação.

* **Excluir**: permite excluir a classificação.
