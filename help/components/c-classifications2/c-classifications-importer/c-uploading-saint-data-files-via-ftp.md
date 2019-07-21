---
description: Etapas que descrevem como fazer upload de arquivos de dados por FTP.
seo-description: Etapas que descrevem como fazer upload de arquivos de dados por FTP.
seo-title: Importação de FTP
solution: Analytics
subtopic: Classificações
title: Importação de FTP
topic: Ferramentas administrativas
uuid: a 914970 d-ba 02-4111-9 dcf -06448 f 71 b 9 f 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importação de FTP

Etapas que descrevem como fazer upload de arquivos de dados por FTP.

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

Etapas que descrevem como fazer upload de arquivos de dados por FTP.

**[!UICONTROL Administração]** &gt; **[!UICONTROL Importador de classificação]**.

Os seguintes limites recomendados são importantes:

* Um número elevado de arquivos pequenos resultará em um processamento mais lento do que o processamento de poucos arquivos grandes. Isso se deve à quantidade de filas e prioridades necessárias para tarefas menores.
* Divida arquivos grandes em blocos de 50 MB. Isso não é obrigatório, mas é recomendável justamente por oferecer maior visibilidade no progresso de back-end. Além disso, se houver erros durante o processamento da tarefa, ela será reiniciada; nesse cenário, os arquivos grandes resultarão em grandes quantidades de trabalho refeito.

A configuração inicial preenche a base de dados de classificações com um grande conjunto de dados originais ou reestrutura as classificações, em vez de reclassificar algumas linhas ou adicionar linhas.

Após um upload inicial em um conjunto de relatórios (para determinada variável ou relatório), a Adobe recomenda fazer upload apenas de linhas novas e atualizadas em importações subsequentes. As linhas que não estão sendo alteradas devem ser omitidas nos uploads futuros.

Cada novo valor de chave que você carrega é descontado do total de únicos que você tem disponível para aquela variável no mês.

Se você excedeu seus únicos do mês, você não verá os dados de classificações correspondentes para os únicos que excederam os valores no relatório. É possível visualizar essas classificações tanto no data warehouse como na Ad Hoc Analysis.

>[!NOTE]
>
>O tempo necessário para processar um arquivo de dados de classificação varia de acordo com o tamanho do arquivo e o número atual de arquivos processados pelos servidores da Adobe. O processamento dos arquivos de dados geralmente não levam mais de 72 horas.

Antes de fazer upload dos dados por FTP, crie uma conta FTP. For more information, see [Create an FTP account](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importar classificações por FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Etapas que descrevem como usar uma conta FTP para importar classificações para o Adobe Analytics.

Para obter mais informações sobre como criar uma conta FTP, consulte [Criar uma conta FTP](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. Use as informações de acesso do FTP (Host, Logon, Senha) para acessar o servidor FTP usando um cliente FTP de sua escolha.
1. Upload the data file ( [!DNL .tab] or [!DNL .txt]) to the FTP server.
1. Após fazer upload do arquivo de dados, carregue um arquivo FIN que indica que o arquivo está pronto para o processamento.

   The FIN file is an empty file that has the same name as your data file, with a [!DNL .fin] filename extension. For example, if your data file is [!DNL classdata1.tab], the FIN filename is [!DNL classdata1.fin].

Em intervalos regulares, a Adobe recupera os arquivos de dados carregados que têm um arquivo FIN associado. A Adobe os importa para dentro dos conjuntos de relatórios e conjuntos de dados especificados na configuração da conta FTP.

## Criar uma conta FTP {#task_C019268E6C934C7C95F4326F42A22CCF}

Antes de fazer upload dos dados por FTP, crie uma conta FTP. &gt;

<!-- 

t_create_an_ftp_account.xml

 -->

Veja [FTP e sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/) para detalhes adicionais sobre os servidores Adobe FTP.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Na guia **Importar Arquivo**, clique em **[!UICONTROL Adicionar Novo]**.
1. Especifique os detalhes da conta FTP:

   | Elemento | Descrição |
   |---|---|
   | Nome | O nome da conta FTP |
   | Conjunto de dados a ser classificado | Na lista suspensa, selecione o conjunto de dados (variável do relatório de marketing) que você deseja classificar. |
   | Selecionar os conjuntos de relatórios | Selecione os conjuntos de relatórios nos quais deseja classificar o conjunto de dados selecionado. Para selecionar vários conjuntos de relatórios, as classificações de cada conjunto de relatórios selecionado devem ser idênticas. |
   | Substituir dados em conflito | Selecione essa opção para substituir os dados duplicados. Esta opção é útil se você deseja atualizar classificações existentes. Se você estiver acrescentando classificações adicionais, esta opção não é recomendada. |
   | Após a importação ser concluída | Selecione essa opção para exportar automaticamente o conjunto de dados atualizado para a mesma conta FTP depois de Especificar o endereço de email para receber notificações sobre essa conta FTP após a conclusão da importação. |
   | Destinatário da notificação | Especifique o endereço de email para receber notificações sobre essa conta FTP. |
   | Autorizar | (Obrigatório) Autoriza a Adobe a importar automaticamente todos os arquivos de dados enviados para a nova conta FTP. |

1. Clique em **[!UICONTROL Salvar]**.

Após sua criação, é possível editar ou excluir as contas FTP clicando no link apropriado ao lado da conta FTP desejada.
