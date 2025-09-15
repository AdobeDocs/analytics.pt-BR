---
description: Explica como migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics.
title: Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: ec4475cdd8f0c3e89f528bd60155caa1ca3f0645
workflow-type: tm+mt
source-wordcount: '1641'
ht-degree: 4%

---

# Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics

Os administradores do Adobe Analytics podem migrar projetos do Adobe Analytics e seus componentes associados para o Customer Journey Analytics.

O processo de migração inclui:

* Recriação de projetos do Adobe Analytics no Customer Journey Analytics.

* Mapeamento de dimensões e métricas de conjuntos de relatórios do Adobe Analytics de acordo com as dimensões e métricas das visualizações de dados do Customer Journey Analytics.

  Algumas dimensões e métricas são mapeadas automaticamente; outras, você deve mapear manualmente como parte do processo de migração. Os segmentos também são migrados, mas não precisam ser mapeados como parte do processo de migração.

  Todos os componentes migrados são exibidos no resumo da migração quando ela é concluída.

>[!NOTE]
>
>As informações nesta página descrevem como migrar projetos e seus componentes associados com a interface do usuário.
>
>Como alternativa, você pode executar a migração usando as APIs. Para obter mais informações, consulte as [APIs do Adobe Analytics](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs). Todas as definições de API estão disponíveis no menu suspenso **[!UICONTROL Selecionar uma definição]**.


## Preparar-se para uma migração

Antes de migrar qualquer projeto para o Customer Journey Analytics, saiba mais sobre como migrar projetos no [Prepare-se para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

Além disso, faça um [inventário do Adobe Analytics](/help/admin/tools/analytics-inventory.md) usando a ferramenta disponível para os administradores do Analytics.

## Migrar projetos do Adobe Analytics para o Customer Journey Analytics

>[!NOTE]
>
>Antes de migrar qualquer projeto para o Customer Journey Analytics conforme descrito nesta seção, saiba mais sobre como migrar projetos na [Prepare-se para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).
>
>**Quaisquer dimensões ou métricas mapeadas se aplicam a este projeto e a todos os projetos futuros em toda a organização IMS, independentemente de qual usuário esteja executando a migração. Esses mapeamentos podem ser atualizados durante a migração de projetos futuros.**

1. No Adobe Analytics, selecione a guia [!UICONTROL **Administrador**] e escolha [!UICONTROL **Todos os administradores**].

1. Em [!UICONTROL **Configuração e coleção de dados**], selecione [!UICONTROL **Migração de componentes**].

1. Localize cada projeto que deseja migrar. Você pode filtrar, classificar ou pesquisar a lista de projetos.

   Por padrão, somente os projetos compartilhados com você são exibidos. Para exibir todos os projetos em sua organização, selecione o ícone **Filtro**, expanda [!UICONTROL **Outros filtros**] e selecione [!UICONTROL **Mostrar tudo**]. (Para obter mais informações sobre filtragem, classificação e pesquisa da lista de projetos, consulte [Filtrar, classificar e pesquisar a lista de projetos](#filter-sort-and-search-the-list-of-projects).)

1. (Condicional) Para migrar vários projetos ao mesmo tempo, marque a caixa de seleção à esquerda de cada projeto que você deseja migrar e selecione [!UICONTROL **Migrar para o Customer Journey Analytics**].

   Considere o seguinte ao migrar vários projetos:

   * É possível selecionar até 20 projetos para migrar de uma só vez.

   * O status da migração deve ser o mesmo para todos os projetos que você está migrando.

     Por exemplo, se você selecionar um projeto para migração com status de migração **[!UICONTROL Não iniciado]**, não será possível selecionar outro projeto com status de migração **[!UICONTROL Falha]**.

   * Você deve designar o mesmo proprietário para todos os projetos que estão sendo migrados.

   * Dimensões e métricas devem ser mapeadas para a mesma visualização de dados para todos os projetos que você está migrando.

   A caixa de diálogo [!UICONTROL **Migrar nome_do_projeto para Customer Journey Analytics**] é exibida.

   <!-- add screenshot -->

1. (Condicional) Para migrar um único projeto, passe o mouse sobre o projeto que deseja migrar, em seguida selecione o ícone **Migrar** ![Migrar projeto](assets/migrate.svg).

   A caixa de diálogo [!UICONTROL **Migrar nome_do_projeto para Customer Journey Analytics**] é exibida.

   <!-- add screenshot -->

1. No campo [!UICONTROL **Proprietário do projeto**], comece digitando o nome do usuário que você deseja definir como proprietário dos projetos que estão sendo migrados no Customer Journey Analytics e, em seguida, selecione o nome dele no menu suspenso.

   O proprietário especificado tem direitos totais de gerenciamento aos projetos migrados. O proprietário deve ser um administrador no Customer Journey Analytics. Você pode alterar a propriedade dos projetos em uma etapa posterior.

1. Na seção [!UICONTROL **Mapear esquema para conjuntos de relatórios**], selecione um conjunto de relatórios.

1. No menu suspenso [!UICONTROL **Visualização de dados**], selecione a visualização de dados do Customer Journey Analytics para onde deseja que os projetos e componentes sejam migrados.

   Quando você migra vários projetos, todos os projetos que você está migrando são combinados no mapeamento de visualização de dados única.

1. Selecione [!UICONTROL **Mapear esquema**].

1. Na seção [!UICONTROL **Mapear esquema**], expanda as seções [!UICONTROL **Dimensões**] e [!UICONTROL **Métricas**].

   Algumas dimensões e métricas no Adobe Analytics são mapeadas automaticamente para uma dimensão ou métrica no Customer Journey Analytics. Outros precisam ser mapeados manualmente.

   **Mapear dimensões e métricas automaticamente**

   >[!NOTE]
   >
   >   Se você usou o SDK da Web para assimilar dados na Adobe Experience Platform, as dimensões e métricas não poderão ser mapeadas automaticamente. Para obter mais informações, consulte [Pré-requisitos](/help/admin/tools/component-migration/prepare-component-migration.md#prerequisites) em [Preparar para migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

   Algumas dimensões e métricas no Adobe Analytics são mapeadas automaticamente para uma dimensão ou métrica no Customer Journey Analytics. Não é possível tomar decisões de mapeamento para essas dimensões e métricas.

   Por exemplo, a métrica **Visitas** no Adobe Analytics é mapeada automaticamente com a métrica **Sessões** no Customer Journey Analytics.

   É possível selecionar qualquer dimensão ou métrica para visualizar suas IDs associadas.

   <!-- update screenshot after I can see the Status column -->

   ![Esquema de migração do projeto](assets/project-migration-schema.png)

   **Mapear dimensões e métricas manualmente**

   Algumas dimensões e métricas no Adobe Analytics não podem ser mapeadas automaticamente para uma dimensão ou métrica no Customer Journey Analytics.

   Quando uma dimensão ou métrica não pode ser mapeada automaticamente, um contador laranja é exibido ao lado do cabeçalho da seção [!UICONTROL **Dimensões**] ou [!UICONTROL **Métricas**], indicando o número de dimensões ou métricas que precisam ser mapeadas manualmente. Na tabela, um ícone de aviso ![ícone de aviso](assets/schema-warning.png) é exibido ao lado de cada dimensão ou métrica que precisa ser mapeada manualmente.

   Além disso, a coluna [!UICONTROL **Status**] diz [!UICONTROL **Não mapeado**].

   <!-- update screenshot after I can see the Status column -->

   ![Mapa manual do esquema de migração](assets/schema-manual-map.png)

1. Para mapear dimensões e métricas manualmente, selecione uma dimensão ou métrica que contenha um ícone de aviso ![ícone de aviso](assets/schema-warning.png) e, em seguida, no campo [!UICONTROL **Métrica do Customer Journey Analytics mapeada**] (ou no campo [!UICONTROL **Dimensão do Customer Journey Analytics mapeada**], se você estiver mapeando uma dimensão), selecione a dimensão ou métrica no Customer Journey Analytics que deseja mapear para a dimensão ou métrica selecionada.

   ![mapear dimensões e métricas](assets/schema-manual-map-drop-down.png)

   Depois que uma dimensão ou métrica é mapeada, o ícone de aviso desaparece e a coluna [!UICONTROL **Status**] muda para [!UICONTROL **Mapped**] com um ponto verde. (Um status de [!UICONTROL **Mapeado**] com um ponto cinza indica que a dimensão ou métrica foi mapeada durante uma migração anterior; os mapeamentos anteriores não podem ser atualizados.)

   Repita esse processo para cada dimensão ou métrica que contenha o ícone de aviso.

   Depois que todas as dimensões e métricas do conjunto de relatórios do Adobe Analytics são mapeadas para uma dimensão ou métrica no conjunto de relatórios do Customer Journey Analytics, uma marca de seleção verde ![marca de seleção](assets/report-suite-check.png) é exibida ao lado do nome do conjunto de relatórios na seção [!UICONTROL **Esquema de mapa para conjuntos de relatórios**].

1. (Condicional) Se os projetos que você está migrando contiverem mais de um conjunto de relatórios, selecione outro conjunto de relatórios na seção [!UICONTROL **Mapear esquema para conjuntos de relatórios**] e repita da etapa 6 à Etapa 10. <!-- double-check that the step numbers are still correct -->

1. Selecione [!UICONTROL **Migrar**].

   >[!WARNING]
   >
   >Uma mensagem de aviso na tela é exibida após você selecionar [!UICONTROL **Migrar**]. Antes de continuar, compreenda que todas as dimensões ou métricas mapeadas se aplicam a este projeto e a todos os projetos futuros em toda a organização IMS, independentemente de qual usuário está executando a migração. Esses mapeamentos podem ser atualizados ao migrar projetos futuros.

   Após a conclusão de uma migração, a página [!UICONTROL **Status da migração**] fornece um resumo do que foi migrado.

   Se a migração falhar, consulte a seção [Repetir uma migração com falha](#retry-a-failed-migration) abaixo, para obter mais informações.

1. (Opcional) Após a migração dos projetos, é possível transferir a propriedade dos projetos para qualquer usuário no Customer Journey Analytics. Para obter mais informações, consulte [Transferir ativos](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) no Guia do Customer Journey Analytics.

## Repetir uma migração com falha

Se a migração falhar, você poderá tentar novamente.

Antes de tentar novamente uma migração com falha, remova todos os [elementos sem suporte](/help/admin/tools/component-migration/prepare-component-migration.md#understand-unsupported-elements-that-cause-errors) do projeto.

>[!NOTE]
>
>Se a migração continuar a falhar após uma nova tentativa, entre em contato com o Atendimento ao cliente com a ID do projeto. Você pode encontrar a ID do projeto na página Status da migração. <!-- when does this page display? How can they get there -->

Para repetir uma migração com falha:

1. No Adobe Analytics, selecione a guia [!UICONTROL **Administrador**] e escolha [!UICONTROL **Todos os administradores**].

1. Em [!UICONTROL **Configuração e coleção de dados**], selecione [!UICONTROL **Migração de componentes**].

1. Selecione [!UICONTROL **Falha**] na coluna [!UICONTROL **Status da migração**] ao lado do projeto que você deseja tentar novamente.

   ![falha na coluna de status da migração](assets/migration-failed.png)

   A página [!UICONTROL **Status da migração**] é exibida.

   Esta página também é exibida imediatamente após a conclusão das etapas de migração descritas na seção [Migrar projetos do Adobe Analytics para o Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) acima.

1. Selecione [!UICONTROL **Repetir migração**].

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
| [!UICONTROL **Outros filtros**] | Os seguintes filtros adicionais estão disponíveis: <ul><li>[!UICONTROL **Meus**]: mostra somente projetos nos quais você está definido como proprietário.</li><li>[!UICONTROL **Compartilhado(s) comigo**]: mostra somente os projetos que foram compartilhados com você.</li><li>[!UICONTROL **Favoritos**]: mostra somente projetos que estão marcados como favoritos. (Você pode marcar um projeto como favorito da [landing page do projeto](/help/analyze/landing.md).)</li><li>[!UICONTROL **Mensal**]</li><li>[!UICONTROL **Anualmente**]</li></ul> |

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
