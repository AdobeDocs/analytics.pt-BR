---
description: Classifique a atividade do link usando sobreposições visuais para monitorar o engajamento do público-alvo nas páginas da Web.
title: Visão geral do Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: a7670fcda3e8e6af0c036c8b263746e142278255
workflow-type: ht
source-wordcount: '623'
ht-degree: 100%

---

# Visão geral do Activity Map

O Activity Map é um recurso do Adobe Analytics que fornece uma representação visual do engajamento de usuários em páginas da web e aplicativos móveis. Permite que profissionais de marketing e analistas rastreiem e analisem interações do usuário, como cliques e comportamento de rolagem. O Activity Map gera mapas de calor e relatórios de sobreposição que mostram os elementos mais populares em uma página da Web, ajudando você a otimizar suas experiências digitais.

O Activity Map como conceito é composto por vários componentes importantes:

* **Configuração do conjunto de relatórios**: um conjunto de relatórios deve ter o Activity Map habilitado para que você possa começar a usá-lo. Consulte [Relatórios do Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) nas configurações do conjunto de relatórios.
* **Implementação**: a maioria dos relatórios do Activity Map está disponível pronta para uso. No entanto, alguns sites podem exigir implementação adicional para aproveitar ao máximo o rastreamento de link. As seguintes variáveis de implementação estão disponíveis:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): filtra dados de cliques por nome de link.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): filtra dados de cliques por nome de região.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): altera o atributo que preenche a dimensão Região do Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): personaliza a lógica que o Activity Map usa para preencher a dimensão Link do Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): personaliza a lógica que o Activity Map usa para preencher a dimensão Região do Activity Map.
* **Sobreposição**: uma extensão de navegador que permite ver os dados de cliques sobrepostos no site. Consulte [Interface de extensão do Activity Map](overlay/overview.md) para obter mais informações. Este recurso não está disponível para implementações do SDK da web.
* **Dimensões**: além da extensão de sobreposição, o Activity Map fornece várias dimensões que você pode usar no Analysis Workspace.
   * [Link do Activity Map](/help/components/dimensions/activity-map-link.md): o nome do link clicado.
   * [Região do Activity Map](/help/components/dimensions/activity-map-region.md): o nome da região clicada.
   * [Página do Activity Map](/help/components/dimensions/activity-map-page.md): o nome da página no momento em que o link foi clicado.
   * [Link do Activity Map por região](/help/components/dimensions/activity-map-link-by-region.md): um valor concatenado de link do Activity Map e região do Activity Map.

## Recursos e benefícios

* **Visualização do engajamento do usuário**: o Activity Map oferece uma representação visual dinâmica do comportamento do usuário, permitindo que você veja exatamente onde os usuários clicam. Esses dados visuais facilitam a identificação de padrões, tendências e áreas de interesse. Em seguida, você pode tomar decisões embasadas sobre design, inserção de conteúdo e fluxo de usuários.

* **Mapas de calor**: o Activity Map gera mapas de calor que exibem as áreas com mais cliques ou interações em uma página da web. Os mapas de calor usam uma codificação por cores para representar o nível de engajamento, permitindo identificar pontos relevantes e priorizar áreas de alto impacto. Essas informações podem ser inestimáveis para otimizar botões de chamada para ação, links, formulários ou quaisquer outros elementos interativos.

* **Relatórios de sobreposição**: os relatórios de sobreposição no Activity Map fornecem métricas de cliques detalhadas para elementos específicos em uma página da web. Ao entender as taxas de cliques e os níveis de engajamento de cada elemento, você pode refinar as estratégias de design e conteúdo para aprimorar a experiência do usuário. Este recurso não está disponível para implementações do SDK da web.

* **Análise de segmento**: você pode analisar o comportamento do usuário com base em diferentes segmentos, como fontes de tráfego, demografia ou personas. Ao segmentar os dados, você pode descobrir informações valiosas sobre grupos de usuários específicos, possibilitando experiências personalizadas e estratégias de marketing direcionadas.

## Aplicações práticas

* **Otimização do site**: o Activity Map ajuda a otimizar os sites, identificando elementos de baixo desempenho, melhorando a navegação e aprimorando a experiência geral do usuário. Ao analisar as interações de usuários, é possível tomar decisões orientadas por dados para simplificar fluxos de usuários e formulários ou ajustar a inserção de conteúdo para obter o impacto máximo.

* **Otimização do índice de conversão**: ao visualizar o engajamento de usuários e analisar as taxas de cliques, o Activity Map desempenha um papel crucial nos esforços de CRO. É possível identificar barreiras para a conversão e experimentar com diferentes variações de design para otimizar funis de conversão, páginas de destino e processos de check-out.

* **Teste A/B**: o Activity Map pode ser combinado com testes A/B para medir o impacto das alterações de design ou conteúdo. Ao comparar as métricas de engajamento entre diferentes versões de uma página da web, é possível determinar quais variações resultam em maior engajamento de usuários, índices de conversão ou receita.

