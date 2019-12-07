---
description: A opção de FTP de classificações (SAINT) oferece mais flexibilidade para fazer upload de configurações de dados de classificação grandes, incluindo a capacidade de fazer upload de dados para vários conjuntos de relatórios e fazer upload de configurações de dados com mais de 50.000 linhas.
keywords: ftp;sftp
title: Classificações
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classificações

A opção FTP de classificações oferece mais flexibilidade ao fazer upload de grandes conjuntos de dados de classificação, incluindo a capacidade de fazer upload de dados em vários conjuntos de relatórios e fazer upload de conjuntos de dados com mais de 50.000 linhas.

Consulte as [classificações](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) para ver como baixar dados de classificação via FTP e como fazer upload de arquivos de dados via FTP (incluindo as etapas para criar uma conta FTP).

O tempo necessário para que o sistema importe esses arquivos varia de acordo com diversos fatores. Se um arquivo enviado ainda está presente no servidor FTP após seis horas, recomende aos usuários da organização que entrem em contato com o Atendimento ao cliente da Adobe.

Se a importação for realizada com sucesso, as alterações apropriadas são exibidas imediatamente em uma exportação. Por outro lado, as alterações de dados no Analytics podem levar quatro horas com uma importação de navegador e até 24 horas com uma importação de FTP.

Para mais informações sobre os limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Informações sobre o arquivo .fin para uploads de classificações e fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. The [!DNL .fin] file lets Adobe recognize that you are done with your import. Após enviá-lo, a Adobe remove ambos os arquivos do FTP e começa a processar a importação.
Importar arquivo: [!DNL Classifications.tab]

Arquivo de finalização: [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Você será notificado sobre isso caso tenha inserido seu endereço de email como o [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP] do Analytics. Se nenhum endereço de email for inserido neste campo, nenhuma notificação será enviada.

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. Se isto acontecer, uma notificação será enviada para o endereço de email listado no campo [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP]. Se nenhum endereço de email for inserido, as notificações não serão enviadas.
