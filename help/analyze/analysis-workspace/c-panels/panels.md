---
description: Um painel é uma coleção de tabelas e visualizações
title: Visão geral dos painéis
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: aacba26d0eb612146a9e0bf6386f9e755a9e8f07
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 49%

---

# Visão geral dos painéis

Um [!UICONTROL painel] é uma coleção de tabelas e visualizações. Você pode acessar os painéis utilizando o ícone no canto superior esquerdo do espaço de trabalho ou por meio de um [painel em branco](blank-panel.md). Os painéis são úteis para organizar projetos de acordo com períodos, conjuntos de relatórios ou caso de uso de análise.

## Tipos de painel

Os seguintes tipos de painel estão disponíveis no Analysis Workspace:

| Nome do painel | Descrição |
| --- | --- |
| [Painel em branco](blank-panel.md) | Escolha entre os painéis e visualizações disponíveis para iniciar a análise. |
| [Painel do Quick Insights](quickinsight.md) | Crie rapidamente uma tabela de forma livre e uma visualização de acompanhamento para analisar e descobrir insights mais rapidamente. |
| [Painel do Analytics for Target](a4t-panel.md) | Analisar atividades e experiências do Target no Analysis Workspace. |
| [Painel de atribuição](attribution.md) | Compare e visualize modelos de atribuição rapidamente usando qualquer dimensão e métrica de conversão. |
| [Painel de forma livre](freeform-panel.md) | Realize comparações e detalhamentos ilimitados e, em seguida, adicione visualizações para obter uma visão ampla dos dados. |
| [Painel Audiência média por minuto de mídia](average-minute-audience-panel.md) | Analise o público-alvo médio por minuto ao longo do tempo, com detalhes sobre as exibições de pico e a capacidade de detalhar e comparar. |
| [Painel de visualizadores simultâneos de mídia](media-concurrent-viewers.md) | Analise os visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de analisar e comparar. |
| [Painel Tempo gasto com a reprodução de mídia](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analise os visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de analisar e comparar. |
| [Painel de comparação de segmentos](c-segment-comparison/segment-comparison.md) | Compare rapidamente dois segmentos em todos os pontos de dados para encontrar automaticamente diferenças relevantes. |

![](assets/panel-overview.png)

[!UICONTROL Insights rápidos], [!UICONTROL Em branco] e [!UICONTROL Forma livre] painéis são ótimos locais para iniciar sua análise, enquanto [!UICONTROL Analytics for Target], [!UICONTROL Atribuição], [!UICONTROL Visualizadores simultâneos de mídia] e [!UICONTROL Comparação de segmentos] Elas se prestam a análises mais avançadas. Um botão `"+"` está disponível nos projetos para que você possa adicionar painéis em branco a qualquer momento.

O painel inicial padrão é o painel [!UICONTROL Forma livre], mas você também pode definir o [painel em branco](/help/analyze/analysis-workspace/c-panels/blank-panel.md) como padrão.

## Conjunto de relatórios {#report-suite}

Tabelas e visualizações em um painel derivam dados do [!UICONTROL conjunto de relatórios] selecionado na parte superior direita do painel. O conjunto de relatórios também determina quais componentes estão disponíveis no painel esquerdo. Em um projeto, você pode usar um ou [vários conjuntos de relatórios](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=pt-BR) dependendo dos casos de uso da análise. Para aplicar um único conjunto de relatórios a todos os painéis em um projeto, **clique com o botão direito do mouse no cabeçalho do painel > Aplicar conjunto de relatórios a todos os painéis**.

A lista dos conjuntos de relatórios é classificada de acordo com a relevância, que a Adobe define levando em conta quão recentemente e frequentemente o pacote foi usado pelo usuário atual e com que frequência o pacote é usado na organização.

![](assets/panel-report-suite.png)

## Calendário {#calendar}

O calendário do painel controla o intervalo de relatórios para tabelas e visualizações dentro de um painel.

>[!NOTE]
>Se um componente de intervalo de datas (em roxo) for usado dentro de uma tabela, uma visualização ou uma área de arrastar e soltar do painel, ele substituirá o calendário do painel.

![](assets/panel-calendar.png)

Você pode aplicar um intervalo de datas com detalhamento de minutos nas configurações avançadas do calendário do painel. Se você estiver emitindo relatórios em um intervalo de datas que abrange muitos dias, a hora de início se aplica ao primeiro dia e a hora de término se aplica ao último dia do intervalo.

## Área de arrastar e soltar {#dropzone}

A área de arrastar e soltar do painel permite aplicar filtros de segmento e de lista suspensa a todas as tabelas e visualizações em um painel. É possível aplicar um ou vários filtros a um painel.

### Filtros de segmento

Arraste e solte quaisquer segmentos do painel esquerdo na área suspensa do painel para começar a filtrá-lo. Repita esse processo para adicionar mais filtros ao painel. Os filtros são exibidos lado a lado na parte superior do painel.

![Filtro](assets/segment-filter.png)

### Filtros de segmento ad hoc

Os componentes que não são de segmentos também podem ser arrastados diretamente para a zona suspensa para criar segmentos ad hoc, economizando tempo e esforço de ter que ir para o Construtor de segmentos. Segmentos criados dessa forma são definidos automaticamente como segmentos de nível de ocorrência. Essa definição pode ser modificada clicando no ícone de informações (i) ao lado do segmento e, em seguida, no ícone de edição em forma de lápis e editando-os no Construtor de segmento.

Segmentos ad hoc são um tipo de segmento rápido e são locais ao projeto. Eles não aparecem no painel esquerdo, a menos que você os torne públicos.

Para obter mais informações consulte [Segmentos rápidos](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Segmentos suspensos estáticos

Os segmentos suspensos estáticos permitem que você interaja com os dados de forma controlada. Por exemplo, você pode adicionar um segmento suspenso para Tipos de dispositivo móvel para segmentar o painel por Tablet, Celular ou Desktop.

Segmentos suspensos estáticos também podem ser usados para consolidar vários projetos em um só. Por exemplo, se você tiver muitas versões do mesmo projeto com diferentes segmentos de País aplicados, será possível consolidar todas as versões em um único projeto e adicionar um segmento suspenso de País.

![](assets/dropdown-filter-intro.png)

#### Criar segmentos suspensos estáticos

* Para segmentos suspensos usando itens de dimensão, selecione uma única dimensão no painel esquerdo e solte-a na área suspensa do painel **ao manter`[Shift]`**. Isso cria um segmento suspenso com todos os itens de dimensão associados a essa dimensão.

  Ou, se quiser que o segmento suspenso inclua apenas itens de dimensão específicos associados a uma dimensão, clique no ícone de seta para a direita ao lado da dimensão desejada no painel esquerdo. Essa ação expõe todos os itens de dimensão disponíveis. Selecione vários itens de dimensão dessa lista usando `[Shift + Click]` ou `[Ctrl + Click]`, em seguida, solte-os na área suspensa do painel **ao manter** `[Shift]`.

* Para segmentos suspensos que usam um único tipo de componente (por exemplo, somente dimensões ou somente segmentos ou somente métricas), selecione vários itens do mesmo tipo no painel esquerdo usando `[Shift + Click]` ou `[Ctrl + Click]`, em seguida, solte-os na área suspensa do painel **ao manter`[Shift]`**.

  Um único segmento suspenso é criado com componentes selecionados.

* Para segmentos suspensos usando uma combinação de tipos de componentes (como 2 métricas e 3 filtros), selecione vários componentes usando `[Shift + Click]` ou `[Ctrl + Click]`. Solte o item selecionado na zona de destino do painel **enquanto mantém a tecla`[Shift]`** pressionada. Nesse contexto, todos os tipos de componentes são tratados como segmentos suspensos separados. Por exemplo, se você incluir métricas e itens de dimensão na seleção, dois segmentos suspensos separados serão criados: um segmento suspenso inclui itens de dimensão e o outro inclui métricas.

  ![A janela Painel com o campo Segmento de cliente móvel disponível para soltar um segmento suspenso estático. ](assets/create-dropdown.png)

Clicar com o botão direito do mouse em um segmento suspenso fornece as seguintes opções:

* **[!UICONTROL Menu suspenso Excluir]**: remove o segmento suspenso do painel.
* **[!UICONTROL Excluir rótulo]**: remova o texto acima de um segmento suspenso. Para modificar o rótulo, selecione o ícone de lápis.
* **[!UICONTROL Adicionar rótulo]**: quando você adiciona um segmento suspenso a um projeto, um rótulo é automaticamente definido para o nome do componente. Se você excluir o rótulo, poderá adicioná-lo novamente com essa opção.
* **[!UICONTROL Exigir seleção]**: exige que um segmento seja definido no painel.

[Assista ao vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=pt-BR) para saber mais sobre como adicionar filtros suspensos ao seu projeto.

#### Usar segmentos suspensos estáticos

Use o menu suspenso de segmentos de qualquer uma das seguintes maneiras para filtrar o painel:

* Aplique um único segmento ao painel selecionando o segmento no menu suspenso.

* Aplique vários segmentos ao painel selecionando mais de um segmento no menu suspenso. O painel é filtrado para incluir qualquer um dos segmentos selecionados.

  Para remover um segmento da lista, selecione-o novamente no menu suspenso.

  ![Selecionar vários segmentos](assets/dropdown-filter-multiselect.png)

### Segmentos suspensos dinâmicos

Os segmentos suspensos dinâmicos permitem determinar os valores disponíveis com base nos dados dentro do intervalo de relatórios do painel e nos valores em outros segmentos suspensos. Por exemplo, você pode criar dois menus suspensos dinâmicos usando a [Países](/help/components/dimensions/countries.md) dimensão e [Cidades](/help/components/dimensions/cities.md) dimensão. Quando você selecionar um país na lista [!UICONTROL Países] lista suspensa, a variável [!UICONTROL Cidades] lista suspensa se ajusta dinamicamente para mostrar apenas as cidades nesse país.

Esse mesmo conceito se aplica a todas as dimensões; somente os itens de dimensão que aparecem no intervalo de datas do painel e nos segmentos selecionados são visíveis. Os itens de Dimension selecionados nos segmentos suspensos estáticos afetam os valores disponíveis nos segmentos suspensos dinâmicos. No entanto, o inverso não é verdadeiro; os itens de Dimension selecionados em segmentos suspensos dinâmicos não afetam os valores disponíveis em segmentos suspensos estáticos.

A seleção manual de itens de dimensão estará disponível se você antecipar que um determinado item de dimensão será coletado no futuro. Você também pode apagar um segmento suspenso dinâmico para que ele não contenha um valor, permitindo que outros segmentos suspensos dinâmicos contenham mais valores. Selecionar **[!UICONTROL Redefinir tudo]** para limpar a seleção de todos os segmentos suspensos desse painel.

Para criar um segmento suspenso dinâmico:

* Arraste e solte uma única dimensão na zona de destino do painel **enquanto mantém a tecla`[Shift]`** pressionada.
* Os segmentos suspensos dinâmicos não estão disponíveis para métricas, segmentos ou intervalos de datas.
* Clique com o botão direito em um segmento suspenso e selecione **[!UICONTROL Excluir lista suspensa]** para excluí-lo.

Clicar com o botão direito em um filtro suspenso dinâmico fornece as mesmas opções que os filtros suspensos estáticos.

## Clique com o botão direito do mouse no menu {#right-click}

Algumas funcionalidades adicionais para painéis são disponibilizadas ao clicar com o botão direito do mouse no cabeçalho do painel.

![Clique com o botão direito do mouse no menu](assets/right-click-menu.png)

As seguintes configurações estão disponíveis:

| Configuração | Descrição |
| --- | --- |
| Inserir visualização/painel copiado | Permite colar (“inserir”) um painel ou visualização copiada em outro lugar no projeto ou em um projeto diferente. |
| Copiar painel | Permite clicar com o botão direito do mouse e copiar um painel, para que você possa inseri-lo em outro lugar no projeto ou em um projeto diferente. |
| Aplicar o conjunto de relatórios a todos os painéis | Permite aplicar o conjunto de relatórios do painel principal a todos os painéis do projeto. |
| Duplicar o painel | Cria uma duplicata exata do painel atual, que você pode modificar. |
| Recolher/expandir todos os painéis | Recolhe e expande todos os painéis do projeto. |
| Recolher/Expandir todas as visualizações no painel | Recolhe e expande todas as visualizações no painel atual. |
| Editar descrição | Adicione (ou edite) uma descrição de texto para o painel. |
| Obter link do painel | Permite direcionar alguém a um painel específico em um projeto. Quando o link for clicado, o destinatário será solicitado a fazer logon antes de ser direcionado para o painel exato que está vinculado. |
