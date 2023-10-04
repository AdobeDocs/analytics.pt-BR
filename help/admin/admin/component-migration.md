---
description: Explica como migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics.
title: Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics
feature: Admin Tools
source-git-commit: e32b239fd64eea4516bc73b934b10346832f2bab
workflow-type: tm+mt
source-wordcount: '2051'
ht-degree: 8%

---

# Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics

Os administradores do Adobe Analytics podem migrar projetos do Adobe Analytics e seus componentes associados para o Customer Journey Analytics.

O processo de migração inclui:

* Recriação de projetos do Adobe Analytics no Customer Journey Analytics.

* Mapeamento de dimensões e métricas dos conjuntos de relatórios do Adobe Analytics para dimensões e métricas em visualizações de dados do Customer Journey Analytics.

  Algumas dimensões e métricas são mapeadas automaticamente; outras, você deve mapear manualmente como parte do processo de migração. Os segmentos também são migrados, mas não precisam ser mapeados como parte do processo de migração.

  Todos os componentes migrados são exibidos no resumo da migração quando ela é concluída.

## Preparar-se para uma migração

Antes que qualquer pessoa na sua organização comece a migrar projetos, conclua as seções a seguir.

### Pré-requisitos 

Antes de preparar os projetos e os componentes associados para a migração, primeiro é necessário:

* Use o conector de origem do Analytics para exibir os dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics. Para fazer isso, é necessário:

   * [Configurar conjuntos de relatórios para assimilação no Adobe Experience Platform e no Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Assimilar e usar os dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=pt-BR)

* Verifique se os usuários no Customer Journey Analytics estão provisionados para as visualizações de dados em que os dados estão sendo mapeados.

  Para obter mais informações, consulte [Permissões de Customer Journey Analytics no Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [controle de acesso Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  A guia Permissões faz parte de cada perfil de produto em Admin Console. Você pode adicionar usuários a perfis de produtos específicos. Em seguida, você atribui direitos a visualizações de dados específicas e determina as permissões dos usuários em um perfil de produto.

* Crie um plano de migração, conforme descrito na seção abaixo, [Criar um plano de migração como uma organização](#create-a-migration-plan-as-an-organization).

### Entender o que está incluído em uma migração

As tabelas a seguir descrevem quais elementos de um projeto e componente são incluídos em uma migração:

#### Elementos de componentes migrados

Os Dimension e as métricas são migrados como parte do processo de mapeamento descrito em [Migrar projetos do Adobe Analytics para o Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics), enquanto os segmentos e intervalos de datas são recriados em Customer Journey Analytics com base no

|  | Migrado |
|---------|---------|
| **[Proprietário](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimension e métricas: Não<p>Segmentos e intervalos de datas: ![marca de seleção](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Compartilhamento](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension e métricas: Não<p>Segmentos e intervalos de datas: Não</p> |
| **[Descrições](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimension e métricas: Não<p>Segmentos e intervalos de datas: ![marca de seleção](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Tags](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension e métricas: Não<p>Segmentos e intervalos de datas: Não</p> |
| **[Atribuição (em dimensões)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimension e métricas: Não<p>Segmentos e intervalos de datas: Não</p> |

{style="table-layout:auto"}

#### Elementos de projeto migrados

|  | Migrado |
|---------|----------|
| **[Intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Segmentos](/help/components/segmentation/seg-overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Dimensões](/help/components/dimensions/overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) Mapeado automática ou manualmente |
| **[Métricas](/help/components/metrics/overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) Mapeado automática ou manualmente |
| **[Painéis](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Proprietário](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) Definido pelo usuário que faz a migração |
| **[Preparação](/help/analyze/analysis-workspace/curate-share/curate.md)** | Não |
| **[Compartilhamento (funções de projeto)](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | Não <!-- Add info on Share with Anyone? Is it the same?--> |
| **[Anotações](/help/analyze/analysis-workspace/components/annotations/overview.md)** | Não |
| **[Estrutura de pastas](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | Não |
| **[Descrições](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![marca de seleção](assets/Smock_Checkmark_18_N.svg) |
| **[Tags](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | Não |
| **[Agendamentos](/help/components/scheduled-projects-manager.md)** | Não |

{style="table-layout:auto"}

<!-- What about Anomaly Detection and Favorites? -->

### Compreender elementos não compatíveis que causam erros

As seguintes visualizações, painéis e recursos não são compatíveis com o Customer Journey Analytics. Quando esses elementos são incluídos em um projeto antes da migração, podem causar falha na migração ou resultar em erros após a migração.

Remova esses elementos do projeto do Adobe Analytics antes de migrar o projeto para o Customer Journey Analytics. Se uma migração falhar, remova esses elementos antes de tentar a migração novamente.

#### Visualizações não suportadas

* [Mapa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

#### Painéis não suportados

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Comparação de segmentos](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Público médio por minuto de mídia](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Próximo item ou anterior](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Resumo da página](/help/analyze/analysis-workspace/c-panels/page-summary.md)

#### Recursos incompatíveis

* [Análise de contribuição](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)

* [Alertas](/help/components/c-alerts/intellligent-alerts.md)

### Decida como uma organização como você mapeará componentes

>[!IMPORTANT]
>
>O processo de migração identifica componentes no seu projeto do Adobe Analytics que não podem ser mapeados automaticamente para componentes no Customer Journey Analytics e permite mapeá-los manualmente.
>
>**Qualquer mapeamento feito em um projeto se aplica a todos os projetos futuros em toda a organização, independentemente de qual usuário está executando a migração. Esses mapeamentos não podem ser modificados ou desfeitos, exceto ao entrar em contato com o Atendimento ao cliente.**
>
>Por isso, é importante que sua organização decida como dimensões e métricas serão mapeadas antes que qualquer projeto seja migrado. Isso evita que administradores individuais tomem decisões em um silo ao considerar apenas um único projeto.
>
>Veja a seguir uma lista de dimensões e métricas que você deve mapear manualmente se elas existirem no seu projeto. Recomendamos revisar esta lista antes de migrar. Se qualquer um desses componentes existir em seu projeto, decida agora a quais componentes do Customer Journey Analytics você os mapeará.


#### Dimension que deve ser mapeado manualmente

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


#### Métricas que devem ser mapeadas manualmente

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


## Migrar projetos do Adobe Analytics para o Customer Journey Analytics

>[!IMPORTANT]
>
>Antes de migrar qualquer projeto para o Customer Journey Analytics conforme descrito nesta seção, saiba mais sobre a migração de projetos na [Planejar a migração](#plan-the-migration) acima.
>
>Quaisquer dimensões ou métricas mapeadas são permanentes, tanto para este projeto quanto para todos os projetos futuros migrados em toda a organização. Os mapeamentos criados não poderão ser modificados após a conclusão da migração.

1. No Adobe Analytics, selecione a guia [!UICONTROL **Administrador**] e escolha [!UICONTROL **Todos os administradores**].

1. Em [!UICONTROL **Configuração e coleção de dados**], selecione [!UICONTROL **Migração de componentes**].

1. Localize o projeto que você deseja migrar. Você pode filtrar, classificar ou pesquisar a lista de projetos.

   Por padrão, somente os projetos compartilhados com você são exibidos. Para exibir todos os projetos em sua organização, selecione a **Filtro** ícone e, em seguida, expandir [!UICONTROL **Outros filtros**] e selecione [!UICONTROL **Mostrar tudo**]. (Para obter mais informações sobre filtragem, classificação e pesquisa da lista de projetos, consulte [Filtrar, classificar e pesquisar a lista de projetos](#filter-sort-and-search-the-list-of-projects).)

1. Passe o mouse sobre o projeto que você deseja migrar e selecione a **Migrar** ícone ![Migrar projeto](assets/migrate.svg).

   Ou

   Selecione o projeto que você deseja migrar e selecione [!UICONTROL **Migrar para o Customer Journey Analytics**].

   Você pode selecionar apenas um projeto por vez para migrar.

   A variável [!UICONTROL **Migrar nome_do_projeto para Customer Journey Analytics**] é exibida.

   <!-- add screenshot -->

1. No [!UICONTROL **Proprietário do projeto**] comece digitando o nome do usuário que deseja definir como proprietário do projeto no Customer Journey Analytics e selecione o nome no menu suspenso.

   O proprietário especificado tem todos os direitos de gerenciamento do projeto.

1. No [!UICONTROL **Mapear esquema para conjuntos de relatórios**] selecione um conjunto de relatórios.

1. No [!UICONTROL **Visualização de dados**] selecione a visualização de dados do Customer Journey Analytics no qual você deseja que o projeto e os componentes sejam migrados.

1. Selecionar [!UICONTROL **Mapear esquema**].

1. No [!UICONTROL **Mapear esquema**] , expanda a [!UICONTROL **Dimension**] e [!UICONTROL **Métricas**] seções.

   Algumas dimensões e métricas no Adobe Analytics são mapeadas automaticamente para uma dimensão ou métrica no Customer Journey Analytics. Outros precisam ser mapeados manualmente.

   **Mapear dimensões e métricas automaticamente**

   Algumas dimensões e métricas no Adobe Analytics são mapeadas automaticamente para uma dimensão ou métrica no Customer Journey Analytics. Não é possível tomar decisões de mapeamento para essas dimensões e métricas.

   Por exemplo, a variável **Visitas** no Adobe Analytics é mapeada automaticamente com a variável **Sessões** métrica em Customer Journey Analytics.

   É possível selecionar qualquer dimensão ou métrica para visualizar suas IDs associadas.

   <!-- update screenshot after I can see the Status column -->

   ![Esquema de migração de projeto](assets/project-migration-schema.png)

   **Mapear dimensões e métricas manualmente**

   Algumas dimensões e métricas no Adobe Analytics não podem ser mapeadas automaticamente para uma dimensão ou métrica no Customer Journey Analytics.

   Quando uma dimensão ou métrica não pode ser mapeada automaticamente, um contador laranja é exibido ao lado da variável [!UICONTROL **Dimension**] ou [!UICONTROL **Métricas**] cabeçalho de seção, indicando o número de dimensões ou métricas que precisam ser mapeadas manualmente. Na tabela, um ícone de aviso ![ícone de aviso](assets/schema-warning.png) é exibido ao lado de cada dimensão ou métrica que precisa ser mapeada manualmente.

   Além disso, a [!UICONTROL **Status**] diz a coluna [!UICONTROL **Não mapeado**].

   <!-- update screenshot after I can see the Status column -->

   ![Mapa manual do esquema de migração](assets/schema-manual-map.png)

1. Para mapear dimensões e métricas manualmente, selecione uma dimensão ou métrica que contenha um ícone de aviso ![ícone de aviso](assets/schema-warning.png), depois no [!UICONTROL **Métrica de Customer Journey Analytics mapeada**] (ou o campo [!UICONTROL **Dimensão Customer Journey Analytics mapeada**] se estiver mapeando uma dimensão), selecione a dimensão ou métrica em Customer Journey Analytics que deseja mapear para a dimensão ou métrica selecionada.

   ![mapear dimensões e métricas](assets/schema-manual-map-drop-down.png)

   Depois que uma dimensão ou métrica é mapeada, o ícone de aviso desaparece e a variável [!UICONTROL **Status**] a coluna muda para [!UICONTROL **Mapeado**] com um ponto verde. (Um status de [!UICONTROL **Mapeado**] quando um ponto cinza indica que a dimensão ou métrica foi mapeada durante uma migração anterior; qualquer mapeamento anterior não pode ser atualizado).

   Repita esse processo para cada dimensão ou métrica que contenha o ícone de aviso.

   Depois que todas as dimensões e métricas do conjunto de relatórios do Adobe Analytics forem mapeadas para uma dimensão ou métrica na visualização de dados Customer Journey Analytics, insira uma marca de seleção verde ![marca de seleção](assets/report-suite-check.png) aparece ao lado do nome do conjunto de relatórios na [!UICONTROL **Mapear esquema para conjuntos de relatórios**] seção.

1. (Condicional) Se o projeto que você está migrando contiver mais de um conjunto de relatórios, selecione outro conjunto de relatórios na [!UICONTROL **Mapear esquema para conjuntos de relatórios**] e repita as etapas de 6 a 10. <!-- double-check that the step numbers are still correct -->

1. Selecionar [!UICONTROL **Migrar**].

   >[!WARNING]
   >
   >   Uma mensagem de aviso na tela é exibida após a seleção [!UICONTROL **Migrar**]. Antes de continuar, saiba que qualquer dimensão ou métrica mapeada é permanente para este projeto e para todos os projetos futuros migrados em toda a organização. Se você continuar, os mapeamentos criados não poderão ser modificados.

   Após a conclusão de uma migração, a variável [!UICONTROL **Status da migração**] fornece um resumo do que foi migrado.

   Se a migração falhar, consulte a [Repetir uma migração com falha](#retry-a-failed-migration) abaixo para obter mais informações.

## Repetir uma migração com falha

Se a migração falhar, você poderá tentar novamente.

Antes de tentar novamente uma migração com falha, remova qualquer [elementos não suportados](#understand-unsupported-elements-that-cause-errors) do projeto.

>[!NOTE]
>
>Se a migração continuar a falhar após uma nova tentativa, entre em contato com o Atendimento ao cliente com a ID do projeto. Você pode encontrar a ID do projeto na página Status da migração. <!-- when does this page display? How can they get there -->

Para repetir uma migração com falha:

1. No Adobe Analytics, selecione a guia [!UICONTROL **Administrador**] e escolha [!UICONTROL **Todos os administradores**].

1. Em [!UICONTROL **Configuração e coleção de dados**], selecione [!UICONTROL **Migração de componentes**].

1. Selecionar [!UICONTROL **Failed**] no [!UICONTROL **Status da migração**] ao lado do projeto que você deseja tentar novamente.

   ![falha na coluna de status da migração](assets/migration-failed.png)

   A variável [!UICONTROL **Status da migração**] é exibida.

   Essa página também é exibida imediatamente após a conclusão das etapas de migração descritas na seção [Migrar projetos do Adobe Analytics para o Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) acima.

1. Selecionar [!UICONTROL **Repetir migração**].

## Filtrar, classificar e pesquisar a lista de projetos

Você pode filtrar, classificar e pesquisar a lista de projetos na página Migração de componentes.

### Filtrar a lista de projetos

Você pode filtrar pelos seguintes critérios:

| Filtro | Descrição |
|---------|----------|
| [!UICONTROL **Status**] | O status da migração: <ul><li>[!UICONTROL **Não iniciado**]</li><li>[!UICONTROL **Iniciado**]</li><li>[!UICONTROL **Concluído**]</li><li>[!UICONTROL **Falha**]</li></ul>. |
| [!UICONTROL **Tags**] | Selecione tags na lista. Somente os projetos que têm as tags selecionadas aplicadas são exibidos. |
| [!UICONTROL **Conjunto de relatórios**] | Selecione qualquer conjunto de relatórios na lista de conjuntos de relatórios. Somente os projetos que usam os conjuntos de relatórios selecionados são exibidos. |
| [!UICONTROL **Proprietários**] | Selecione qualquer proprietário na lista de proprietários. Somente projetos pertencentes aos usuários selecionados são exibidos. |
| [!UICONTROL **Outros filtros**] | Os seguintes filtros adicionais estão disponíveis: <ul><li>[!UICONTROL **Meus**]: mostra somente projetos nos quais você está definido como proprietário.</li><li>[!UICONTROL **Compartilhado comigo**]: mostra somente projetos que foram compartilhados com você.</li><li>[!UICONTROL **Favoritos**]: mostra somente os projetos marcados como favoritos. (Você pode marcar um projeto como favorito na [página de aterrissagem do projeto](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensalmente**]</li><li>[!UICONTROL **Anualmente**]</li></ul> |

{style="table-layout:auto"}

### Classificar a lista de projetos

Você pode classificar a lista de projetos por qualquer coluna.

Para classificar a lista de projetos:

1. Selecione o cabeçalho da coluna pela qual deseja classificar.

1. (Opcional) Selecione o mesmo cabeçalho de coluna novamente para inverter a ordem de classificação.

### Procurar um projeto

Você pode pesquisar a lista de projetos na página Migração de componentes para encontrar o projeto que deseja migrar.

1. No campo de pesquisa na parte superior da página Migração de componentes, comece digitando o nome do projeto que deseja migrar.

1. Selecione o projeto quando ele aparecer no menu suspenso.

<!-- is there going to be a way to customize the columns that are displayed? -->
