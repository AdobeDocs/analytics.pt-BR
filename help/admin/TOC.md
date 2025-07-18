---
product: analytics
audience: admin
user-guide-title: Guia de administração do Analytics
breadcrumb-title: Guia de administração
user-guide-description: Saiba mais sobre as tarefas administrativas do Analytics, como gerenciar usuários e produtos no Admin Console da Experience Cloud, configurar conjuntos de relatórios e muito mais.
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 98%

---


# Guia do administrador do Adobe Analytics {#admin}

+ [Guia de administração do Analytics](home.md)
+ [Notas de versão do Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
+ Adobe Admin Console {#admin-console}
   + [Visão geral](admin-console/home.md)
   + [Guia do primeiro administrador do Adobe Analytics](admin-console/first-admin-guide.md)
   + [Funções de administrador no Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Resumo das permissões das ferramentas do Analytics {#permissions}
      + [Perfis de produto para o Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Permissões de perfil de produto para Ferramentas de conjuntos de relatórios](admin-console/permissions/report-suite-tools.md)
      + [Permissões de perfil de produto para as Ferramentas do Analytics](admin-console/permissions/analytics-tools.md)
+ Ferramentas administrativas do Analytics {#admin-tools}
   + [Visão geral das ferramentas administrativas](admin/c-admin-tools.md)
   + [Gerenciador de código](admin/code-manager-admin.md)
   + [Inventário do Analytics](admin/analytics-inventory.md)
   + [Fontes de dados](admin/data-sources.md)
   + [Excluir por endereço IP](admin/exclude-ip.md)
   + [Logs](admin/logs.md)
   + Gerenciador de atividades de relatórios {#reporting-activity-manager}
      + [Visão geral](admin/reporting-activity-manager/reporting-activity-overview.md)
      + [Exibir atividade de relatório](admin//reporting-activity-manager/reporting-activity.md)
      + [Cancelar solicitações de geração de relatórios](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migração de componentes {#component-migration}
      + [Preparar para migração](admin/component-migration/prepare-component-migration.md)
      + [Fluxo de trabalho de migração](admin/component-migration/component-migration.md)
   + Gerenciador de conjuntos de relatórios {#manage-report-suites}
      + Editar configurações de um conjunto de relatórios {#edit-report-suite}
         + Geral {#report-suite-general}
            + [Configurações gerais da conta](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtros internos do URL](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [Personalizar calendário](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Detecção de pesquisa paga {#paid-search-detection}
               + [Visão geral da detecção de pesquisa paga](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configurar a detecção de pesquisa paga](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + Regras de processamento {#processing-rules}
               + [Visão geral](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)
               + [Interface](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-interface.md)
               + [Visualizar histórico](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-view-history.md)
               + [Copiar regras](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-copy.md)
               + [Dimensões e métricas disponíveis](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-variables.md)
               + [Casos de uso](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-use-cases.md)
            + Regras de bot {#bot-removal}
               + [Remoção de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Noções básicas e configuração de regras de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Assinaturas comuns do bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Métodos de exclusão de bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Configurações de privacidade](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Configuração de carimbos de data e hora](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Encaminhamento pelo lado do servidor {#server-side-forwarding}
               + [Visão geral do encaminhamento pelo lado do servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [Conformidade com o RGPD/ePrivacy e o encaminhamento pelo lado do servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisitos do encaminhamento pelo lado do servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Referência de dados e de código do encaminhamento pelo lado do servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Como verificar a implementação do encaminhamento pelo lado do servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Perguntas frequentes sobre o encaminhamento pelo lado do servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Tráfego {#traffic-variables}
            + [Variáveis de tráfego](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Classificações de tráfego](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descrições do relatório personalizado](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Conversão {#conversion-variables}
            + [Variáveis de conversão](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Métodos de descoberta](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [Classificações de conversão](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + Variável de visitante único {#unique-visitor-variable}
               + [Especificar a Variável de visitante único](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso de uso - Extração de IDs de visitantes](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Eventos bem-sucedidos](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
            + [Hierarquias de classificação](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Variáveis da lista](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [eVars de merchandising](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + Canais de marketing {#marketing-channels}
            + [Gerenciador de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [Regras de processamento de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [Classificações de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [Expiração de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + Gerenciamento de tráfego {#traffic-management}
            + [Visão geral](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Programar pico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Tráfego permanente](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Métricas padrão](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + Gerenciamento de aplicativos {#app-management}
            + [Relatório do aplicativo](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
            + [Classificações do aplicativo](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
         + [Gerenciamento de mídia](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [Relatórios de privacidade](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Gerenciamento da Document Cloud {#doc-cloud-mgt}
            + [Configurar a Document Cloud com o Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Configurar relatórios da Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Configuração do Advertising Analytics](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + Tempo real {#real-time-reports}
            + [Visão geral dos Relatórios em tempo real](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configuração de relatórios em tempo real](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Métricas e dimensões em tempo real compatíveis](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [Gerenciar conjuntos de relatórios](admin/c-manage-report-suites/report-suites-admin.md)
      + [Conjuntos de relatórios globais](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Salvar uma pesquisa do conjunto de relatórios](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Fazer download das configurações do conjunto de relatórios](admin/c-manage-report-suites/t-download-rs-settings.md)
      + Novo conjunto de relatórios {#c-new-report-suite}
         + [Criar um conjunto de relatórios](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Criar um grupo de conjunto de relatórios](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [Configurações do novo conjunto de relatórios](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [Configurações não copiadas do conjunto de relatórios de origem](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + Modelos de conjunto de relatórios {#report-suite-templates}
         + [Visão geral dos modelos de conjunto de relatórios](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [Portal agregador](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [Comércio](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [Conteúdo e mídia](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [Modelo padrão](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [Serviços financeiros](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [Portal de trabalho](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [Geração de leads](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Mídia de suporte](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + Configurações da empresa {#company-settings}
      + [Visão geral das configurações da empresa](admin/company/c-company-settings.md)
      + [Gerenciador de segurança](admin/company/security-manager.md)
      + [Serviços Web](admin/company/web-services-admin.md)
      + [Relatórios do Report Builder](admin/company/report-builder-reports-admin.md)
      + [Logon único](admin/company/single-signon-admin.md)
      + [Ocultar conjuntos de relatórios](admin/company/c-hide-report-suites.md)
      + [Gerenciador de preferências](admin/company/preferences-manager.md)
      + [Ações pendentes](admin/company/pending-actions-admin.md)
      + [Níveis de acesso a recursos](admin/company/feature-access-levels.md)
   + Rotulagem de privacidade de governança de dados {#data-governance}
      + [Fluxo de trabalho de Privacidade de dados do Adobe Analytics](admin/c-data-governance/an-gdpr-workflow.md)
      + [Perguntas frequentes](admin/c-data-governance/gdpr-faq.md)
      + Rotulagem de dados {#data-labels}
         + [Rótulos de privacidade de dados para componentes do Analytics](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [Rotular dados do conjunto de relatórios](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [Exibir/gerenciar rótulos de privacidade do conjunto de relatórios](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [Práticas recomendadas de rotulagem](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [Exemplo de rotulagem](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [Namespaces](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [Isenção de consentimento da CNIL](admin/c-data-governance/cnil-consent-exemption.md)
   + Uso de chamadas do servidor {#server-call-usage}
      + [Visão geral do uso de chamadas do servidor](admin/c-server-call-usage/overage-overview.md)
      + [Visualizar uso de chamadas do servidor atual](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Visualizar uso do conjunto de relatórios](admin/c-server-call-usage/report-suite-usage.md)
      + [Alertas de uso de chamadas do servidor](admin/c-server-call-usage/scu-alerts.md)
      + [Perguntas frequentes sobre o uso de chamadas do servidor](admin/c-server-call-usage/overage-faq.md)
   + Gerenciamento de usuários e produtos (legado) {#user-product-management}
      + [Gerenciamento de usuários e produtos (legado)](admin/user-management2/user-management.md)
      + [Gerenciar contas de usuário, ativos e expirações legados](admin/user-management2/users-assets.md)
      + Migrar usuários para o Adobe Admin Console {#migrate-users}
         + [Migração de usuários do Analytics para o Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [Migrar contas de usuário do Analytics para Adobe IDs](admin/user-management2/user-migration/t-migrate-users.md)
         + [Migrar contas de usuário do Analytics para Enterprise e Federated IDs](admin/user-management2/user-migration/migrate-enterprise.md)
         + [Desabilitar logons herdados](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [APIs afetadas pela migração](admin/user-management2/user-migration/developer.md)
+ [API de administração](c-admin-api/c-admin-api.md)
+ [Perguntas frequentes sobre o fim da vida útil da API do Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

