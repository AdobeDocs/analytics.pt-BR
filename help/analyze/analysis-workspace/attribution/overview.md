---
title: Visão geral da atribuição
description: Saiba mais sobre o conceito de atribuição de crédito de um evento bem-sucedido a vários itens de dimensão.
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 81%

---

# Visão geral da atribuição

A atribuição oferece aos analistas a capacidade de personalizar como os itens de dimensão recebem crédito por eventos bem-sucedidos. Por exemplo:

1. Um visitante do site clica em um link de pesquisa pago para uma de suas páginas de produtos. Eles adicionam o produto ao carrinho, mas não o compram.
2. No dia seguinte, eles veem uma postagem de mídia social de um de seus amigos, clicam no link e concluem a compra.

Em alguns relatórios, você pode desejar que a ordem seja atribuída à pesquisa paga. Em outros relatórios, você pode desejar que a ordem seja atribuída ao Social. A atribuição permite controlar esse aspecto dos relatórios. Ele está disponível para todas as organizações no Adobe Analytics Ultimate, Prime, Select e Foundation. Se você não tem certeza do tipo de contrato que tem com a Adobe, entre em contato com a equipe de contas da Adobe da sua organização.

## Valor de atribuição

A jornada do cliente não é linear e é muitas vezes imprevisível. Cada cliente atua no seu ritmo e com frequência voltam, param, reiniciam ou adotam outros comportamentos não lineares. Essas ações orgânicas dificultam a identificação do impacto dos esforços de marketing na jornada do cliente. Também dificultam os esforços para unir vários canais de dados.

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

O Adobe Analytics aprimora a atribuição ao permitir:

* Definir a atribuição além da mídia paga: qualquer dimensão, métrica, canal ou evento pode ser aplicado a modelos (por exemplo: pesquisa interna), não apenas campanhas de marketing.
* Use comparação ilimitada de modelos de atribuição: compare dinamicamente quantos modelos desejar.
* Evitar alterações de implementação: com processamento de tempo de relatório e sessões contextuais, o contexto da jornada do cliente pode ser incorporado e aplicado no tempo de execução.
* Criar a sessão que melhor corresponde ao seu cenário de atribuição.
* Detalhar atribuições por segmentos: compare facilmente o desempenho dos canais de marketing em segmentos importantes (por exemplo: novos clientes e clientes recorrentes, produto X e produto Y, nível de fidelidade ou CLV).
* Inspecionar canais cruzados e análises de multitoque: usando diagramas e histogramas de Venn e resultados de atribuição de tendência.
* Analisar visualmente as principais sequências de marketing: explore visualmente caminhos que levaram à conversão usando as visualizações de fluxo de múltiplos nós e de fallout.
* Criar métricas calculadas: use a quantidade de métodos de alocação de atribuição que desejar.

## Recursos

A atribuição compreende os seguintes recursos:

* [Painel de atribuição](../c-panels/attribution.md): pegue qualquer dimensão e métrica e compare-a rapidamente com diferentes modelos de atribuição.
* [Aplicar atribuição a uma métrica](../visualizations/freeform-table/column-row-settings/column-settings.md): use uma atribuição não padrão em qualquer métrica em um projeto.
* [Aplicar atribuição a um detalhamento](../components/dimensions/t-breakdown-fa.md): use uma atribuição não padrão em um detalhamento.
* [Comparar modelos de atribuição](../components/apply-create-metrics.md): veja rapidamente como os diferentes modelos de atribuição são comparados para qualquer métrica.

## Vídeos


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Atribuição em tabelas de forma livre](https://video.tv.adobe.com/v/23136?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Atribuição em métricas calculadas](https://video.tv.adobe.com/v/23140?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Usando o painel Atribuição](https://video.tv.adobe.com/v/23139?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adicionando comparações lado a lado de modelos de atribuição](https://video.tv.adobe.com/v/23651?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Ferramentas do Adobe Analytics que não oferecem suporte para atribuição

Qualquer ferramenta que não seja compatível com a API do Analytics 2.0, como o [Report Builder herdado](/help/analyze/legacy-report-builder/home.md), não será compatível com a Atribuição.
