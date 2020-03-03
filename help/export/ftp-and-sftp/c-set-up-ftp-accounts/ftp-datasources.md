---
description: É possível usar o Analytics para criar e gerenciar fontes de dados baseadas em FTP, o que impulsiona a transferência de arquivos por FTP para a importação de dados offline e de histórico na Experience Cloud.
keywords: ftp;sftp
title: Fontes de dados
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fontes de dados

É possível usar o Analytics para criar e gerenciar fontes de dados baseadas em FTP, o que impulsiona a transferência de arquivos por FTP para a importação de dados offline e de histórico na Experience Cloud.

Depois de criar a instância fontes de dados, a ferramenta fornece um local de FTP que você pode utilizar para enviar arquivos de fontes de dados. Após serem carregados, a fontes de dados automaticamente os localiza e processa. Depois que os arquivos são processados, os dados ficam disponíveis para relatórios no Analytics.

A guia [!UICONTROL Criar] no Gerente de fontes de dados permite que você configure uma nova instância de fontes de dados para o conjunto de relatórios selecionado. O [!UICONTROL Assistente das fontes de dados] orienta você ao longo do processo de criação de um modelo de fontes de dados, além de criar um local FTP para carregar os dados.

Na janela [!UICONTROL Gerenciar fontes de dados], encontre sua fonte de dados e selecione o link Informações do FTP. Suas informações de logon FTP são exibidas na janela [!UICONTROL Ativar uma fonte de dados] na seção [!UICONTROL Fazer upload/Informações do FTP].

Para mais informações sobre os limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Informações sobre o arquivo .fin para uploads de classificações e fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

Ao fazer upload de um arquivo de classificação ou [!UICONTROL Fonte de dados] ( [!DNL .tab] ou [!DNL .txt]) o upload também exige que você faça um upload de um arquivo vazio com o mesmo nome do arquivo de dados a ser importado, mas com extensão [!DNL .fin]. Este arquivo [!DNL .fin] é um arquivo de finalização. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. O arquivo [!DNL .fin] permite que a Adobe reconheça que a importação foi finalizada. Após enviá-lo, a Adobe remove ambos os arquivos do FTP e começa a processar a importação.
Importar arquivo: [!DNL Classifications.tab]

Arquivo de finalização: [!DNL Classifications.fin]

Se você fizer upload de suas fontes de dados ou do arquivo SAINT sem um arquivo de acompanhamento [!DNL .fin], a Adobe não colocará o arquivo ou as fontes de dados na fila para processamento. O arquivo permanece no FTP e não é aplicado aos seus dados na [!UICONTROL Experience Cloud]. Você será notificado sobre isso caso tenha inserido seu endereço de email como o [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP] do relatório. Se nenhum endereço de e-mail for inserido neste campo, nenhuma notificação será enviada.

Caso tenha realizado o upload do seu arquivo com um arquivo [!DNL .fin], mas ele tenha alertado sobre um erro, ele será enviado para o processamento; contudo, esse erro fará com que o processo seja interrompido e o arquivo será enviado para uma pasta de erros. Se isto acontecer, uma notificação será enviada para o endereço de e-mail listado no campo [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP]. Se nenhum endereço de email for inserido, as notificações não serão enviadas.
