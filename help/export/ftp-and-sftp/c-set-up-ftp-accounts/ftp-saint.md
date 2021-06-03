---
description: A opção de FTP de classificações (SAINT) oferece mais flexibilidade para fazer upload de configurações de dados de classificação grandes, incluindo a capacidade de fazer upload de dados para vários conjuntos de relatórios e fazer upload de configurações de dados com mais de 50.000 linhas.
keywords: ftp;sftp
title: Classificações
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 98%

---

# Classificações

A opção de FTP de classificações oferece mais flexibilidade para fazer upload de configurações de dados de classificação grandes, incluindo a capacidade de fazer upload de dados para vários conjuntos de relatórios e fazer upload de configurações de dados com mais de 50.000 linhas.

Consulte as [classificações](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) para ver como baixar dados de classificação via FTP e como fazer upload de arquivos de dados via FTP (incluindo as etapas para criar uma conta FTP).

O tempo necessário para que o sistema importe esses arquivos varia de acordo com diversos fatores. Se um arquivo carregado estiver presente no servidor FTP por mais de três dias, peça aos usuários com suporte de sua organização que entrem em contato com o Atendimento ao cliente da Adobe.

Se a importação for realizada com sucesso, as alterações apropriadas são exibidas imediatamente em uma exportação. Por outro lado, as alterações de dados no Analytics podem levar quatro horas com uma importação de navegador e até 24 horas com uma importação de FTP.

Para mais informações sobre os limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Sobre o arquivo `.fin` para Classificações e uploads de fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

Ao fazer upload de uma Classificação ou Fonte de dados (`.tab` ou `.txt`), o upload também exige que você carregue um arquivo vazio com exatamente o mesmo nome do arquivo de dados que está sendo importado, mas com a extensão .`.fin`. Este arquivo `.fin` é um arquivo de finalização. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. O arquivo `.fin` permite que a Adobe reconheça que a importação foi finalizada.

Depois de enviar o arquivo de origem e o arquivo `.fin`, é importante fazer logoff do site FTP. O motivo é que o Adobe Analytics usa eventos de logout como um acionador para que os arquivos estejam prontos para processamento. Após concluir a importação, a Adobe remove ambos os arquivos do local FTP.

Arquivo de finalização: [!DNL Classifications.fin]

Se você fizer upload de fontes de dados ou do arquivo de classificação sem um arquivo de acompanhamento `.fin`, a Adobe não os colocará na fila para processamento. O arquivo permanece no FTP e não é aplicado aos seus dados na [!UICONTROL Experience Cloud]. Você será notificado sobre isso caso tenha inserido seu endereço de email como o [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP] do Analytics. Se nenhum endereço de e-mail for inserido neste campo, nenhuma notificação será enviada.

Caso tenha realizado o upload do seu arquivo com um arquivo `.fin`, mas ele tenha alertado sobre um erro, ele será enviado para o processamento; contudo, esse erro fará com que o processo seja interrompido e o arquivo será enviado para uma pasta de erros. Se isto acontecer, uma notificação será enviada para o endereço de e-mail listado no campo [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP]. Se nenhum endereço de email for inserido, as notificações não serão enviadas.
