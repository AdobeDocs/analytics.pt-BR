---
description: Como fazer upload de arquivos de dados via FTP.
title: Importação de FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 72%

---

# Importação de FTP (herdada)

>[!IMPORTANT]
>
>A Adobe não recomenda mais usar o FTP para importação conforme descrito nesta página.
>
>O FTP não é recomendado porque é um método não criptografado de compartilhamento de arquivos, o que significa que qualquer pessoa pode interceptar o conteúdo do arquivo, bem como o nome de usuário e a senha usados para a conta.
>
>Em vez disso, configure uma conta de nuvem conforme descrito em [Configurar contas de importação e exportação da nuvem](/help/components/locations/configure-import-accounts.md).

Etapas que descrevem como fazer upload de arquivos de dados por FTP.

## Importação de FTP {#concept_2F965BE873254546A61FB755F25299FD}

Como fazer upload de arquivos de dados via FTP:

1. **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.

Os seguintes limites recomendados são importantes.

>[!IMPORTANT]
>
>Ter muitos arquivos pequenos ou arquivos grandes únicos pode criar carga de processamento desnecessária nos servidores de processamento. A Adobe recomenda dividir arquivos grandes em blocos de 50 MB e combinar arquivos pequenos.

A configuração inicial preenche a base de dados de classificações com um grande conjunto de dados originais ou reestrutura as classificações, em vez de reclassificar algumas linhas ou adicionar linhas.

Após um upload inicial em um conjunto de relatórios (para determinada variável ou relatório), a Adobe recomenda fazer upload apenas de linhas novas e atualizadas em importações subsequentes. As linhas que não estão sendo alteradas devem ser omitidas nos uploads futuros.

Cada novo valor de chave que você carrega é descontado do total de únicos que você tem disponível para aquela variável no mês.

Se você excedeu seus únicos do mês, você não verá os dados de classificações correspondentes para os únicos que excederam os valores no relatório. É possível ver essas classificações no Data Warehouse.

>[!NOTE]
>
>O tempo necessário para processar um arquivo de dados de classificação varia de acordo com o tamanho do arquivo e o número atual de arquivos processados pelos servidores da Adobe. O processamento dos arquivos de dados geralmente não levam mais de 72 horas.

## Criar uma conta FTP

Antes de fazer upload dos dados por FTP, crie uma conta FTP. >

Veja [FTP e sFTP](/help/export/ftp-and-sftp/ftp-overview.md) para detalhes adicionais sobre os servidores Adobe FTP.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.
1. Clique em **[!UICONTROL Importar Arquivo]**, e então clique em **[!UICONTROL Importação de FTP]**.
1. Na guia **[!UICONTROL Importar Arquivo]**, clique em **[!UICONTROL Adicionar Novo]**.
1. Especifique os detalhes da conta FTP:

   | Elemento | Descrição |
   |---|---|
   | **Nome** | O nome da conta FTP. |
   | **Conjunto de dados a ser classificado** | Na lista suspensa, selecione o conjunto de dados (variável do relatório de marketing) que você deseja classificar. |
   | **Selecionar Conjuntos de Relatórios** | Selecione os conjuntos de relatórios nos quais deseja classificar o conjunto de dados selecionado. Para selecionar vários conjuntos de relatórios, as classificações de cada conjunto de relatórios selecionado devem ser idênticas. |
   | **Substituir Dados em Conflitos** | Selecione essa opção para substituir os dados duplicados. Esta opção é útil se você deseja atualizar classificações existentes. Se você estiver na [última arquitetura de classificação](../sets/overview.md), essa configuração sempre estará habilitada. |
   | **Após a Conclusão da Importação** | Selecione essa opção para exportar automaticamente o conjunto de dados atualizado para a mesma conta FTP depois de especificar o endereço de email para receber notificações sobre essa conta FTP depois que a importação for concluída. Se você estiver na [última arquitetura de classificação](../sets/overview.md), essa opção não estará disponível. |
   | **Destinatário da Notificação** | Especifique o endereço de email para receber notificações sobre essa conta FTP. |
   | **Autorizar** | (Obrigatório) Autoriza a Adobe a importar automaticamente todos os arquivos de dados enviados para a nova conta FTP. |

1. Clique em **[!UICONTROL Salvar]**.

Após sua criação, é possível editar ou excluir as contas FTP clicando no link apropriado ao lado da conta FTP desejada.

>[!NOTE]
>
>As notificações não serão enviadas se uma importação não introduzir alterações em uma classificação. Um email só será enviado se for bem-sucedido e resultar em alterações em uma classificação.

## Importar classificações por FTP

Você pode usar uma conta FTP para importar classificações para o Adobe Analytics.

Para importar classificações via FTP:

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Importador de classificação]**.
1. Clique em **[!UICONTROL Importar Arquivo]**, e então clique em **[!UICONTROL Importação de FTP]**.
1. Ao lado da conta FTP que deseja usar, clique em **[!UICONTROL Exibir]**.
1. Use as informações de acesso do FTP (Host, Logon, Senha) para acessar o servidor FTP usando um cliente FTP de sua escolha.
1. Carregue o arquivo de dados (`.tab` ou `.txt`) no servidor FTP.
1. Após fazer upload do arquivo de dados, carregue um arquivo FIN que indica que o arquivo está pronto para o processamento.

   O arquivo é um arquivo vazio que tem o mesmo nome de seu arquivo de dados, com uma extensão de nome de arquivo `.fin`. Por exemplo, se seu arquivo de dados é `classdata1.tab`, o nome do arquivo é `classdata1.fin` .fin.

Em intervalos regulares, a Adobe recupera os arquivos de dados carregados que têm um arquivo FIN associado. A Adobe os importa para dentro dos conjuntos de relatórios e conjuntos de dados especificados na configuração da conta FTP.

Depois que o Adobe Analytics ler e processar os arquivos carregados na pasta FTP, os arquivos serão automaticamente removidos do site FTP.
