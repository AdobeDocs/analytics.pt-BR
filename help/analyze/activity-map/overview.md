---
description: Classifique a atividade do link usando sobreposições visuais para monitorar a participação do público-alvo nas páginas da Web.
title: Visão geral do Activity Map
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# Visão geral do Activity Map

O Activity Map é um recurso do Adobe Analytics que fornece uma representação visual do engajamento de usuários em páginas da web e aplicativos móveis. Ele permite que profissionais de marketing e analistas rastreiem e analisem interações do usuário, como cliques e comportamento de rolagem. O Activity Map gera mapas de calor e relatórios de sobreposição que mostram os elementos mais populares em uma página da Web, ajudando você a otimizar suas experiências digitais.

Esta seção da documentação se concentra na sobreposição do Activity Map. No entanto, há outras partes importantes para usar o Activity Map:

* **Configuração do conjunto de relatórios**: um conjunto de relatórios deve ter o Activity Map habilitado. Consulte [Relatórios do Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) nas configurações do conjunto de relatórios.
* **Implementação**: a maioria dos relatórios do Activity Map está disponível pronta para uso. No entanto, alguns sites podem exigir implementação adicional para aproveitar ao máximo o rastreamento de links. As seguintes variáveis de implementação estão disponíveis:
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md): Filtrar dados de cliques por nome de link.
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md): Filtrar dados de cliques por nome de região.
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md): Altere o atributo que preenche a dimensão Região do Activity Map.
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md): Personalize a lógica que o Activity Map usa para preencher a dimensão Link do Activity Map.
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md): Personalize a lógica que o Activity Map usa para preencher a dimensão Região do Activity Map.
* **Dimensões**: além da extensão de sobreposição, o Activity Map fornece várias dimensões que você pode usar no Analysis Workspace.
   * [Link do Activity Map](/help/components/dimensions/activity-map-link.md): o nome do link clicado.
   * [Região do Activity Map](/help/components/dimensions/activity-map-region.md): o nome da região clicada.
   * [Página do Activity Map](/help/components/dimensions/activity-map-page.md): o nome da página no momento em que o link foi clicado.
   * [Link do Activity Map por Região](/help/components/dimensions/activity-map-link-by-region.md): um valor concatenado de Link do Activity Map e Região do Activity Map.

## Recursos e benefícios

* **Visualização do engajamento do usuário**: o Activity Map oferece uma representação visual dinâmica do comportamento do usuário, permitindo que você veja exatamente onde os usuários clicam. Esses dados visuais facilitam a identificação de padrões, tendências e áreas de interesse. Em seguida, você pode tomar decisões conscientes sobre design, inserção de conteúdo e fluxo de usuários.

* **Mapas de calor**: o Activity Map gera mapas de calor que exibem as áreas mais clicadas ou interagidas de uma página da Web. Os mapas de calor usam codificação de cores para representar o nível de engajamento, permitindo que você identifique pontos de acesso e priorize a atenção a áreas de alto impacto. Essas informações podem ser valiosas para otimizar botões, links, formulários ou quaisquer outros elementos interativos do call-to-action.

* **Relatórios de sobreposição**: os relatórios de sobreposição no Activity Map fornecem métricas de clique detalhadas para elementos específicos em uma página da Web. Ao entender as taxas de click-through e os níveis de engajamento de elementos individuais, você pode ajustar as estratégias de design e conteúdo para aprimorar as experiências do usuário.

* **Análise de segmento**: você pode analisar o comportamento do usuário com base em diferentes segmentos, como fontes de tráfego, demografia ou personas. Ao segmentar os dados, você pode descobrir insights valiosos em grupos de usuários específicos, permitindo experiências personalizadas e estratégias de marketing direcionadas.

## Aplicativos práticos

* **Otimização do site**: o Activity Map ajuda a otimizar seus sites identificando elementos com baixo desempenho, melhorando a navegação e aprimorando a experiência geral do usuário. Ao analisar as interações do usuário, você pode tomar decisões orientadas por dados para simplificar os fluxos de usuários, simplificar formulários ou ajustar a inserção de conteúdo para obter o máximo impacto.

* **Otimização da taxa de conversão**: ao visualizar o engajamento do usuário e analisar as taxas de click-through, o Activity Map desempenha um papel crucial nos esforços de CRO. Você pode identificar barreiras para a conversão e experimentar com diferentes variações de design para otimizar funis de conversão, páginas de aterrissagem e processos de finalização.

* **Teste A/B**: o Activity Map pode ser combinado com testes A/B para medir o impacto das alterações de design ou conteúdo. Comparando as métricas de envolvimento entre diferentes versões de uma página da Web, é possível determinar quais variações resultam em maior engajamento do usuário, taxas de conversão ou receita.

