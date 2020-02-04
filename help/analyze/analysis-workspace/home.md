---
description: Introdução ao Adobe Analytics.
keywords: Analysis Workspace
title: Guia de Introdução
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Analysis Workspace

O Analysis Workspace é uma das principais ferramentas da Adobe para que a sua organização tome decisões acionáveis baseadas em dados. A visualização mais comum, a tabela de forma livre, permite que você crie relatórios personalizados usando dimensões, métricas, segmentos e intervalos de datas.

## Pré-requisitos

[Enviar dados para o Adobe Analytics usando o Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): o uso do Analysis Workspace requer uma implementação em funcionamento. Verifique se sua organização está enviando dados para a Adobe antes de usar a ferramenta. Outras implementações, como o Gerenciamento dinâmico de tags (DTM) ou implementações manuais herdadas, também podem funcionar.

## Obter um relatório classificado básico no Workspace

É possível obter um relatório classificado básico usando o Analysis Workspace. Os relatórios classificados incluem uma exibição total agregada de cada valor de dimensão, mostrando primeiro os maiores valores. Esse tipo de relatório é útil para ver quais componentes do site são mais eficazes, quais páginas recebem mais tráfego ou quais produtos vendem mais.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, clique em Workspace.
4. Clique no botão “Criar novo projeto”.
5. No pop-up modal, verifique se “Projeto em branco” está selecionado e clique em Criar.
6. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Páginas (em laranja) e arraste-a para a tela que diz “Solte uma dimensão aqui”.
7. Observe que, se o conjunto de relatórios tiver dados, você poderá ver um relatório com as principais páginas deste mês. O Analysis Workspace preenche o relatório automaticamente com a métrica [Ocorrências](/help/components/c-variables/c-metrics/metrics-occurrences.md).
8. Localize a métrica Visitas (em verde), arraste-a e solte **sobre** ou **ao lado** do cabeçalho da métrica Ocorrências (evite colocá-la acima da métrica). Se você arrastar a métrica Visitas e soltá-la acima de Ocorrências, a métrica será substituída no relatório. Se você arrastar a métrica Visitas e soltá-la ao lado de Ocorrências, ambas as métricas serão exibidas lado a lado.
9. Para salvar seu projeto, clique em *[!UICONTROL Projeto] > [!UICONTROL Salvar]* no menu superior esquerdo.

## Obter relatório de tendências básico no Workspace

É possível obter um relatório de tendências básico usando o Analysis Workspace. Os relatórios de tendências incluem uma exibição das métricas ao longo do tempo usando o intervalo de datas selecionado. Esse tipo de relatório é útil para identificar tendências ao longo do tempo e podem ser usados para medir o sucesso ou a falha das decisões comerciais tomadas. Por exemplo, você pode analisar a tendência de um relatório de exibições de página ao longo do tempo para ver se um novo design de site ajudou a aumentar ou diminuir o tráfego.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, clique em Workspace.
4. Clique no botão “Criar novo projeto”.
5. No pop-up modal, verifique se “Projeto em branco” está selecionado e clique em Criar.
6. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Exibições de página e arraste-a para o pequeno espaço na tela com o rótulo “Solte uma métrica aqui”. Evite soltá-la no espaço reservado para dimensões (pelo menos neste exercício).
7. Observe que, se o conjunto de relatórios tiver dados, você deve ver as tendências de um relatório básico de exibições de página do mês atual. O Analysis Workspace inclui o intervalo de datas “Dia” de modo automático para que você possa ver a tendência das exibições de página do mês atual.
8. Localize o intervalo de datas Semana (em roxo) na lista de componentes do intervalo de datas à esquerda. Clique no título do intervalo de datas para expandir e ver todos os componentes do intervalo de datas, ou use a barra de pesquisa.
9. Arraste o intervalo de datas Semana e solte-o acima do cabeçalho do intervalo de datas Dia na tela para substituí-lo.
10. Observe que seu relatório de tendências agora é agregado por semana em vez de por dia.
11. Para salvar seu projeto, clique em *[!UICONTROL Projeto] > [!UICONTROL Salvar]* no menu superior esquerdo.

## Experimentar com a ferramenta

Como o Analysis Workspace é uma ferramenta de relatórios, ela não exerce impacto na coleta de dados. Se você arrastar componentes indiscriminadamente para um projeto para ver o que acontece, não haverá nenhuma repercussão. Arraste diferentes combinações de dimensões e métricas para o projeto do seu espaço de trabalho para ver o que está disponível.

Se você arrastar acidentalmente um componente inválido para o projeto do seu espaço de trabalho ou quiser voltar uma etapa, pressione ctrl+Z (Windows) ou cmd+Z (Mac) para desfazer a última ação realizada. Você também pode começar com uma tabulação limpa clicando em *[!UICONTROL Projeto] > [!UICONTROL Novo]* no menu superior esquerdo.

## Solução de problemas

**Quando eu arrasto uma métrica, vejo “Dados inválidos”.**

Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado.

**Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros.**

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, você pode realizar as seguintes verificações:

* Verifique novamente o conjunto de relatórios e veja se ele está preenchido com dados.
* Se você estiver usando um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e certifique-se de que esteja definido como um valor que você esperaria.
* Acesse seu site e use o Depurador para verificar se os dados estão sendo coletados.

## Recursos adicionais

* [Notas de versão do Analysis Workspace](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md): leia os recursos mais recentes introduzidos na ferramenta.
* [Analysis Workspace no YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): saiba mais sobre como usar a maioria dos recursos do Analysis Workspace acessando essa lista de reprodução abrangente.
* Dicas dentro do produto: dicas do dia, juntamente com vídeos curtos, aparecem ocasionalmente no canto inferior direito do Analysis Workspace. Se essas dicas forem descartadas, elas poderão ser acessadas em *[!UICONTROL Ajuda] > [!UICONTROL Dicas]* a qualquer momento.
* [Comunidade do Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): fale sobre o Analysis Workspace com outros usuários e vote nos recursos que você gostaria de ver na ferramenta.
* Publicações no blog:
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [New Adobe Analytics Capabilities Make Powerful Insights More Accessible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Faster Insights with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Why You Should Be Using Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Próximas etapas

Há muitas direções a seguir para aprofundar sua compreensão do Analysis Workspace. Estas são algumas das noções básicas recomendadas pela Adobe:

### Para usuários finais que desejam expandir o conhecimento sobre como usar o Analysis Workspace

* [Detalhes da interface do usuário do Workspace](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): agora que você criou um relatório básico, familiarize-se com o resto da interface.
* [Visualizações no Workspace](visualizations/freeform-analysis-visualizations.md): as tabelas de forma livre são apenas um tipo de visualização do Analysis Workspace. Saiba como usar outras visualizações, como gráficos de linhas, gráficos de barras e mapas geográficos.
* [Dimensões no Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): saiba mais sobre as dimensões e como usá-las além dos relatórios classificados.
* [Métricas no Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): saiba mais sobre as métricas e como usá-las em outras partes das tabelas de forma livre.
* [Introdução à segmentação](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): saiba mais sobre segmentos e obtenha um relatório básico usando um segmento.
* [Intervalos de datas no Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): saiba mais sobre datas relativas e datas do acumulado e use-as em projetos do Workspace.
* Compartilhamento de projetos no Workspace: mostre aos colegas o projeto do Workspace que você criou.
* [(Avançado) Painéis no Workspace](c-panels/panels.md): use recursos avançados no Workspace, como Atribuição e Comparação de segmentos.

### Para analistas e administradores que buscam melhorar a qualidade do espaço de trabalho em sua organização

* [Permissões do Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html): atribua permissões do Workspace aos usuários com o Admin Console da Adobe.
* [Criar um documento com uma solução de design](/help/implement/prepare/solution-design.md): comece a planejar como sua organização coleta dimensões ou métricas adicionais específicas do site.
* [Modelos no Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): crie modelos para que seus colegas possam começar com um espaço de projeto adaptado às suas necessidades.
* [Curadoria no Workspace](curate-share/curate.md): crie um projeto e limite os componentes disponíveis, tornando o espaço de trabalho mais acessível para os menos familiarizados com a ferramenta.
