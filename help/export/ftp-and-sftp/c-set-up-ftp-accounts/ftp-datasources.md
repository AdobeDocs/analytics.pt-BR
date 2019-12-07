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

Depois de criar a instância fontes de dados, a ferramenta fornece um local de FTP que você pode utilizar para enviar arquivos de fontes de dados. Após serem carregados, a fontes de dados automaticamente os localiza e processa. Depois que os arquivos são processados, os dados ficam disponíveis para relatórios no Analytics.

A guia [!UICONTROL Criar] no Gerente de fontes de dados permite que você configure uma nova instância de fontes de dados para o conjunto de relatórios selecionado. O [!UICONTROL Assistente das fontes de dados] orienta você ao longo do processo de criação de um modelo de fontes de dados, além de criar um local FTP para carregar os dados.

Na janela [!UICONTROL Gerenciar fontes de dados], encontre sua fonte de dados e selecione o link Informações do FTP. Suas informações de logon FTP são exibidas na janela [!UICONTROL Ativar uma fonte de dados] na seção [!UICONTROL Fazer upload/Informações do FTP].

Para mais informações sobre os limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Informações sobre o arquivo .fin para uploads de classificações e fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Após enviá-lo, a Adobe remove ambos os arquivos do FTP e começa a processar a importação.
Importar arquivo: [!DNL Classifications.tab]

Arquivo de finalização: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Você será notificado sobre isso caso tenha inserido seu endereço de email como o [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP] do relatório. Se nenhum endereço de email for inserido neste campo, nenhuma notificação será enviada.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Se isto acontecer, uma notificação será enviada para o endereço de email listado no campo [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP]. Se nenhum endereço de email for inserido, as notificações não serão enviadas.
