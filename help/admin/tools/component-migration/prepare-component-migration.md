---
description: Explica os preparativos necessários para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics.
title: Preparar-se para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: ec4475cdd8f0c3e89f528bd60155caa1ca3f0645
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 10%

---

# Preparar-se para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics

Antes que qualquer pessoa na sua organização comece a migrar projetos conforme descrito em [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md), conclua as seções a seguir.

## Pré-requisitos

Antes de migrar seus projetos e componentes associados, primeiro siga as etapas do [Evolution from Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=pt-BR) no Guia do Adobe Customer Journey Analytics. Essas etapas incluem:

1. Use qualquer um dos métodos a seguir para assimilar dados na Adobe Experience Platform e exibir dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics:

   >[!NOTE]
   >
   >  Quando você usa o SDK da Web para assimilar dados, todos os campos de esquema devem ser mapeados manualmente. (Para obter mais informações sobre o processo de mapeamento, consulte [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md))


   * Para usar o conector de origem do Adobe Analytics, é necessário:

      1. [Configurar conjuntos de relatórios para assimilação na Adobe Experience Platform e no Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Assimilar e usar os dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=pt-BR)

   * Para usar o SDK da Web, é necessário:

      1. [Configurar conjuntos de relatórios para assimilação na Adobe Experience Platform e no Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Assimilar dados via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. Crie uma [conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) e [exibição de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=pt-BR) com os dados assimilados.

1. Verifique se os usuários no Customer Journey Analytics estão provisionados para as visualizações de dados em que os dados estão sendo mapeados.

   Para obter mais informações, consulte [Permissões do Customer Journey Analytics no Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html#customer-journey-analytics-permissions-in-admin-console) em [Controle de acesso do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

   A guia Permissões faz parte de cada perfil de produto no Admin Console. Você pode adicionar usuários a perfis de produtos específicos. Em seguida, você atribui direitos a visualizações de dados específicas e especifica quais permissões os usuários em um perfil de produto têm.

1. Decida como uma organização como você mapeará componentes.

   Para obter mais informações, consulte a seção abaixo, [Decida como uma organização como mapear componentes](#decide-as-an-organization-how-you-will-map-components).

## Entender o que está incluído em uma migração

As tabelas a seguir descrevem quais elementos de um projeto e componente são incluídos em uma migração:

### Elementos de componentes migrados

Dimensões e métricas são migradas como parte do processo de mapeamento descrito em [Migrar projetos do Adobe Analytics para o Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics).

Segmentos, intervalos de datas e métricas calculadas que ainda não existem no Customer Journey Analytics são recriados lá com base nas dimensões e métricas mapeadas.

|  | Migrado |
|---------|---------|
| **[Proprietário](/help/components/calculated-metrics/workflow/cm-manager.md)** | Dimensões e métricas: Não<p>Segmentos e intervalos de datas: ![marca de seleção](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Compartilhamento](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensões e métricas: Não<p>Segmentos e intervalos de datas: Não</p> |
| **[Descrições](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimensões e métricas: Não<p>Segmentos e intervalos de datas: ![marca de seleção](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Tags](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimensões e métricas: Não<p>Segmentos e intervalos de datas: Não</p> |
| **[Atribuição (em dimensões)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimensões e métricas: Não<p>Segmentos e intervalos de datas: Não</p> |

{style="table-layout:auto"}

### Elementos de projeto migrados

|  | Migrado |
|---------|----------|
| **[Intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Segmentos](/help/components/segmentation/seg-overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Dimensões](/help/components/dimensions/overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) Mapeada automática ou manualmente |
| **[Métricas](/help/components/metrics/overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) Mapeada automática ou manualmente |
| **[Painéis](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Proprietário](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) Definida pelo usuário que está fazendo a migração |
| **[Curadoria](/help/analyze/analysis-workspace/curate-share/curate.md)** | Não |
| **[Compartilhamento](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | Não |
| **[Anotações](/help/analyze/analysis-workspace/components/annotations/overview.md)** | Não |
| **[Estrutura de pastas](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | Não |
| **[Descrições](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Tags](/help/analyze/landing.md)** | Não |
| **[Favoritos](/help/analyze/landing.md)** | Não |
| **[Calendários](/help/components/scheduled-projects-manager.md)** | Não |
| **[Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Compreender elementos não compatíveis que causam erros

As seguintes visualizações e painéis não são compatíveis com o Customer Journey Analytics. Quando esses elementos são incluídos em um projeto antes da migração, podem causar falha na migração ou resultar em erros após a migração.

Remova esses elementos do projeto do Adobe Analytics antes de migrar o projeto para o Customer Journey Analytics. Se uma migração falhar, remova esses elementos antes de tentar a migração novamente.

### Painéis não suportados

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Comparação de segmentos ](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Público-alvo médio por minuto de mídia](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Próximo item ou anterior](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Resumo da página](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [Análise de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## Decida como uma organização como você mapeará componentes

>[!NOTE]
>
>O processo de migração identifica componentes no seu projeto do Adobe Analytics que não podem ser mapeados automaticamente para componentes no Customer Journey Analytics e permite mapeá-los manualmente.
>
>**Qualquer mapeamento feito em um projeto se aplica a todos os projetos futuros em toda a organização IMS, independentemente de qual usuário está executando a migração. Esses mapeamentos podem ser atualizados durante a migração de projetos futuros.**
>
>É importante que sua organização decida como dimensões e métricas serão mapeadas antes que qualquer projeto seja migrado. Isso evita que administradores individuais tomem decisões em um silo ao considerar apenas um único projeto.
>
>Veja a seguir uma lista de dimensões e métricas que você deve mapear manualmente se elas existirem no seu projeto. Recomendamos revisar esta lista antes de migrar. Se qualquer um desses componentes existir em seu projeto, decida agora a quais componentes do Customer Journey Analytics você os mapeará.


### Dimensões que devem ser mapeadas manualmente

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* categoria
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identiationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### Métricas que devem ser mapeadas manualmente

* timespentvisit
* timespentvisitor
* recarregamentos
* devoluções
* bouncerate
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisitors
* singlepagevisits
* singlevaluevisitors
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* novos engajamentos
* granularidade_tempo
* concurrent_views_visitors
* concurrent_views_occurrences
* dispositivos
* estimatedpeople
* playback_time_sent_seconds
* playback_time_sent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression
