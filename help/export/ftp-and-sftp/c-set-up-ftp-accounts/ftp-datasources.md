---
description: Você pode usar o Analytics para criar e gerenciar fontes de dados baseadas em FTP, o que impulsiona a transferência de arquivos do FTP para importar dados off-line e de histórico na CX Enterprise.
keywords: ftp;sftp
title: Visão geral das Fontes de dados
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: https://experienceleague.adobe.com/Mq4r5p1872tIxfjts7HOq50XWky12Oy4fTi9ajzbAsc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 453
ht-degree: 40%

---

# Fontes de dados baseadas em FTP

Você pode usar o Analytics para criar e gerenciar fontes de dados baseadas em FTP, o que impulsiona a transferência de arquivos do FTP para importar dados off-line e de histórico na CX Enterprise.

Depois de criar uma instância de Fontes de dados, a ferramenta fornece um local FTP que você pode usar para carregar arquivos de Fontes de dados. Após serem carregados, as Fontes de Dados automaticamente os localiza e processa. Depois que os arquivos são processados, os dados são disponibilizados para os relatórios do Analytics.

A guia [!UICONTROL Criar] no Gerenciador de fontes de dados permite configurar uma nova instância das Fontes de dados para o conjunto de relatórios selecionado. O Assistente das fontes de dados o orienta pelo processo de criação de um modelo de fontes de dados e cria um local FTP para o upload de dados.

Na janela [!UICONTROL Gerenciar Fontes de Dados], encontre a fonte de dados e selecione o link Informações de FTP. Suas informações de logon de FTP são exibidas na janela [!UICONTROL Ativar Source de Dados] na seção [!UICONTROL Informações de Upload/FTP].

Para obter informações sobre limites FTP e retenção de dados, consulte [Limites FTP e retenção de dados](/help/export/ftp-and-sftp/ftp-limits.md).

## Informações sobre o arquivo .fin para uploads de classificações e fontes de dados {#section_1484719F8A134EAE91212DBD8F15174F}

Ao carregar um arquivo de classificação ou fonte de dados ( `.tab` ou `.txt`) o carregamento também exige que você carregue um arquivo vazio com exatamente o mesmo nome do arquivo de dados a ser importado, mas com extensão `.fin`. Este arquivo `.fin` é um arquivo de finalização. Ele tem o objetivo de informar ao sistema que o arquivo de dados foi enviado com sucesso para a conta FTP. O arquivo `.fin` permite que a Adobe reconheça que a importação foi finalizada. Após enviá-lo, a Adobe remove ambos os arquivos do FTP e começa a processar a importação.

Importar arquivo: `Classifications.tab`

Arquivo de finalização: `Classifications.fin`

Se você fizer upload de suas fontes de dados ou do arquivo SAINT sem um arquivo de acompanhamento `.fin`, a Adobe não colocará o arquivo ou as fontes de dados na fila para processamento. O arquivo permanece no FTP e não é aplicado aos seus dados no CX Enterprise. Você será notificado disso somente se tiver inserido seu endereço de email como [!UICONTROL Destinatário de Notificações] na janela de relatórios [!UICONTROL Criar Conta FTP]. Se nenhum endereço de e-mail for inserido neste campo, nenhuma notificação será enviada.

Caso tenha realizado o upload do seu arquivo com um arquivo `.fin`, mas ele tenha alertado sobre um erro, ele será enviado para o processamento; contudo, esse erro fará com que o processo seja interrompido e o arquivo será enviado para uma pasta de erros. Se isto acontecer, uma notificação será enviada para o endereço de e-mail listado no campo [!UICONTROL destinatário de notificações] na janela [!UICONTROL Criar conta FTP]. Se nenhum endereço de email for inserido, nenhuma notificação será enviada.
