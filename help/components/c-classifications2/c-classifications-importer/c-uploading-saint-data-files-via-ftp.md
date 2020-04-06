---
description: Etapas que descrevem como fazer upload de arquivos de dados por FTP.
subtopic: Classifications
title: Importação de FTP
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Importação de FTP

Etapas que descrevem como fazer upload de arquivos de dados por FTP.

## Importação de FTP {#concept_2F965BE873254546A61FB755F25299FD}

Etapas que descrevem como fazer upload de arquivos de dados por FTP.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

Os seguintes limites recomendados são importantes:

* Muitos arquivos pequenos resultarão em processamento mais lento do que alguns arquivos grandes. Isso se deve à quantidade de enfileiramento e priorização necessários para trabalhos menores.
* Divida arquivos grandes em blocos de 50 MB. Isso não é obrigatório, mas é recomendado porque oferece melhor visibilidade ao progresso no back-end. Além disso, se ocorrerem erros enquanto estamos processando seu trabalho, o trabalho será reiniciado; arquivos grandes resultam em grandes quantidades de trabalho refeito nesse cenário.

A configuração inicial preenche o banco de dados de classificações com um grande conjunto de dados originais ou reestrutura as classificações, em vez de reclassificar algumas linhas ou adicionar linhas.

Após um upload inicial em um conjunto de relatórios (para uma determinada variável ou relatório), a Adobe recomenda carregar somente linhas novas e atualizadas em importações subsequentes. As linhas que não estão sendo alteradas devem ser omitidas de uploads futuros.

Cada novo valor de chave que você carrega conta com seus únicos para essa variável do mês.

Se você excedeu seus únicos do mês, não verá os dados de classificações correspondentes para os únicos que excederam os valores no relatórios. É possível ver essas classificações no data warehouse ou na análise ad hoc.

>[!NOTE] O tempo necessário para processar um arquivo de dados de classificação varia de acordo com o tamanho do arquivo e o número atual de arquivos processados pelos servidores da Adobe. Geralmente, o processamento de arquivos de dados não leva mais de 72 horas.

Antes de fazer upload dos dados por FTP, crie uma conta FTP. Para obter mais informações, consulte [Criar uma conta FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importar classificações por FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Etapas que descrevem como usar uma conta FTP para importar classificações para o Adobe Analytics.

Para obter mais informações sobre como criar uma conta FTP, consulte  [Criar uma conta FTP](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Clique em **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Clique em **[!UICONTROL Import File]**, em seguida, clique em **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Use as informações de acesso do FTP (Host, Logon, Senha) para acessar o servidor FTP usando um cliente FTP de sua escolha.
1. Carregue o arquivo de dados ([!DNL .tab] ou [!DNL .txt]) no servidor FTP.
1. Após fazer upload do arquivo de dados, carregue um arquivo FIN que indica que o arquivo está pronto para o processamento.

   O arquivo é um arquivo vazio que tem o mesmo nome de seu arquivo de dados, com uma extensão de nome de arquivo [!DNL .fin]. Por exemplo, se seu arquivo de dados é [!DNL classdata1.tab], o nome do arquivo é [!DNL classdata1.fin].fin.

Em intervalos regulares, a Adobe recupera arquivos de dados carregados que têm um arquivo FIN associado. A Adobe os importa para os conjuntos de relatórios e conjuntos de dados especificados na configuração da conta FTP.

## Criar uma conta FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Antes de fazer upload dos dados por FTP, crie uma conta FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Veja [FTP e sFTP](https://marketing.adobe.com/resources/help/pt_BR/whitepapers/ftp/) para detalhes adicionais sobre os servidores Adobe FTP.

1. Clique em **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Clique em **[!UICONTROL Import File]**, em seguida, clique em **[!UICONTROL FTP Import]**.
1. Na **[!UICONTROL Import File]** guia, clique em **[!UICONTROL Add New]**.
1. Especifique os detalhes da conta FTP:

   | Elemento | Descrição |
   |---|---|
   | Nome | O nome da conta FTP. |
   | Conjunto de dados a ser classificado | Na lista suspensa, selecione o conjunto de dados (variável de relatório de marketing) que deseja classificar. |
   | Selecionar os conjuntos de relatórios | Selecione os conjuntos de relatórios nos quais deseja classificar o conjunto de dados selecionado. Para selecionar vários conjuntos de relatórios, as classificações de cada conjunto de relatórios selecionado devem ser idênticas. |
   | Substituir dados em conflito | Selecione essa opção para substituir os dados do duplicado. Essa opção é útil se você estiver atualizando classificações existentes. Se você estiver adicionando classificações adicionais, essa opção não é recomendada. |
   | Após a importação ser concluída | Selecione essa opção para exportar automaticamente o conjunto de dados atualizado para a mesma conta FTP depois de Especificar o endereço de email para receber notificações sobre essa conta FTP após a conclusão da importação. |
   | Destinatário da notificação | Especifique o endereço de email para receber notificações sobre essa conta FTP. |
   | Autorizar | (Obrigatório) Autoriza a Adobe a importar automaticamente todos os arquivos de dados enviados para a nova conta FTP. |

1. Clique em **[!UICONTROL Save]**.

Após sua criação, é possível editar ou excluir as contas FTP clicando no link apropriado ao lado da conta FTP desejada.
