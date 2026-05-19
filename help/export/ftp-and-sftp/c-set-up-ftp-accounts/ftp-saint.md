---
description: A opção de FTP de classificações (SAINT) oferece mais flexibilidade para fazer upload de configurações de dados de classificação grandes, incluindo a capacidade de fazer upload de dados para vários conjuntos de relatórios e fazer upload de configurações de dados com mais de 50.000 linhas.
keywords: ftp;sftp
title: Classificações
feature: FTP Export
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
TQID: https://experienceleague.adobe.com/JdxiVF-HzQPiFzC6CH0yeIIPEulsacjl11-X8wLMrl4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 75%

---

# Classificações

A opção de FTP de classificações oferece mais flexibilidade para fazer upload de configurações de dados de classificação grandes, incluindo a capacidade de fazer upload de dados para vários conjuntos de relatórios e fazer upload de configurações de dados com mais de 50.000 linhas.

O tempo necessário para o sistema importar esses arquivos varia de acordo com vários fatores. Se um arquivo carregado estiver presente no servidor FTP por mais de três dias, peça aos usuários com suporte de sua organização que entrem em contato com o Atendimento ao cliente da Adobe.

Se a importação for realizada com sucesso, as alterações apropriadas são exibidas imediatamente em uma exportação. Por outro lado, as alterações de dados no Analytics podem levar quatro horas com uma importação de navegador e até 24 horas com uma importação de FTP.

Para obter informações sobre limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Sobre o arquivo `.fin` para Classificações e uploads de fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

Ao carregar um arquivo de Classificação ou Source de Dados (`.tab` ou `.txt`), o carregamento também exige que você carregue um arquivo vazio com exatamente o mesmo nome do arquivo de dados a ser importado, mas com um .`.fin` extensão. Este arquivo `.fin` é um arquivo de finalização. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. O arquivo `.fin` permite que a Adobe reconheça que a importação foi finalizada.

Depois de enviar o arquivo de origem e o arquivo `.fin`, é importante fazer logoff do site FTP. O motivo é que o Adobe Analytics usa eventos de logout como um acionador para que os arquivos estejam prontos para processamento. Após concluir a importação, a Adobe remove ambos os arquivos do local FTP.

Arquivo de finalização: [!DNL Classifications.fin]

Se você fizer upload de fontes de dados ou do arquivo de classificação sem um arquivo de acompanhamento `.fin`, a Adobe não os colocará na fila para processamento. O arquivo permanece no FTP e não é aplicado aos seus dados no CX Enterprise. Você será notificado disso somente se tiver inserido seu endereço de email como [!UICONTROL Destinatário da Notificação] na janela [!UICONTROL Criar Conta FTP] do Analytics. Se nenhum endereço de e-mail for inserido neste campo, nenhuma notificação será enviada.

Caso tenha realizado o upload do seu arquivo com um arquivo `.fin`, mas ele tenha alertado sobre um erro, ele será enviado para o processamento; contudo, esse erro fará com que o processo seja interrompido e o arquivo será enviado para uma pasta de erros. Se isto acontecer, uma notificação será enviada para o endereço de e-mail listado no campo [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP]. Se nenhum endereço de email for inserido, as notificações não serão enviadas.
