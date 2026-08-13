---
description: Como fazer upload de arquivos de dados via FTP.
title: Importação de FTP
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
TQID: https://experienceleague.adobe.com/CMHQpWtGl14Z7kHaZ7ufp6-tDIfQ-pCEzSI47XMi-pA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 727
ht-degree: 40%

---

# Importação de FTP (herdada)

{{classification-importer-deprecation}}

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

A configuração inicial preenche o banco de dados de classificações com um grande conjunto de dados originais ou reestrutura as classificações, em vez de reclassificar algumas linhas ou adicionar linhas.

Após um upload inicial em um conjunto de relatórios (para uma determinada variável ou relatório), a Adobe recomenda fazer upload somente de linhas novas e atualizadas em importações subsequentes. As linhas que não estão sendo alteradas devem ser omitidas dos uploads futuros.

Cada novo valor de chave carregado conta em relação aos únicos para essa variável do mês.

Se você tiver excedido seus únicos no mês, não verá os dados de classificação correspondentes para os valores excedidos de únicos no relatório. É possível ver essas classificações no Data Warehouse.

>[!NOTE]
>
>O tempo necessário para processar um arquivo de dados de classificação varia de acordo com o tamanho do arquivo e o número atual de arquivos processados pelos servidores da Adobe. O processamento de arquivos de dados geralmente não leva mais de 72 horas.

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
   | **Conjunto de dados a ser classificado** | Na lista suspensa, selecione o conjunto de dados (variável de relatório de marketing) que deseja classificar. |
   | **Selecionar Conjuntos de Relatórios** | Selecione os conjuntos de relatórios nos quais você deseja classificar o conjunto de dados selecionado. Para selecionar vários conjuntos de relatórios, as classificações de cada um dos conjuntos de relatórios selecionados devem ser idênticas. |
   | **Substituir Dados em Conflitos** | Selecione esta opção para substituir dados duplicados. Essa opção é útil se você estiver atualizando classificações existentes. Se você estiver na [última arquitetura de classificação](../sets/overview.md), essa configuração sempre estará habilitada. |
   | **Após a Conclusão da Importação** | Selecione essa opção para exportar automaticamente o conjunto de dados atualizado para a mesma conta FTP depois de especificar o endereço de email para receber notificações sobre essa conta FTP depois que a importação for concluída. Se você estiver na [última arquitetura de classificação](../sets/overview.md), essa opção não estará disponível. |
   | **Destinatário da Notificação** | Especifique o endereço de email para receber notificações sobre esta conta FTP. |
   | **Autorizar** | (Obrigatório) Autoriza o Adobe a importar automaticamente todos os arquivos de dados enviados para a nova conta FTP. |

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

Em intervalos regulares, o Adobe recupera arquivos de dados carregados que tenham um arquivo FIN associado. O Adobe os importa para os conjuntos de relatórios e conjuntos de dados especificados na configuração da conta FTP.

Depois que o Adobe Analytics ler e processar os arquivos carregados na pasta FTP, os arquivos serão automaticamente removidos do site FTP.
