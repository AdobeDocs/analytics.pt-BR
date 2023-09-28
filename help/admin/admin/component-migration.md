---
description: Explica como migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics.
title: Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics
feature: Admin Tools
source-git-commit: 8a9c3b4d6c7a59582a6fd8bdc5464c2dbed3ad1b
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 5%

---

# Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics

Os administradores do Adobe Analytics podem migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics.

O processo de migração inclui:

* Recriação de projetos do Adobe Analytics no Customer Journey Analytics.

* Correspondência de dimensões e métricas dos conjuntos de relatórios do Adobe Analytics com dimensões e métricas em visualizações de dados do Customer Journey Analytics.

  Algumas dimensões e métricas são correspondidas automaticamente; outras você deve corresponder manualmente como parte do processo de migração.

## Pré-requisitos 

Antes de preparar os projetos e as dimensões e métricas associadas para a migração, primeiro é necessário:

* Use o conector de origem do Analytics para exibir os dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics. Para fazer isso, é necessário:

   * [Configurar conjuntos de relatórios para assimilação no Adobe Experience Platform e no Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Assimilar e usar os dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=pt-BR)

* Verifique se os usuários no Customer Journey Analytics estão provisionados para as visualizações de dados em que os dados estão sendo correspondidos.

  Para obter mais informações, consulte [Permissões de Customer Journey Analytics no Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [controle de acesso Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  A guia Permissões faz parte de cada perfil de produto em Admin Console. Você pode adicionar usuários a perfis de produtos específicos. Em seguida, você atribui direitos a visualizações de dados específicas e determina as permissões dos usuários em um perfil de produto.

## Criar um plano de migração como uma organização

Como todos os componentes correspondentes a uma determinada migração de projeto se aplicam a todas as migrações de projeto futuras para toda a organização, é importante que sua organização planeje todas as migrações de projeto antecipadamente.

Você deve decidir como uma organização quais dimensões e métricas serão correspondidas com o que é correspondido, a fim de evitar que administradores individuais tomem decisões em um silo no momento da migração de um projeto.

## Migrar projetos do Adobe Analytics para o Customer Journey Analytics

>[!IMPORTANT]
>
>Antes de migrar qualquer projeto para o Customer Journey Analytics conforme descrito nesta seção, saiba mais sobre a migração de projetos na [Planejar a migração](#plan-the-migration) acima.
>
>Quaisquer dimensões ou métricas que você corresponder serão permanentes, tanto para este projeto quanto para todos os projetos futuros que forem migrados em toda a organização. Se você continuar, as correspondências feitas não poderão ser modificadas.



1. No Adobe Analytics, selecione a variável [!UICONTROL **Admin**] e selecione [!UICONTROL **Todos os administradores**].

1. Em [!UICONTROL **Configuração e coleção de dados**], selecione [!UICONTROL **Migração de componentes**].

1. (Condicional) Para localizar rapidamente o projeto que deseja migrar, você pode:

   * Filtre a lista de projetos selecionando o ícone Filtrar.

     Você pode filtrar pelos seguintes critérios:

      * Status

      * Tags

      * Conjunto de relatórios

      * Proprietários

      * Outros filtros

   * Use o campo de pesquisa para pesquisar o projeto que você deseja migrar.

1. Passe o mouse sobre o projeto que você deseja migrar e selecione a **Migrar** ícone ![Migrar projeto](assets/migrate.svg).

   Ou

   Selecione o projeto que você deseja migrar e selecione [!UICONTROL **Migrar para o Customer Journey Analytics**].

   Você pode selecionar apenas um projeto por vez para migrar.

   A variável [!UICONTROL **Migrar nome_do_projeto para Customer Journey Analytics**] é exibida.

   <!-- add screenshot -->

1. No [!UICONTROL **Proprietário do projeto**] comece digitando o nome do usuário que deseja definir como proprietário do projeto no Customer Journey Analytics e selecione o nome no menu suspenso.

   O proprietário especificado tem direitos totais de gerenciamento ao projeto.

1. No [!UICONTROL **Corresponder esquema para conjuntos de relatórios**] selecione um conjunto de relatórios.

1. No [!UICONTROL **Visualização de dados**] selecione a visualização de dados do Customer Journey Analytics no qual você deseja que o projeto e os componentes sejam migrados.

1. Selecionar [!UICONTROL **Corresponder esquema**].

1. No [!UICONTROL **Corresponder esquema**] , expanda a [!UICONTROL **Dimension**] e [!UICONTROL **Métricas**] seções.

   Algumas dimensões e métricas no Adobe Analytics são automaticamente correspondidas a uma dimensão ou métrica no Customer Journey Analytics. Outros precisam ser correspondidos manualmente.

   **Dimensões e métricas automaticamente correspondidas**

   Algumas dimensões e métricas no Adobe Analytics são automaticamente correspondidas a uma dimensão ou métrica no Customer Journey Analytics. Você não pode tomar decisões correspondentes para essas dimensões e métricas.

   Por exemplo, a variável **Visitas** no Adobe Analytics é automaticamente compatível com a variável **Sessões** métrica em Customer Journey Analytics.

   É possível selecionar qualquer dimensão ou métrica para visualizar suas IDs associadas.

   <!-- update screenshot after I can see the Status column -->

   ![Esquema de migração de projeto](assets/project-migration-schema.png)

   **Corresponder dimensões e métricas manualmente**

   Outras dimensões e métricas no Adobe Analytics não podem ser correspondidas automaticamente a uma dimensão ou métrica no Customer Journey Analytics.

   Quando uma dimensão ou métrica não pode ser correspondida automaticamente, um contador laranja é exibido ao lado da variável [!UICONTROL **Dimension**] ou [!UICONTROL **Métricas**] cabeçalho de seção, indicando o número de dimensões ou métricas que precisam ser correspondidas manualmente. Na tabela, um ícone de aviso ![ícone de aviso](assets/schema-warning.png) é exibido ao lado de cada dimensão ou métrica que precisa ser correspondida manualmente.

   <!-- update screenshot after I can see the Status column -->

   ![Correspondência manual do esquema de migração](assets/schema-manual-map.png)

1. Para corresponder manualmente dimensões e métricas, selecione uma dimensão ou métrica que contenha um ícone de aviso ![ícone de aviso](assets/schema-warning.png), depois no [!UICONTROL **Métrica de Customer Journey Analytics correspondente**] (ou o campo [!UICONTROL **Coincidir dimensão de Customer Journey Analytics**] se você estiver correspondendo a uma dimensão), selecione a dimensão ou métrica em Customer Journey Analytics que deseja corresponder com a dimensão ou métrica selecionada.

   ![corresponder dimensões e métricas](assets/schema-manual-map-drop-down.png)

   Repita esse processo para cada dimensão ou métrica que contenha o ícone de aviso.

   Depois que todas as dimensões e métricas no conjunto de relatórios do Adobe Analytics são correspondidas a uma dimensão ou métrica na visualização de dados Customer Journey Analytics, aparece uma marca de seleção verde ![marca de seleção](assets/report-suite-check.png) aparece ao lado do nome do conjunto de relatórios na [!UICONTROL **Corresponder esquema para conjuntos de relatórios**] seção.

1. (Condicional) Se o projeto que você está migrando contiver mais de um conjunto de relatórios, selecione outro conjunto de relatórios na [!UICONTROL **Corresponder esquema para conjuntos de relatórios**] e repita as etapas de 6 a 10. <!-- double-check that the step numbers are still correct -->

1. Selecionar [!UICONTROL **Migrar**].

   >[!WARNING]
   >
   >   Uma mensagem de aviso na tela é exibida após a seleção [!UICONTROL **Migrar**]. Antes de continuar, entenda que qualquer dimensão ou métrica correspondente é permanente, tanto para este projeto quanto para todos os projetos futuros que serão migrados em toda a organização. Se você continuar, as correspondências feitas não poderão ser modificadas.
