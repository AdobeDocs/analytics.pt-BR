---
title: Workflow de rastreamento de campanha
description: Use o Adobe Analytics para acompanhar seus esforços de marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: c118d42667c4a1af55929834b87d148a5973bed9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Workflow de rastreamento de campanha

Se sua organização deseja rastrear o desempenho e a taxa de cliques nos esforços de marketing, você pode usar o seguinte processo. Cada uma dessas etapas tem seções dedicadas abaixo que contêm mais detalhes.

1. [Estabeleça um processo de geração de código de rastreamento](#establish-a-tracking-code-generation-process)
1. [Adicionar o código de rastreamento desejado ao email](#add-the-desired-tracking-code-to-the-email)
1. [Configurar ou ajustar a implementação do Adobe Analytics para incluir dados do código de rastreamento](#include-campaign-variables-in-your-implementation)
1. [Exibir os relatórios no Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) O pode ajudar a simplificar cada uma dessas etapas para tirar o máximo proveito de seus esforços de marketing. Entre em contato com o representante de vendas do Adobe para obter mais informações.

## Estabeleça um processo de geração de código de rastreamento

Cada organização tem necessidades diferentes para códigos de rastreamento. Algumas organizações podem ter necessidades mínimas, onde os códigos de rastreamento criados manualmente são mais do que suficientes. Outras organizações podem querer mais controle sobre o rastreamento e ter vários sistemas em vigor para criar códigos de rastreamento desejados. Se sua organização usar o Google Analytics além da Adobe Analytics, a empresa já pode ter uma `utm` modelo de código de rastreamento estabelecido.

Independentemente de como você optar por criar ou gerar códigos de rastreamento, ter um sistema consistente em vigor permite que sua organização tenha um tempo muito mais fácil quando deseja agrupar códigos de rastreamento para gerar relatórios. Códigos de rastreamento estruturados de maneira consistente permitem criar [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para que você possa obter informações sobre desempenho categórico.

## Adicionar o código de rastreamento desejado a um URL

Depois de ter o valor do código de rastreamento desejado, você pode adicioná-lo a qualquer link publicado online, como anúncios, mídia social ou email. A adição desses códigos de rastreamento normalmente ocorre em uma sequência de consulta de link. Qual parâmetro da cadeia de caracteres de consulta você usa depende dos requisitos de rastreamento de sua organização; um parâmetro comum da string de consulta é `cid` (abreviado para ID da campanha). Algumas organizações que também usam Google Analytics podem já ter vários parâmetros de sequência de consulta de campanha, como `utm_source`, `utm_medium`e outros.

Adicionar cadeias de caracteres de consulta a um link em um email seria semelhante ao seguinte:

```text
https://example.com?cid=EM989027
```

## Inclua variáveis de campanha na implementação

A Adobe Analytics tem um [Código de rastreamento](/help/components/dimensions/tracking-code.md) que você pode usar para medir vários esforços de marketing em sua organização. No entanto, organizações diferentes podem ter requisitos de rastreamento diferentes. É importante fazer referência ao relatório de [Documento de design da solução](../prepare/solution-design.md) para rastrear consistentemente os valores corretos nas variáveis certas.

Se sua organização ainda não tiver configurado o rastreamento da campanha, você poderá ajustar a implementação para definir a variável [`campaign`](/help/implement/vars/page-vars/campaign.md) variável. Consulte a [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) para saber como coletar valores de parâmetro da string de consulta específicos para a implementação da organização.

Se sua organização coletar `utm` sequências de consulta, você pode optar por:

* Enviar tudo `utm` sequências de consulta na dimensão Código de rastreamento como valores concatenados. Você pode usar [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para criar dimensões adicionais que se concentram em cada `utm` parâmetro. Esse método tem uma curva de aprendizado mais complexa, mas não usa eVars extras.
* Enviar cada `utm` sequência de consulta em um [eVar](/help/components/dimensions/evar.md). Esse método é mais simples de implementar em geral, mas requer o uso de eVars extras.

## Exibir os relatórios no Analysis Workspace

Depois de configurar corretamente a implementação para coletar os dados do código de rastreamento, você pode exibir os relatórios no Analysis Workspace.

1. Faça logon no [Adobe Experience Cloud](https://experience.adobe.com) e selecione [!UICONTROL Adobe Analytics].
1. Crie um [Projeto do Workspace](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Na lista de componentes à esquerda, arraste o [Código de rastreamento](/help/components/dimensions/tracking-code.md) à tela do espaço de trabalho.
1. Arraste a métrica desejada, como [Visitas](/help/components/metrics/visits.md) ou [Pedidos](/help/components/metrics/orders.md) ao lado direito da tela do espaço de trabalho.

![Relatório de rastreamento de campanha](../assets/campaign-tracking-report.png)
