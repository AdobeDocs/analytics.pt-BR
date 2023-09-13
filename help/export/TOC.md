---
product: analytics
audience: end-user
user-guide-title: Guia de exportação do Analytics
breadcrumb-title: Guia de exportação
user-guide-description: Saiba mais sobre como usar os feeds de dados para exportar dados brutos e o Data Warehouse para recuperar uma saída de dados em planilha. Saiba como usar o FTP e SFTP para transferir arquivos.
source-git-commit: a38ee68a1560200e55067ef0ea007f69ce8b575e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 100%

---


# Guia de exportação do Adobe Analytics {#export}

+ [Guia de exportação do Analytics](home.md)
+ [Notas de versão do Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
+ Feed de dados do Analytics {#analytics-data-feed}
   + [Visão geral do feed de dados](analytics-data-feed/data-feed-overview.md)
   + [Criar ou editar um feed de dados](analytics-data-feed/create-feed.md)
   + [Gerenciar feeds de dados](analytics-data-feed/df-manage-feeds.md)
   + [Gerenciar trabalhos do feed de dados](analytics-data-feed/df-manage-jobs.md)
   + Conteúdos do feed de dados {#data-feed-contents}
      + [Visão geral dos conteúdos do feed de dados](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [Calcular métricas](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [Referência da coluna de dados](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [Pesquisa de evento da página](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [Pesquisas dinâmicas](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [Pesquisa de eVar de merchandising](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [Caracteres especiais](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [Ocorrências com atraso de chegada](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [Perguntas frequentes sobre o feed de dados](analytics-data-feed/df-faq.md)
   + [Práticas recomendadas do feed de dados](analytics-data-feed/data-feeds-best-practices.md)
   + [Solução de problemas com feeds de dados](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Visão geral do Data Warehouse](data-warehouse/data-warehouse.md)
   + [Adicionar grupo de usuários do Data Warehouse](data-warehouse/t-dw-group.md)
   + Criar uma solicitação do Data Warehouse {#dw-create-request}
      + [Criar uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [Configurações gerais](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [Crie seu relatório](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [Destino do relatório](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [Opções de relatório](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [Opções de agendamento](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [Email de notificação](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [Solicitar tempo de delivery](data-warehouse/delivery-time.md)
   + [Arquivo de dados Tableau](data-warehouse/t-tableau.md)
   + [Classificar por métrica](data-warehouse/sorting-by-metric.md)
   + [Gerenciar solicitações do Data Warehouse](data-warehouse/data-warehouse-requests-manage.md)
   + [Componentes compatíveis com o Data Warehouse](data-warehouse/component-support.md)
   + [Perguntas frequentes sobre o Data Warehouse](data-warehouse/faq.md)
   + [Práticas recomendadas do Data Warehouse](data-warehouse/data-warehouse-bp.md)
+ FTP e SFTP {#ftp-and-sftp}
   + [Usar o FTP e SFTP com a Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + Configurar contas FTP hospedadas pela Adobe {#set-up-ftp-accounts}
      + [Configurar contas FTP - visão geral](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [Classificações](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [Fontes de dados](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Data Connectors](ftp-and-sftp/c-set-up-ftp-accounts/ftp-genesis.md)
      + [Feeds de dados](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Relatórios entregues do Data Warehouse](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Relatórios entregues do Report Builder](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [Envolvimentos de serviços de engenharia com FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [Limites FTP e retenção de dados](ftp-and-sftp/ftp-limits.md)
   + [Excluir dados e contas FTP](ftp-and-sftp/ftp-delete.md)
   + [Restaurar contas e dados FTP excluídos](ftp-and-sftp/ftp-restore.md)
   + [Atualizar servidores FTP da Adobe](ftp-and-sftp/ftp-upgrade.md)
   + [Usar o modo FTP passivo](ftp-and-sftp/ftp-passive.md)
   + [Tempos de processamento do FTP](ftp-and-sftp/ftp-processing.md)
   + Protocolo de transferência segura de arquivo {#secure-file-transfer-protocol}
      + [Atualização de serviços SFTP - Perguntas frequentes](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [Protocolo de transferência segura de arquivo - visão geral](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [Conexão com uma conta FTP da Adobe com SFTP](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [Enviar dados da Adobe para uma conta FTP externa com SFTP](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [Enviar solicitações de Data Warehouse para servidores SFTP](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [Conexão com a Adobe via SFTP sem uma senha](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Downloads do Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=pt-BR)
+ [API do Adobe Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=pt-BR)
