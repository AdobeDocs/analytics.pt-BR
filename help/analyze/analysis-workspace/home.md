---
description: Como começar a usar o Adobe Analytics.
keywords: Analysis Workspace
seo-description: Como começar a usar o Adobe Analytics.
seo-title: Guia de introdução
solution: Analytics
title: Guia de introdução
topic: Reports and Analytics
uuid: 851 feadb -5 e 30-45 ab -9 f 66-02 bdf 844 fa 54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

A Analysis Workspace é uma das ferramentas principais da Adobe para tomar decisões acionáveis baseadas em dados para sua organização. A visualização mais comum, a tabela de forma livre, permite que você crie relatórios personalizados com dimensões, métricas, segmentos e intervalos de datas.

## Pré-requisitos

[Envie dados para o Adobe Analytics usando o Adobe Experience Platform Launch](../../implement/implement-with-launch/validate-publish-prod.md): O uso da Analysis Workspace requer uma implementação de trabalho. Certifique-se de que a organização está enviando dados para a Adobe antes de usar a ferramenta. Outras implementações, como DTM ou implementações manuais herdadas, também podem funcionar.

## Puxar um relatório classificado básico no Workspace

Puxe um relatório classificado básico usando a Analysis Workspace. Um relatório classificado mostra uma exibição total agregada de cada valor de dimensão, mostrando os maiores valores primeiro. Esses tipos de relatórios são úteis para ver quais componentes do site são mais eficazes, como quais páginas obtêm mais tráfego ou quais produtos mais vendem.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Clique no ícone de 9-quadrado na parte superior direita e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, clique em Espaço de trabalho.
4. Clique no botão «Criar novo projeto».
5. No pop-up modal, verifique se "Projeto em branco" está selecionado e clique em Criar.
6. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Páginas (laranja colorido) e arraste-a para a tela onde ela diz "Soltar uma dimensão aqui".
7. Observe que, se o conjunto de relatórios tiver dados, um relatório que mostra as principais páginas desse mês pode ser visualizado. Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). Se você arrastar a métrica Visitas sobre Ocorrências, a métrica será substituída nos relatórios. Se você arrastar a métrica Visitas ao lado de Ocorrências, ambas as métricas serão exibidas lado a lado.
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Puxar um relatório de tendência básico no Workspace

Puxe um relatório de tendência básico usando a Analysis Workspace. Um relatório de tendências mostra uma exibição de métricas ao longo do tempo com o intervalo de datas selecionado. Esses tipos de relatórios são úteis para identificar tendências ao longo do tempo e podem ser usadas para medir o sucesso ou a falha das decisões comerciais feitas. Por exemplo, você pode observar um relatório de exibições de página com o passar do tempo para verificar se um novo design de site ajuda a aumentar ou diminuir o tráfego.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Clique no ícone de 9-quadrado na parte superior direita e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, clique em Espaço de trabalho.
4. Clique no botão «Criar novo projeto».
5. No pop-up modal, verifique se "Projeto em branco" está selecionado e clique em Criar.
6. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Exibições de página e arraste-a para o espaço pequeno na tela denominada "Soltar uma métrica aqui". Evite soltar no espaço reservado para dimensões (pelo menos para esse exercício).
7. Observe que, se o conjunto de relatórios tiver dados, você verá um relatório de exibições de página básico com tendência sobre o mês atual. A Analysis Workspace trouxe automaticamente o intervalo de datas «Dia» para que você possa ver a tendência das exibições de página do mês atual.
8. Localize o intervalo de datas Semana (roxo colorido) na lista de componentes de intervalo de datas à esquerda. Clique no título do intervalo de datas para expandir e ver todos os componentes de intervalo de datas, ou use a barra de pesquisa.
9. Arraste o intervalo de datas Semana na parte superior do cabeçalho do intervalo de datas do Dia na tela para substituí-lo.
10. Observe que o relatório de tendências agora é agregado por semana em vez de dia.
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Teste com a ferramenta

Como a Analysis Workspace é uma ferramenta de relatórios, ela não afeta a coleta de dados. Não há repercussões para arrastar os componentes indiscriminadamente para um projeto para ver o que funciona. Arraste combinações diferentes de dimensões e métricas para o projeto do espaço de trabalho para ver o que está disponível para você.

Se você arrastar acidentalmente um componente inválido para o projeto do espaço de trabalho ou voltar uma etapa, pressione ctrl + Z (Windows) ou cmd + Z (Mac) para desfazer a última ação realizada. You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## Solução de problemas

**Quando uma métrica é arrastada, ela diz "Dados inválidos".**

Dados inválidos significam que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas na parte superior não podem ser retornadas como dados, pois não há como exibir duas métricas dessa forma. Em vez disso, coloque as métricas lado a lado.

**Ao arrastar uma métrica, eu não vejo nenhum dado real - apenas zeros.**

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, há algumas coisas que você pode verificar:

* Verifique novamente o conjunto de relatórios e verifique se ele está preenchido com dados.
* Se você estiver usando um segmento em seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e certifique-se de que está configurado para um valor que você espera.
* Navegue até seu site e use o Depurador para validar que os dados estão sendo coletados.

## Recursos adicionais

* [Notas de versão do Analysis Workspace](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md): Leia os recursos mais recentes introduzidos na ferramenta.
* [Analysis Workspace no youtube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Saiba como usar a maioria dos recursos na Analysis Workspace por meio dessa extensa lista de reprodução.
* Dicas no produto: As dicas do dia, juntamente com vídeos curtos, aparecem ocasionalmente no canto inferior direito da Analysis Workspace. If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [Comunidade da Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Discuta a Analysis Workspace com outros usuários e vote os recursos que gostaria de ver na ferramenta.
* Postagens do blog:
   * [Potencializar organizações usando a análise mais inteligente](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Os novos recursos do Adobe Analytics tornam insights geniais mais acessíveis](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [Cinco dicas para maximizar sua produtividade com a Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Insights mais rápidos com a Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Por que você deve usar a Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Próximas etapas

Há muitas instruções para aprofundar a compreensão da Análise do espaço de trabalho. Estas são algumas noções básicas que a Adobe recomenda:

### Para usuários finais que desejam expandir conhecimento sobre como usar a Analysis Workspace

* [Detalhes da interface do usuário do Workspace](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): Agora que você criou um relatório básico, fique mais familiarizado com o restante da interface.
* [Visualizações no Workspace](visualizations/freeform-analysis-visualizations.md): Tabelas de forma livre são apenas um tipo de visualização na Analysis Workspace. Saiba como usar outras visualizações, como gráficos de linha, gráficos de barras e mapas geográficos.
* [Dimensões no Workspace](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Saiba mais sobre quais são as dimensões e como usá-las em mais do que apenas relatórios classificados.
* [Métricas no Workspace](../../analyze/analysis-workspace/components/apply-create-metrics.md): Saiba mais sobre quais são as métricas e como usá-las em outras partes das tabelas de forma livre.
* [Introdução à segmentação](../../analyze/analysis-workspace/components/t-freeform-project-segment.md): Saiba mais sobre quais segmentos são e puxam um relatório básico usando um segmento.
* [Intervalos de datas no Workspace](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Saiba mais sobre as datas relativas e acumuladas e use-as em projetos do espaço de trabalho.
* Compartilhamento de projetos no Workspace: Mostre ao seu colega o incrível projeto da Workspace que você criou.
* [(Avançado) Painéis no Workspace](c-panels/panels.md): Use recursos avançados no Workspace, como Atribuição e Comparação de segmentos.

### Para análises e administradores que procuram melhorar a qualidade do espaço de trabalho na organização

* [Permissões da Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html): Atribuir permissões de usuário ao Workspace por meio do Adobe Admin Console.
* [Crie um documento de design de solução](../../implement/prepare/solution-design.md): Comece a planejar como a sua organização coleta dimensões ou métricas adicionais específicas ao site.
* [Modelos no Workspace](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md): Crie modelos para que seus colegas possam começar com um espaço de projeto adaptado às suas necessidades.
* [Curadoria de espaço de trabalho](curate-share/curate.md): Criar um projeto que limita os componentes disponíveis, tornando a área de trabalho mais acessível para aqueles que estão menos familiarizados com a ferramenta