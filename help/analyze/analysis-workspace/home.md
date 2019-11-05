---
description: Como começar a usar o Adobe Analytics.
keywords: Analysis Workspace
seo-description: Como começar a usar o Adobe Analytics.
seo-title: Guia de introdução
solution: Analytics
title: Guia de introdução
topic: Reports and Analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analysis Workspace

A Analysis Workspace é uma das principais ferramentas da Adobe para tomar decisões acionáveis baseadas em dados para sua organização. A visualização mais comum, a tabela de forma livre, permite que você crie relatórios personalizados usando dimensões, métricas, segmentos e intervalos de datas.

## Pré-requisitos

[Envie dados para o Adobe Analytics usando o Adobe Experience Platform Launch](/help/implement/implement-with-launch/validate-publish-prod.md): O uso da Analysis Workspace requer uma implementação de trabalho. Verifique se sua organização está enviando dados para a Adobe antes de usar a ferramenta. Outras implementações, como DTM ou implementações manuais herdadas, também podem funcionar.

## Puxar um relatório classificado básico no Workspace

Puxe um relatório classificado básico usando a Analysis Workspace. Um relatório classificado mostra uma exibição total agregada de cada valor de dimensão, mostrando primeiro os maiores valores. Esses tipos de relatórios são úteis para ver quais componentes do site são mais eficazes, como quais páginas recebem mais tráfego ou quais produtos mais vendem.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, clique em Espaço de trabalho.
4. Clique no botão 'Criar novo projeto'.
5. No pop-up modal, verifique se "Projeto em branco" está selecionado e clique em Criar.
6. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Páginas (laranja colorido) e arraste-a para a tela onde ela diz 'Soltar uma dimensão aqui'.
7. Observe que se o conjunto de relatórios tiver dados, um relatório mostrando as principais páginas deste mês poderá ser visto. A Analysis Workspace preencheu automaticamente o relatório com a métrica [Ocorrências](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Localize a métrica Visitas (verde colorido) e arraste-a **sobre** ou **ao lado** do cabeçalho da métrica Ocorrências (evite colocá-la acima da métrica). Se você arrastar a métrica Visitas para cima de Ocorrências, a métrica será substituída no relatório. Se você arrastar a métrica Visitas ao lado de Ocorrências, ambas as métricas serão exibidas lado a lado.
9. Se você quiser salvar seu projeto, clique em *[!UICONTROL Projeto]&gt;[!UICONTROL Salvar]* no menu superior esquerdo.

## Puxar um relatório básico de tendências no Workspace

Puxe um relatório de tendências básico usando a Analysis Workspace. Um relatório de tendências mostra uma exibição ao longo do tempo das métricas usando o intervalo de datas selecionado. Esses tipos de relatórios são úteis para identificar tendências ao longo do tempo e podem ser usados para medir o sucesso ou a falha das decisões de negócios tomadas. Por exemplo, você pode observar um relatório de exibições de página com tendência ao longo do tempo para ver se um novo design de site ajudou a aumentar ou diminuir o tráfego.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
2. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
3. Na barra de navegação superior, clique em Espaço de trabalho.
4. Clique no botão 'Criar novo projeto'.
5. No pop-up modal, verifique se "Projeto em branco" está selecionado e clique em Criar.
6. À esquerda, você deve ver uma lista de dimensões, métricas, segmentos e intervalos de datas. Localize a dimensão Exibições de página e arraste-a para o pequeno espaço na tela rotulada como 'Soltar uma métrica aqui'. Evite soltá-lo no espaço reservado para dimensões (pelo menos para este exercício).
7. Observe que se o conjunto de relatórios tiver dados, você deverá ver um relatório básico de exibições de página com tendência ao longo do mês atual. A Analysis Workspace trouxe automaticamente o intervalo de datas "Dia" para que você possa ver a tendência das exibições de página do mês atual.
8. Localize o intervalo de datas Semana (roxo colorido) na lista de componentes do intervalo de datas à esquerda. Clique no título do intervalo de datas para expandir e ver todos os componentes do intervalo de datas, ou use a barra de pesquisa.
9. Arraste o intervalo de datas Semana na parte superior do cabeçalho do intervalo de datas Dia na tela para substituí-lo.
10. Observe que seu relatório de tendências agora é agregado por semana em vez de dia.
11. Se você quiser salvar seu projeto, clique em *[!UICONTROL Projeto]&gt;[!UICONTROL Salvar]* no menu superior esquerdo.

## Experimente com a ferramenta

Como a Analysis Workspace é uma ferramenta de relatório, ela não tem impacto na coleta de dados. Não há repercussão em arrastar indiscriminadamente componentes para um projeto para ver o que funciona. Arraste diferentes combinações de dimensões e métricas para o projeto da área de trabalho para ver o que está disponível.

Se você arrastar acidentalmente um componente inválido para o projeto do seu espaço de trabalho ou quiser voltar uma etapa, pressione ctrl+Z (Windows) ou cmd+Z (Mac) para desfazer a última ação realizada. Você também pode começar com uma tabulação limpa clicando em *[!UICONTROL Projeto]&gt;[!UICONTROL Novo]* no menu superior esquerdo.

## Solução de problemas

**Quando eu arrasto uma métrica, ela diz "Dados inválidos".**

Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem ser retornadas como dados, pois não há como exibir duas métricas dessa forma. Em vez disso, coloque as métricas lado a lado.

**Quando eu arrasto uma métrica, eu não vejo nenhum dado real - apenas zeros.**

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, há alguns itens que você pode verificar:

* Verifique novamente o conjunto de relatórios e verifique se ele está preenchido com dados.
* Se você estiver usando um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e certifique-se de que esteja definido como um valor que você esperaria.
* Navegue até seu site e use o Depurador para validar se os dados estão sendo coletados.

## Recursos adicionais

* [Notas](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)de versão da Analysis Workspace: Leia os recursos mais recentes introduzidos na ferramenta.
* [Analysis Workspace no YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Saiba mais sobre como usar a maioria dos recursos na Analysis Workspace por meio dessa lista de reprodução abrangente.
* Dicas do produto: Dicas do dia, juntamente com vídeos curtos, aparecem ocasionalmente no canto inferior direito da Analysis Workspace. Se essas dicas forem descartadas, elas poderão ser acessadas por meio de *[!UICONTROL Ajuda]&gt;[!UICONTROL Dicas]* a qualquer momento.
* [Comunidade](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)da Analysis Workspace: Discuta a Analysis Workspace com outros usuários e vote nos recursos que você gostaria de ver na ferramenta.
* Postagens no blog:
   * [Potencializar organizações usando a análise mais inteligente](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Os novos recursos do Adobe Analytics tornam insights geniais mais acessíveis](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [Cinco dicas para maximizar sua produtividade com a Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Insights mais rápidos com a Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Por que você deve usar a Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Próximas etapas

Há muitas direções a seguir para aprofundar sua compreensão da Analysis Workspace. Estas são algumas das noções básicas recomendadas pela Adobe:

### Para usuários finais que desejam expandir o conhecimento sobre como usar a Analysis Workspace

* [Detalhes da interface do usuário](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)do Workspace: Agora que você criou um relatório básico, familiarize-se com o resto da interface.
* [Visualizações no Workspace](visualizations/freeform-analysis-visualizations.md): Tabelas de forma livre são apenas um tipo de visualização na Analysis Workspace. Saiba como usar outras visualizações, como gráficos de linha, gráficos de barra e mapas geográficos.
* [Dimensões no Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Saiba mais sobre quais dimensões são e como usá-las em mais do que apenas relatórios classificados.
* [Métricas no Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Saiba mais sobre quais métricas são e como usá-las em outras partes de tabelas de forma livre.
* [Introdução à segmentação](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Saiba mais sobre quais segmentos são e obtenha um relatório básico usando um segmento.
* [Intervalos de datas no Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Saiba mais sobre datas relativas e acumuladas e use-as em projetos de espaço de trabalho.
* Compartilhamento de projetos no Workspace: Mostre ao seu colega o incrível projeto da Workspace que você criou.
* [(Avançado) Painéis no Workspace](c-panels/panels.md): Use recursos avançados no Workspace, como Atribuição e Comparação de segmentos.

### Para analistas e administradores que buscam melhorar a qualidade do espaço de trabalho em sua organização

* [Permissões](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)da Analysis Workspace: Atribua aos usuários permissões ao Workspace por meio do Adobe Admin Console.
* [Criar um documento](/help/implement/prepare/solution-design.md)de design de solução: Comece a planejar como sua organização coleta dimensões ou métricas adicionais específicas do site.
* [Modelos no Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Crie modelos para que seus colegas possam começar com um espaço de projeto adaptado às suas necessidades.
* [Curadoria](curate-share/curate.md)do espaço de trabalho: Crie um projeto que limite os componentes disponíveis, tornando o espaço de trabalho mais acessível para os menos familiarizados com a ferramenta
