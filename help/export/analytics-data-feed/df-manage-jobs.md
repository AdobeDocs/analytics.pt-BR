---
title: Gerenciar tarefas do feed de dados
description: Saiba como gerenciar trabalhos individuais em feeds de dados. Navegue pela interface, use filtros e pesquisa e localize definições de coluna.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: 728e807764901ad2bd6834339e5e75348dd5a988
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 30%

---

# Gerenciar processos de feed de dados

Os processos são tarefas individuais que geram um arquivo compactado. Eles são criados e governados por feeds.

Para gerenciar trabalhos do feed de dados:

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.

1. Selecione o ícone de 9 quadrados no canto superior direito e escolha [!UICONTROL **Analytics**].

1. Na barra de navegação superior, acesse [!UICONTROL **Admin**] > [!UICONTROL **Feeds de dados**].

   Os feeds de dados de todos os conjuntos de relatórios aos quais você tem acesso são exibidos. Ou, se nenhum feed for configurado, a página exibirá um botão [!UICONTROL Criar novo feed de dados].

   ![Gerenciador de feed de dados](assets/data-feed-manager.png)

1. (Opcional) Marque a caixa de seleção ao lado do feed de dados que contém os trabalhos que deseja exibir e selecione [!UICONTROL **Histórico de trabalhos**].

   Para obter mais informações, consulte [Exibir histórico de trabalho de um feed de dados](#view-job-history-for-a-data-feed).

## Filtrar e pesquisar

Você pode filtrar e pesquisar para localizar o trabalho exato que está procurando.

Na extremidade esquerda, clique no ícone de filtro para mostrar ou ocultar as opções de filtragem. Os filtros são organizados por categoria. Clique na divisa para recolher ou expandir as categorias de filtragem. Clique na caixa de seleção para aplicar um filtro.

![Filtro](assets/jobs-filter.png)

Use a pesquisa para localizar um trabalho por nome.

![Pesquisar](assets/search.png)

## Classificar e personalizar colunas

Cada tarefa mostra várias colunas com informações sobre ela. Você pode classificar as informações em cada coluna e personalizar as colunas exibidas.

### Classificar colunas

Selecione um cabeçalho de coluna para classificá-lo em ordem crescente. Selecione um cabeçalho de coluna novamente para classificá-lo em ordem decrescente.

### Personalizar colunas

Para ajustar as colunas visíveis na tabela:

1. Selecione o ícone de coluna ![Ícone de coluna](assets/customize-columns-icon.png) no canto superior direito.

1. Na caixa de diálogo Personalizar tabela, selecione cada coluna que deseja exibir e desmarque cada coluna que deseja ocultar.

   As seguintes colunas estão disponíveis:

* **Nome do feed**: coluna obrigatória. Exibe o nome do feed. Os trabalhos criados pelo mesmo feed têm o mesmo nome de feed.
* **ID do feed**: exibe a ID do feed, um identificador exclusivo. Os processos criados pelo mesmo feed têm a mesma ID do feed.
* **Conjunto de relatórios**: o conjunto de relatórios do qual o trabalho faz referência aos dados.
* **ID do conjunto de relatórios**: o identificador exclusivo do conjunto de relatórios.
* **Intervalo**: o intervalo do feed.
* **Tipo de destino**: o tipo de destino do feed.
* **Destino**: o destino do feed.
* **Proprietário**: o proprietário do feed.
* **Status**: o status do feed.
   * Aguardando dados: o processo é operacional e os dados da janela de relatório estão sendo coletados.
   * Processamento: o processo está criando os arquivos de dados e se preparando para enviá-los.
   * Concluído: o processo foi concluído sem problemas.
   * Falha: o processo não foi concluído. Consulte [Solução de problemas com feeds de dados](troubleshooting.md) para ajudar a determinar a causa da falha.
   * Aguardando exportação: os dados da janela de relatórios ainda não foram totalmente processados.
   * Sem dados: não há dados no conjunto de relatórios na janela de relatórios solicitada.
* **Última modificação**: a hora em que o feed foi modificado pela última vez.
* **Data de início**: a hora em que o trabalho começou. A data e a hora são mostradas no fuso horário do conjunto de relatórios com deslocamento GMT. Os feeds diários normalmente começam perto da meia-noite no fuso horário do conjunto de relatórios.
* **Data de término**: a hora em que o trabalho terminou. A data e a hora são mostradas no fuso horário do conjunto de relatórios com deslocamento GMT.

## Exibir o histórico de tarefas de um feed de dados

Você pode visualizar uma lista de trabalhos de feed de dados anteriores para um determinado feed de dados, juntamente com informações sobre cada trabalho.

Para exibir o histórico de tarefas de um feed de dados:

1. No Adobe Analytics, selecione [!UICONTROL **Administrador**] > [!UICONTROL **Feeds de dados**].

   ![Gerenciador de feed de dados](assets/data-feed-manager.png)

1. Marque a caixa de seleção ao lado do feed de dados cujo histórico de trabalho você deseja exibir e selecione [!UICONTROL **Histórico de trabalho**].

   O histórico de tarefas do feed de dados é exibido com as seguintes informações disponíveis sobre cada trabalho (selecione o ícone de coluna para adicionar colunas que não estão visíveis por padrão):

   * **[!UICONTROL Início do período de solicitação]**

   * **[!UICONTROL Fim do período de solicitação]**

   * **[!UICONTROL Programado]**

   * **[!UICONTROL Iniciado]**

   * **[!UICONTROL Concluído]**

   * **[!UICONTROL Executar nº]**

   * **[!UICONTROL Status]**

   * **[!UICONTROL Código de erro]**

   * **[!UICONTROL Mensagem de erro]**

## Reenviar trabalhos de feed de dados

Você pode reenviar uma tarefa de feed de dados se quiser enviar o arquivo de feed de dados novamente com exatamente os mesmos dados e processamento de quando ele foi enviado originalmente. Como alternativa, você pode [reprocessar um trabalho de feed de dados](#reprocess-data-feed-jobs).

Para reenviar um ou mais trabalhos do feed de dados:

1. No Adobe Analytics, selecione [!UICONTROL **Administrador**] > [!UICONTROL **Feeds de dados**].

1. Marque a caixa de seleção ao lado do feed de dados que contém os trabalhos que você deseja reenviar e selecione [!UICONTROL **Histórico de trabalhos**].

1. Marque a caixa de seleção ao lado de um ou mais trabalhos de feed de dados e selecione **[!UICONTROL Reenviar]**. <!-- What does the status need to be? Error, ... -->

   ![Reprocessar trabalho do feed de dados](assets/data-feed-job-resend.png)

## Reprocessar trabalhos do feed de dados

Você pode reprocessar os dados de origem de uma tarefa do feed de dados e enviá-los novamente com os dados reprocessados. Como alternativa, você pode [reenviar um trabalho de feed de dados](#resend-data-feed-jobs).

Para reprocessar um ou mais trabalhos do feed de dados:

1. No Adobe Analytics, selecione [!UICONTROL **Administrador**] > [!UICONTROL **Feeds de dados**].

1. Marque a caixa de seleção ao lado do feed de dados que contém os trabalhos que você deseja reprocessar e selecione [!UICONTROL **Histórico de trabalhos**].

1. Marque a caixa de seleção ao lado de um ou mais trabalhos de feed de dados e selecione **[!UICONTROL Reprocessar]**. <!-- What does the status need to be? Error, ... -->

   ![Reprocessar trabalho do feed de dados](assets/data-feed-job-reprocess.png)
