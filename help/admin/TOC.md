---
product: analytics
audience: admin
user-guide-title: Guia de administração do Analytics
breadcrumb-title: Guia de administração
user-guide-description: Saiba mais sobre as tarefas administrativas do Analytics, como gerenciar usuários e produtos no Admin Console da Experience Cloud, configurar conjuntos de relatórios e muito mais.
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 99%

---


# Guia do administrador do Adobe Analytics {#admin}

+ [Guia de administração do Analytics](home.md)
+ [Notas de versão do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/release-notes/latest)
+ Adobe Admin Console {#admin-console}
   + [Visão geral](admin-console/home.md)
   + [Guia do primeiro administrador do Adobe Analytics](admin-console/first-admin-guide.md)
   + [Funções de administrador no Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Resumo das permissões das ferramentas do Analytics {#permissions}
      + [Perfis de produto para o Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Permissões de perfil de produto para Ferramentas de conjuntos de relatórios](admin-console/permissions/report-suite-tools.md)
      + [Permissões de perfil de produto para as Ferramentas do Analytics](admin-console/permissions/analytics-tools.md)
+ Ferramentas administrativas do Analytics {#admin-tools}
   + [Visão geral das ferramentas administrativas](tools/c-admin-tools.md)
   + [Gerenciador de código](tools/code-manager-admin.md)
   + [Inventário do Analytics](tools/analytics-inventory.md)
   + [Fontes de dados](tools/data-sources.md)
   + [Excluir por endereço IP](tools/exclude-ip.md)
   + [Logs](tools/logs.md)
   + Gerenciador de atividades de relatórios {#reporting-activity-manager}
      + [Visão geral](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [Exibir atividade de relatório](tools//reporting-activity-manager/reporting-activity.md)
      + [Cancelar solicitações de geração de relatórios](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migração de componentes {#component-migration}
      + [Preparar para migração](tools/component-migration/prepare-component-migration.md)
      + [Fluxo de trabalho de migração](tools/component-migration/component-migration.md)
   + Gerenciador de conjuntos de relatórios {#manage-report-suites}
      + Editar configurações de um conjunto de relatórios {#edit-report-suite}
         + Geral {#report-suite-general}
            + [Configurações gerais da conta](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [Filtros internos do URL](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [Personalizar calendário](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + Detecção de pesquisa paga {#paid-search-detection}
               + [Visão geral da detecção de pesquisa paga](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [Configurar a detecção de pesquisa paga](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + Regras de processamento {#processing-rules}
               + [Visão geral](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [Interface](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [Visualizar histórico](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [Copiar regras](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [Dimensões e métricas disponíveis](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [Casos de uso](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + Regras de bot {#bot-removal}
               + [Remoção de bots](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [Noções básicas e configuração de regras de bots](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [Assinaturas comuns do bot](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [Métodos de exclusão de bot](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [Configurações de privacidade](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [Configuração de carimbos de data e hora](tools/manage-rs/edit-settings/general/timestamp-optional.md)
            + Encaminhamento pelo lado do servidor {#server-side-forwarding}
               + [Visão geral do encaminhamento pelo lado do servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [Conformidade com o RGPD/ePrivacy e o encaminhamento pelo lado do servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisitos do encaminhamento pelo lado do servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [Referência de dados e de código do encaminhamento pelo lado do servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [Como verificar a implementação do encaminhamento pelo lado do servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [Perguntas frequentes sobre o encaminhamento pelo lado do servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + Tráfego {#traffic-variables}
            + [Variáveis de tráfego](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [Classificações de tráfego](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [Descrições do relatório personalizado](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + Conversão {#conversion-variables}
            + [Variáveis de conversão](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [Métodos de descoberta](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [Classificações de conversão](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + Variável de visitante único {#unique-visitor-variable}
               + [Especificar a Variável de visitante único](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso de uso - Extração de IDs de visitantes](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Eventos bem-sucedidos](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [Hierarquias de classificação](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [Variáveis da lista](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [eVars de merchandising](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + Canais de marketing {#marketing-channels}
            + [Gerenciador de canal de marketing](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [Regras de processamento de canal de marketing](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [Classificações de canal de marketing](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [Expiração de canal de marketing](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + Gerenciamento de tráfego {#traffic-management}
            + [Visão geral](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [Programar pico](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [Tráfego permanente](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [Métricas padrão](tools/manage-rs/edit-settings/default-metrics.md)
         + Gerenciamento de aplicativos {#app-management}
            + [Relatório do aplicativo](tools/manage-rs/edit-settings/app-reporting.md)
            + [Classificações do aplicativo](tools/manage-rs/edit-settings/app-classifications.md)
         + [Gerenciamento de mídia](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [Relatórios de privacidade](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Gerenciamento da Document Cloud {#doc-cloud-mgt}
            + [Configurar a Document Cloud com o Adobe Analytics](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [Configurar relatórios da Document Cloud](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Configuração do Advertising Analytics](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + Tempo real {#real-time-reports}
            + [Visão geral dos Relatórios em tempo real](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [Configuração de relatórios em tempo real](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [Métricas e dimensões em tempo real compatíveis](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [Gerenciar conjuntos de relatórios](tools/manage-rs/report-suites-admin.md)
      + [Conjuntos de relatórios globais](tools/manage-rs/rollup-report-suite.md)
      + [Salvar uma pesquisa do conjunto de relatórios](tools/manage-rs/t-report-suite-saved-search.md)
      + [Fazer download das configurações do conjunto de relatórios](tools/manage-rs/t-download-rs-settings.md)
      + Novo conjunto de relatórios {#c-new-report-suite}
         + [Criar um conjunto de relatórios](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [Criar um grupo de conjunto de relatórios](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [Configurações do novo conjunto de relatórios](tools/manage-rs/new-rs/new-report-suite.md)
         + [Configurações não copiadas do conjunto de relatórios de origem](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + Modelos de conjunto de relatórios {#report-suite-templates}
         + [Visão geral dos modelos de conjunto de relatórios](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [Portal agregador](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [Comércio](tools/manage-rs/rs-templates/commerce-admin.md)
         + [Conteúdo e mídia](tools/manage-rs/rs-templates/content-media.md)
         + [Modelo padrão](tools/manage-rs/rs-templates/default-rs-template.md)
         + [Serviços financeiros](tools/manage-rs/rs-templates/financial-services.md)
         + [Portal de trabalho](tools/manage-rs/rs-templates/job-portal.md)
         + [Geração de leads](tools/manage-rs/rs-templates/lead-generation.md)
         + [Mídia de suporte](tools/manage-rs/rs-templates/support-media.md)
   + Configurações da empresa {#company-settings}
      + [Visão geral das configurações da empresa](tools/company/c-company-settings.md)
      + [Gerenciador de segurança](tools/company/security-manager.md)
      + [Serviços Web](tools/company/web-services-admin.md)
      + [Relatórios do Report Builder](tools/company/report-builder-reports-admin.md)
      + [Logon único](tools/company/single-signon-admin.md)
      + [Ocultar conjuntos de relatórios](tools/company/c-hide-report-suites.md)
      + [Gerenciador de preferências](tools/company/preferences-manager.md)
      + [Ações pendentes](tools/company/pending-actions-admin.md)
      + [Níveis de acesso a recursos](tools/company/feature-access-levels.md)
   + Rotulagem de privacidade {#privacy-labeling}
      + [Visão geral](tools/privacy-labeling/labeling-overview.md)
      + [Rótulos de privacidade de dados para componentes do Analytics](tools/privacy-labeling/labels.md)
      + [Exibir/gerenciar rótulos de privacidade do conjunto de relatórios](tools/privacy-labeling/view-settings.md)
      + [Práticas recomendadas de rotulagem](tools/privacy-labeling/best-practices.md)
      + [Exemplo de rotulagem](tools/privacy-labeling/examples.md)
      + [Namespaces](tools/privacy-labeling/namespaces.md)
   + Uso de chamadas do servidor {#server-call-usage}
      + [Visão geral do uso de chamadas do servidor](tools/server-call-usage/overage-overview.md)
      + [Visualizar uso de chamadas do servidor atual](tools/server-call-usage/server-call-usage-dashboard.md)
      + [Visualizar uso do conjunto de relatórios](tools/server-call-usage/report-suite-usage.md)
      + [Alertas de uso de chamadas do servidor](tools/server-call-usage/scu-alerts.md)
      + [Perguntas frequentes sobre o uso de chamadas do servidor](tools/server-call-usage/overage-faq.md)
   + Gerenciamento de usuários e produtos (legado) {#user-product-management}
      + [Gerenciamento de usuários e produtos (legado)](tools/user-management/user-management.md)
      + [Gerenciar contas de usuário, ativos e expirações legados](tools/user-management/users-assets.md)
      + Migrar usuários para o Adobe Admin Console {#migrate-users}
         + [Migração de usuários do Analytics para o Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [Migrar contas de usuário do Analytics para Adobe IDs](tools/user-management/user-migration/t-migrate-users.md)
         + [Migrar contas de usuário do Analytics para Enterprise e Federated IDs](tools/user-management/user-migration/migrate-enterprise.md)
         + [Desabilitar logons herdados](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [APIs afetadas pela migração](tools/user-management/user-migration/developer.md)
+ [API de administração](c-admin-api/c-admin-api.md)
+ [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

