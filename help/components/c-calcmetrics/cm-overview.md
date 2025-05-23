---
description: Métricas calculadas e métricas calculadas avançadas são métricas personalizadas que podem ser criadas a partir de métricas existentes.
keywords: Métricas calculadas;métricas calculadas avançadas
title: Métricas calculadas e métricas calculadas avançadas
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# Métricas calculadas e métricas calculadas avançadas

Métricas calculadas e métricas calculadas avançadas são métricas personalizadas que podem ser criadas a partir de métricas existentes.

Nossas ferramentas para métricas calculadas oferecem uma maneira muito mais flexível para criar, gerenciar e preparar métricas. Elas permitem que os profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do [!DNL Analytics]. As métricas personalizadas disponíveis em cada pacote do [!DNL Analytics] são:

* Adobe [!DNL Analytics] Foundation: calculadas
* [Adobe Analytics Select](https://www.adobe.com/br/data-analytics-cloud/analytics/select.html): Calculadas + Calculadas avançadas
* [Adobe Analytics Prime](https://www.adobe.com/br/data-analytics-cloud/analytics/prime.html): Calculadas + Calculadas avançadas
* [Adobe Analytics Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html): Calculadas + Calculadas avançadas

Confira abaixo uma comparação entre os recursos de métricas calculadas e métricas calculadas avançadas:

| Opções do criador | Métricas calculadas | Métricas calculadas avançadas |
|---|---|---|
| [Tipos de formatos (decimal, hora, percentual, moeda)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sim | Sim |
| [Alterações de atribuição (padrão, linear, participação etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sim | Sim |
| [Tipos de métrica (padrão, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sim | Sim |
| Operadores básicos (adição, subtração, multiplicação, divisão) | Sim | Sim |
| [Aplicar segmentos](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | Não | Sim |
| [Funções básicas (contagem, valor absoluto, meio etc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | Não | Sim |
| [Funções avançadas (regressão, if/then, t-score etc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | Não | Sim |

## Capacidades {#section_A0A5C275B68A4D628950BBB0B1EE631F}

É possível

* Crie métricas em [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Detecção de anomalias] e [!UICONTROL Análise de contribuição].
* Criar métricas segmentadas derivadas do tempo de execução do relatório, sem precisar alterar a implementação. Essas métricas podem ser exibidas historicamente, pois se baseiam em segmentos.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://video.tv.adobe.com/v/32608?quality=12&learn=on&captions=por_br){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

* Compartilhe métricas em conjuntos de relatórios. Isso significa que todas as métricas recém-criadas se aplicam a todos os conjuntos de relatórios da mesma empresa de logon.
* (Somente métricas calculadas avançadas) Segmente nas métricas. Por exemplo, é possível criar uma métrica para “Novos visitantes” com uma contagem de pessoas para as quais esta é a primeira sessão.

* (Somente métricas calculadas avançadas) Incorpore funções estatísticas para ajudar a descrever melhor os seus dados. Por exemplo, é possível contar o número de itens em um relatório ou adicionar o número de desvios padrão para cada item.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas segmentadas em segmentos](https://video.tv.adobe.com/v/32603?quality=12&learn=on&captions=por_br){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


## Limitações {#section_CB878B02451541D68A68B508D4DBD19A}

Alguns recursos do [!DNL Analytics] permitem usar eventos, mas não permitem usar métricas calculadas:

* [!UICONTROL Fallout] na [!UICONTROL Analysis Workspace]
* [!UICONTROL Análise de coorte] na Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!DNL Analytics] for [!DNL Target]

## Ferramentas {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Esta é uma visão geral breve das ferramentas de [!UICONTROL Métricas calculadas]:

| Ferramenta | Capacidades |
|--- |--- |
| Criador de métricas calculada | <ul><li>Crie métricas calculadas e calculadas avançadas usando modelos de alocação avançados.</li><li>Adicionar segmentos em linha às fórmulas de métricas</li><li>Comparar segmentos em um mesmo relatório. É possível, por exemplo, comparar visitantes locais com visitantes internacionais.</li><li>Usar funções estatísticas</li><li>Fornecer descrições detalhadas das métricas (mostrar o que elas fazem, quando as usar e quando NÃO as usar).</li><li>Copiar definições para novas métricas</li><li>Fornecer uma visualização em linha das métricas</li><li>Definir a polaridade da métrica, que indica se ela é boa ou ruim, caso um determinado evento personalizado (métrica) aumente</li><li>Métricas de tags</li></ul> |
| Gerenciador de métricas calculadas | <ul><li>Compartilhar métricas com outras pessoas&lt;/li<li>Aprovar e preparar métricas</li><li>Organize (marque com tags) as suas métricas, para que as pessoas as possam encontrar</li><li>Excluir métricas</li><li>Renomear métricas</li></ul> |
| Painel Seletor de métricas | Permite pesquisar e adicionar/aplicar métricas ao relatório. Também é possível alterar a ordem de classificação (as opções incluem: alfabética, recomendadas, usadas com frequência, usadas recentemente). Além disso, você pode filtrar por conjuntos de relatórios para mostrar apenas as métricas criadas em um conjunto de relatórios específico.  Para acessar o seletor de métricas, clique no ícone de métricas à esquerda de um relatório.  |
| API para métricas calculadas | Parte do conjunto de APIs do Adobe Analytics 2.0. |
