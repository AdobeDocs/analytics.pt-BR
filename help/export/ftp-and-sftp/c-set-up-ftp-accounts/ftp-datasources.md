---
description: É possível usar o Analytics para criar e gerenciar fontes de dados baseadas em FTP, o que impulsiona a transferência de arquivos por FTP para a importação de dados offline e de histórico na Experience Cloud.
keywords: ftp;sftp
title: Fontes de dados
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fontes de dados

É possível usar o Analytics para criar e gerenciar fontes de dados baseadas em FTP, o que impulsiona a transferência de arquivos por FTP para a importação de dados offline e de histórico na Experience Cloud.

Depois de criar a instância fontes de dados, a ferramenta fornece um local de FTP que você pode utilizar para enviar arquivos de fontes de dados. Após serem carregados, as Fontes de Dados automaticamente os localiza e processa. Depois que os arquivos são processados, os dados ficam disponíveis para relatórios no Analytics.

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. Suas informações de logon FTP são exibidas na [!UICONTROL Activate a Data Source] janela da [!UICONTROL Upload/FTP Information] seção.

Para mais informações sobre os limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Informações sobre o arquivo .fin para uploads de classificações e fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. Este arquivo [!DNL .fin] é um arquivo de finalização. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. O arquivo [!DNL .fin] permite que a Adobe reconheça que a importação foi finalizada. Após enviá-lo, a Adobe remove ambos os arquivos do FTP e começa a processar a importação.
Importar arquivo: [!DNL Classifications.tab]

Arquivo de finalização: [!DNL Classifications.fin]

Se você fizer upload de suas fontes de dados ou do arquivo SAINT sem um arquivo de acompanhamento [!DNL .fin], a Adobe não colocará o arquivo ou as fontes de dados na fila para processamento. O arquivo permanece no FTP e não é aplicado aos seus dados na [!UICONTROL Experience Cloud]. You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. Se nenhum endereço de e-mail for inserido neste campo, nenhuma notificação será enviada.

Caso tenha realizado o upload do seu arquivo com um arquivo [!DNL .fin], mas ele tenha alertado sobre um erro, ele será enviado para o processamento; contudo, esse erro fará com que o processo seja interrompido e o arquivo será enviado para uma pasta de erros. If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. Se nenhum endereço de email for inserido, as notificações não serão enviadas.
