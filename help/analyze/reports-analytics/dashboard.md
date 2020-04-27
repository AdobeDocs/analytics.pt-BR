---
description: 'Um painel é uma coleção de relatórios miniatura chamados de reportlets. Um painel é mais útil quando contém reportlets relacionados que completam as visões gerais de aspectos específicos de seu site como, por exemplo, localizar métodos, perfis de visitantes, etc. '
subtopic: Dashboards
title: Painéis e reportlets
topic: Reports and analytics
uuid: 7a7b3bc9-0a3c-49b0-9168-e2878ae67b97
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Painéis e reportlets

Um painel é uma coleção de relatórios miniatura chamados de reportlets. Um painel é mais útil quando contém reportlets relacionados que completam as visões gerais de aspectos específicos de seu site como, por exemplo, localizar métodos, perfis de visitantes, etc. 

## Painéis e reportlets {#concept_8CD3ACA2830A4994A68A31D8773B57E0}

Um painel é uma coleção de relatórios miniatura chamados de *`reportlets`*. Um painel é mais útil quando contém reportlets relacionados que completam as visões gerais de aspectos específicos de seu site como, por exemplo, localizar métodos, perfis de visitantes, etc. 

Você pode adicionar a maioria dos relatórios de marketing a um painel, incluindo relatórios com muitos gráficos, como o [!UICONTROL Fallout Report], o [!UICONTROL Conversion Funnel Report]e o [!UICONTROL Pathfinder Report].

Você também pode configurar um painel como página inicial, compartilhar painéis com outros usuários e agendar a entrega deles. If you do not set a dashboard (or a bookmark) as a landing page, the [!UICONTROL My Recommended Reports] dashboard displays. **[!UICONTROL My Recommended Reports]** mostra o **[!UICONTROL Key Metrics]** relatório mais seus cinco relatórios exibidos com mais frequência. É dinâmico e baseia-se nos relatórios reais que são mais visualizados.

Alguns dos relatórios exibidos frequentemente podem não ser exibidos no painel, e portanto não estarão disponíveis para visualização. Dentre eles:

* Relatórios de detecção de anomalias
* Relatórios de análise de contribuição
* Relatórios de fallout
* Relatórios do pathfinder
* Relatórios em Tempo real
* Outros painéis

>[!NOTE] O **[!UICONTROL Site Overview]** painel não está mais listado em Relatórios e análises. Entretanto, ainda existem algumas circunstâncias nas quais você observará alguns ou todos os reportlets.

* If you have, say, only three frequently viewed reports, Reports &amp; Analytics will take two reports from the Site Overview dashboard to complete the **[!UICONTROL My Recommended Reports]** dashboard.
* Inicialmente, os novos conjuntos de relatórios ainda contarão com os reportlets de Visão geral do site até serem substituídos pelos relatórios exibidos frequentemente. Mesmo assim, o painel agora será chamado **[!UICONTROL My Recommended Reports]**.

Além dos painéis criados, os seguintes painéis pré-integrados são incluídos para cada usuário:

**[!UICONTROL Components]>[!UICONTROL Dashboards]>[!UICONTROL Shared Dashboards]>[!UICONTROL Local Sites]**

Esse painel personalizável oferece uma maneira de colocar reportlets no modelo fornecido.

**[!UICONTROL Components]>[!UICONTROL Dashboards]>[!UICONTROL Shared Dashboards]>[!UICONTROL Site Operations Dashboard]**

Esse painel fornece uma visão geral de métricas principais relacionadas às operações de seu site. Os relatórios nesse painel incluem:

* Páginas de saída
* Páginas mais populares
* Seções do site mais populares
* Reportlet de medição/KPI
* Reportlet de Texto
* Reportlet de Resumo da Empresa

Use the [!UICONTROL Dashboard Manager] to edit and manage dashboards, and enable them for DirectAccess.

Consulte [Gerenciamento de painéis](/help/analyze/reports-analytics/dashboard-manage.md).

## Criar um painel {#task_54EFBED59BDC4418A919E6EF84AB9CFF}

Etapas que descrevem como criar um painel.

<!-- 

t_dashboard_add.xml

 -->

Antes de adicionar um relatório (como um reportlet) a um painel, defina o layout do painel.

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Clique em **[!UICONTROL Add Dashboard]**.
1. Digite um nome para o painel.
1. Clique em **[!UICONTROL 3 x 2]** ou **[!UICONTROL 2 x 2]** para especificar quantos reportlets você deseja incluir na página do painel.
1. Configure o layout da página do painel:

   * **[!UICONTROL Add Page]**: Adiciona uma página em branco ao painel, na qual você pode arrastar o conteúdo para criar reportlets.
   * **[!UICONTROL Paper]**: Permite que você especifique um tamanho de papel, como paisagem, retrato e A4.
   * **[!UICONTROL Find Content]**: Permite que você pesquise por conteúdo nos menus [!UICONTROL Add Content] e [!UICONTROL Dashboard Contents] .

1. Adiciona o conteúdo disponível ao painel, arrastando os itens para a tela do reportlet.

   Consulte [Criação de um reportlet](/help/analyze/reports-analytics/dashboard.md#task_EC3AFBBAA51C45CEBAF632F841C305B3) e [Edição das configurações do painel](/help/analyze/reports-analytics/dashboard.md#task_90D7FAC1CC3E4DB786B4C87CC33B5459).
1. Clique em **[!UICONTROL Save.]**

   Saving a dashboard makes it available in the **[!UICONTROL Dashboard]** menu. The new dashboard is also available in the [!UICONTROL Dashboard Manager] ( **[!UICONTROL Favorites]** > **[!UICONTROL Dashboards]** > **[!UICONTROL Manager]**), where you can edit, organize, share, schedule, archive dashboards, and more. (Consulte [Gerenciamento de painéis](/help/analyze/reports-analytics/dashboard-manage.md).)

1. (Opcional) Para definir o painel como sua landing page, clique em **[!UICONTROL More Options]** > **[!UICONTROL Set as Landing Page]**.

## Criar um reportlet {#task_EC3AFBBAA51C45CEBAF632F841C305B3}

Etapas que descrevem como criar um reportlet. Depois de criar um reportlet, ele estará disponível para exibição em um painel.

<!-- 

t_dashboard_add_report.xml

 -->

1. Executar um relatório.
1. Clique em **[!UICONTROL Dashboard.]**
1. Na [!UICONTROL Add Reportlet] página, nomeie o relatório e selecione um painel de **[!UICONTROL Place in Dashboard]**.
1. (Opcional) Configure o intervalo de datas.

   * **[!UICONTROL Rolling]**: Altera a data conforme o tempo passa, de acordo com o intervalo de tempo (diário, mensal e assim por diante). Por exemplo, se hoje é 17 de janeiro, você pode definir as datas para 15-16 de janeiro. Then if you select **[!UICONTROL Rolling]**, on January 27 the reportlet displays data for January 25 - 26.
   * **[!UICONTROL Fixed]**: Impede que a data avance com o passar do tempo.

1. (Opcional) Substitua a lista de distribuição de publicação.

   **[!UICONTROL Publishing List Override]**: Se você ativar esta opção, o report suite mencionado neste reportlet será sempre usado na distribuição para uma lista de publicação. Se você desativar esta opção, o conjunto de relatórios identificado na lista de publicação substituirá o conjunto de relatórios neste reportlet.

1. Clique em **[!UICONTROL Create New]**.

   The reportlet is added to the **[!UICONTROL Dashboard Contents]** menu in the dashboard editor.

## Adicionar conteúdo a um painel {#task_90D7FAC1CC3E4DB786B4C87CC33B5459}

Etapas que descrevem como adicionar conteúdo de outros painéis e painéis compartilhados. Você também pode adicionar conteúdo a partir de qualquer fonte personalizada ou externa como, por exemplo, texto e imagens.

<!-- 

t_dashboard_content.xml

 -->

1. Abra um painel e, em seguida, clique em **[!UICONTROL Layout]** . 
1. Click **[!UICONTROL Add Content]**, then drag items to the dashboard.

   The [!UICONTROL Add Content] menu displays reportlet content from other dashboards, legacy dashboards, and shared dashboards.

   >[!NOTE]
   >
   >O limite atual para o número de páginas em um painel é 30.

   **Reportlets personalizados**

   *Conteúdo de dados:*

   * Resumo da empresa: mostra as exibições de página por vários conjuntos de relatórios e as métricas que você selecionou.
   * Parâmetro de métrica: mostra um indicador que informa onde estão suas figuras métricas em relação aos limites que você especificou.

      Você pode selecionar uma métrica, tipo de gráfico, gama de cores e os valores de limite. Se a contagem da métrica ultrapassar o limite Maior que, o medidor indicará isso no reportlet, usando a cor acima do campo Maior que. Se a contagem da métrica ultrapassar o limite Menor que, o medidor indicará isso no reportlet, usando a cor acima do campo Menor que. Os valores especificados nesses campos representam o valor contábil da métrica como, por exemplo, o número de exibições de páginas, valores em dólares, exibições do carrinho, etc. (Não use caracteres especiais).
   * Resumo de Conjunto de relatórios: exibe uma métrica selecionada e seu valor total ou valores alto e baixo de um conjunto de ferramentas de relatório.
   * Resumo de uso: mostra dados sobre o acesso da interface por pessoais em sua organização. Este reportlet pode mostrar dados de acesso por nome de usuário, acesso de relatório ou acesso ao conjunto de relatórios.
Você pode criar os seguintes reportlets de Conteúdo do usuário fornecendo URLs. Se um URL ou outro recurso de imagem não começar com https://, os usuários do Internet Explorer pode receber um aviso sobre conteúdo misto. Você pode desativar o aviso para conteúdo misto nas configurações de segurança do navegador.
   *Conteúdo do usuário*

   * Relatório externo: permite adicionar um relatório externo nos formatos .xml e .csv.
   * HTML: permite adicionar um reportlet HTML personalizado. O URL deve usar HTTP ou HTTPS. Caso contrário, você verá um erro `Specified URL could not be retrieved`. No conteúdo do documento, todas as marcas com atributos usando os protocolos dados: e javascript: serão removidos. Scripts, frames, applets, manipuladores de eventos, flash e outros objetos incorporados serão removidos. Se os recursos não forem especificados usando HTTPS, os usuários do IE receberão um aviso sobre conteúdo misto.
   * Imagem: permite criar um painel a partir de um URL da imagem. Se o URL usa o protocolo HTTP, o Internet Explorer emite um aviso de conteúdo misto. Usar um URL com HTTPS remove o aviso. Todos os outros protocolos emitem um erro `Specified URL could not be retrieved`.
   * RSS: permite adicionar um feed RSS. Deve utilizar HTTP ou HTTPS. Caso contrário, você verá um erro `Specified URL could not be retrieved`.
   * Texto: permite que você use o código XHTML para criar seus próprios dados. Use HTTP ou HTTPS para um URL. Imagens usadas no conteúdo do reportlet de texto que têm o protocolo HTTP farão com que os usuários do IE recebam um aviso sobre conteúdo misto. Imagens incluídas usando outros protocolos não serão exibidos no reportlet.
   **Meus painéis**

   Lista de seus painéis atualizados a partir da qual você pode mover o conteúdo para o novo painel.

   **Painéis legados**

   Lista de seus painéis compartilhados a partir da qual você pode mover o conteúdo para o novo painel.

   **Painéis compartilhados**

   Lista de seus painéis legados a partir da qual você pode mover o conteúdo para o novo painel. Painéis legados são úteis se você desejar preservar a formatação anterior dos painéis de versões anteriores do.

   **Conteúdo do painel**

   Exibe itens que você já adicionou ao painel.

1. Clique em **[!UICONTROL Save.]**

## Editar um painel de dados de reportlet {#task_B460CCD70D9F40FCAC6BBC1C044CC460}

Você pode alterar as configurações de dados em nível de painel ou reportlet. Por exemplo, você pode alterar ou bloquear o conjunto de relatórios, alterar datas, aplicar segmentos, etc. Também é possível personalizar um painel inserindo a declaração de confidencialidade da sua empresa e incluir dados HTML, XML, Web API e CSV em reportlets personalizados.

<!-- 

t_dashboard_edit.xml

 -->

**Para editar um painel de dados de reportlet**

1. Click **[!UICONTROL Components]** > **[!UICONTROL Dashboards]** > *dashboard name* to open a dashboard.
1. Clique em **[!UICONTROL Layout]**.

| Para | Fazer isso |
|--- |--- |
| altere conjunto de relatórios de um painel | Clique no menu no cabeçalho da Experience Cloud e, em seguida, selecione um conjunto de relatórios. |
| altere o conjunto de relatórios de um reportlet | No reportlet, clique no nome do conjunto do relatórios e, em seguida, selecione um conjunto de relatórios no menu [!UICONTROL Report Suite]. |
| Aplicar um segmento a um painel | In the Experience Cloud header, click [!UICONTROL Show Segments], then select a segment. |
| Aplicar um segmento a um reportlet | No painel, clique em Layout para editar um painel.   No reportlet, clique no nome do conjunto de relatórios, selecione um valor no campo Segmento e clique em Atualizar. |
| Bloquear um conjunto de relatórios (evita alterar o conjunto de relatórios em um reportlet) | In the reportlet, click the report suite name, then enable [!UICONTROL Lock Report Suite]. Clique Atualizar. |
| Mudar uma data de relatório | Para um painel, clique no calendário. (todos os reportlets no painel refletem a alteração de data.)<br>Para uma reportlet, clique no link da data e, em seguida, configure o calendário. |
| Dar um nome a um painel | Abra um painel e, em seguida, clique em  [!UICONTROL More] >  [!UICONTROL Rename]. |
| Visualizar um arquivo de painel | Clique em  [!UICONTROL More] >  [!UICONTROL View Archive]. |
| Definir o painel como uma página de aterrissagem | No painel, clique em  [!UICONTROL More] > [!UICONTROL Set As Landing Page]. |
| Fazer o download de um painel | In a dashboard, click  [!UICONTROL More] >  Download. |
| Imprimir um painel | In a dashboard, click  [!UICONTROL More] >  Print. |
| Salvar um painel | Em um painel, clique em Salvar como e, em seguida, especifique um nome. |

## Co-brand do painel {#task_603BDE7700B945699AF5514C2DEB81F7}

Etapas que descrevem como fazer o upload de uma imagem para exibição em um painel.

<!-- 

t_dashboard_branding.xml

 -->

1. **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]**.
1. Na [!UICONTROL Company Settings] página, clique em **[!UICONTROL Co-Brand the Adobe Experience Cloud]**.
1. Clique em **[!UICONTROL Enable Co-Branding]**.
1. Browse to upload the image, then click **[!UICONTROL Save.]**

   Para obter resultados melhores ao visualizar a imagem em um navegador, carregue uma imagem de 100px por 30px. Para obter resultados melhores na saída PDF, carregue uma imagem de 417px por 125px (300 dpi). Imagens de grandes dimensões serão reduzidas, mantendo a relação de aspecto.

## Usar segmentos com painéis {#concept_ED030C3713D54D03971FB7B209285750}

Painéis, como a maioria dos relatórios no Adobe Analytics, podem utilizar segmentos para recuperar dados desejados.

<!-- 

segments_dashboards.xml

 -->

Os segmentos podem ser aplicados em dois níveis: em um painel inteiro ou em um reportlet específico.

* **Nível de reportlet**: clique em **[!UICONTROL Layout]** e no conjunto de relatórios do reportlet que você deseja segmentar. Uma janela modal é exibida e permite adicionar ou alterar os segmentos que o reportlet usa.
* **Nível de painel**: clique no ícone Segmento na navegação esquerda, verifique os segmentos que deseja usar e clique em Aplicar. Os segmentos selecionados substituem segmentos de nível de reportlet.
