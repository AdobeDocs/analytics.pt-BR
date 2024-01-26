---
title: Fluxo de trabalho de rastreamento de campanha
description: Use o Adobe Analytics para acompanhar seus esforços de marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 1%

---

# Fluxo de trabalho de rastreamento de campanha

Se a sua organização quiser acompanhar o desempenho e a taxa de cliques dos esforços de marketing, você poderá usar o processo a seguir. Cada uma dessas etapas tem seções dedicadas abaixo que contêm mais detalhes.

1. [Estabelecer um processo de geração de código de rastreamento](#establish-a-tracking-code-generation-process)
1. [Adicionar o código de rastreamento desejado ao email](#add-the-desired-tracking-code-to-the-email)
1. [Configurar ou ajustar a implementação do Adobe Analytics para incluir dados de código de rastreamento](#include-campaign-variables-in-your-implementation)
1. [Exibir os relatórios no Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) O pode ajudar a simplificar cada uma dessas etapas para agregar mais valor aos seus esforços de marketing. Entre em contato com o representante de vendas da Adobe para obter mais informações.

## Estabelecer um processo de geração de código de rastreamento

Cada organização tem necessidades diferentes para códigos de rastreamento. Algumas organizações podem ter necessidades mínimas em que os códigos de rastreamento criados manualmente são mais do que suficientes. Outras organizações podem querer mais controle sobre o rastreamento e ter vários sistemas em vigor para criar os códigos de rastreamento desejados. Se sua organização usar Google Analytics além do Adobe Analytics, sua organização pode já ter um `utm` modelo de código de rastreamento estabelecido.

Independentemente de como você optar por criar ou gerar códigos de rastreamento, ter um sistema consistente em vigor facilita muito a tarefa da organização quando você deseja agrupar códigos de rastreamento para gerar relatórios. Os códigos de rastreamento estruturados de forma consistente permitem criar [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para que você possa obter informações sobre o desempenho categórico.

## Adicionar o código de rastreamento desejado a um URL

Depois de ter o valor do código de rastreamento desejado, você pode adicioná-lo a qualquer link que publicar online, como anúncios, mídia social ou email. A adição desses códigos de rastreamento normalmente ocorre em uma sequência de consulta do link. O parâmetro de sequência de consulta usado depende dos requisitos de rastreamento da organização. Um parâmetro de sequência de consulta comum é `cid` (abreviação de ID de campanha). Algumas organizações que também usam o Google Analytics podem já ter vários parâmetros de sequência de consulta de campanha, como `utm_source`, `utm_medium`, e outros.

A adição de cadeias de caracteres de consulta a um link em um email seria semelhante ao seguinte:

```text
https://example.com?cid=EM989027
```

## Incluir variáveis de campanha na implementação

O Adobe Analytics tem um [Código de rastreamento](/help/components/dimensions/tracking-code.md) que você pode usar para medir vários esforços de marketing em sua organização. No entanto, organizações diferentes podem ter requisitos de rastreamento diferentes. É importante consultar o [Documento de design da solução](../prepare/solution-design.md) para rastrear de forma consistente os valores corretos nas variáveis certas.

Se a organização ainda não tiver configurado o rastreamento de campanha, você poderá ajustar a implementação para definir o [`campaign`](/help/implement/vars/page-vars/campaign.md) variável. Consulte a [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) para saber como coletar valores de parâmetro de sequência de consulta específicos para a implementação de sua organização.

Se sua organização coletar `utm` sequências de consulta, você pode optar por:

* Enviar tudo `utm` sequências de consulta na dimensão Código de rastreamento como valores concatenados. Você pode então usar [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para criar dimensões adicionais com foco em cada `utm` parâmetro. Esse método tem uma curva de aprendizado mais complexa, mas não usa eVars extras.
* Enviar cada `utm` sequência de consulta em um [eVar](/help/components/dimensions/evar.md). Esse método é mais simples de implementar no geral, mas requer o uso de eVars adicionais.

## Exibir os relatórios no Analysis Workspace

Depois de configurar corretamente a implementação para coletar dados do código de rastreamento, é possível exibir os relatórios no Analysis Workspace.

1. Faça logon no [Adobe Experience Cloud](https://experience.adobe.com) e selecione [!UICONTROL Adobe Analytics].
1. Criar um [Projeto do Workspace](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Na lista de componentes à esquerda, arraste o [Código de rastreamento](/help/components/dimensions/tracking-code.md) dimensão à tela do espaço de trabalho.
1. Arraste a métrica desejada, como [Visitas](/help/components/metrics/visits.md) ou [Pedidos](/help/components/metrics/orders.md) à direita da tela do espaço de trabalho.

![Relatório de rastreamento de campanha](../assets/campaign-tracking-report.png)
