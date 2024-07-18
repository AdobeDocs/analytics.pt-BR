---
title: Fluxo de trabalho de rastreamento de campanha
description: Use o Adobe Analytics para rastrear seus esforços de marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 100%

---

# Fluxo de trabalho de rastreamento de campanha

Se a sua organização quiser rastrear o desempenho e o índice de click-through dos esforços de marketing, você poderá usar o processo a seguir. Cada uma dessas etapas tem seções dedicadas abaixo que contêm mais detalhes.

1. [Estabelecer um processo de geração de código de rastreamento](#establish-a-tracking-code-generation-process)
1. [Adicionar o código de rastreamento desejado ao email](#add-the-desired-tracking-code-to-the-email)
1. [Configurar ou ajustar a implementação do Adobe Analytics para incluir dados de código de rastreamento](#include-campaign-variables-in-your-implementation)
1. [Exibir os relatórios no Analysis Workspace](#view-the-reports-in-analysis-workspace)

O [Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) pode ajudar a simplificar cada uma dessas etapas para agregar mais valor aos seus esforços de marketing. Entre em contato com o(a) representante de vendas da Adobe para obter mais informações.

## Estabelecer um processo de geração de código de rastreamento

Cada organização tem necessidades diferentes de códigos de rastreamento. Algumas organizações podem ter necessidades mínimas e, nesses casos, os códigos de rastreamento criados manualmente são mais do que suficientes. Outras organizações podem desejar ter mais controle sobre o rastreamento e adotar vários sistemas para criar os códigos de rastreamento desejados. Se sua organização usar o Google Analytics além do Adobe Analytics, ela pode já ter um modelo de código de rastreamento de `utm` estabelecido.

Independentemente de como você escolhe criar ou gerar códigos de rastreamento, adotar um sistema consistente oferece à sua organização muito mais facilidade ao agrupar códigos de rastreamento para relatórios. Os códigos de rastreamento estruturados de forma consistente permitem criar [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para obter insights sobre o desempenho categórico.

## Adicionar o código de rastreamento desejado a um URL

Quando tiver o código de rastreamento desejado, é possível adicioná-lo a qualquer link que seja publicado online, como anúncios, redes sociais ou email. A adição desses códigos de rastreamento normalmente é feita por meio de uma string de consulta do link. O parâmetro de string de consulta que você usa depende dos requisitos de rastreamento da organização. Um parâmetro de string de consulta comum é `cid` (abreviação de ID de campanha). Algumas organizações que também usam o Google Analytics podem já ter vários parâmetros de string de consulta de campanha, como `utm_source`, `utm_medium` e outros.

A adição de strings de consulta a um link em um email seria semelhante ao seguinte:

```text
https://example.com?cid=EM989027
```

## Incluir variáveis de campanha na implementação

O Adobe Analytics tem uma dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md) dedicada que você pode usar para medir vários esforços de marketing em sua organização. No entanto, organizações diferentes podem ter requisitos de rastreamento diferentes. É importante consultar o [Documento de design da solução](../prepare/solution-design.md) da sua organização para rastrear de forma consistente os valores corretos nas variáveis certas.

Se a organização ainda não configurou o rastreamento de campanha, você pode ajustar a implementação para utilizar a variável [`campaign`](/help/implement/vars/page-vars/campaign.md). Consulte o método [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) para saber como coletar valores de parâmetros de string de consulta específicos para a implementação da sua organização.

Se sua organização coleta strings de consulta `utm`, você pode optar por:

* Enviar todas as strings de consulta `utm` por meio da dimensão Código de rastreamento como valores concatenados.  Em seguida, é possível usar [Regras de classificação](/help/components/classifications/crb/classification-rule-builder.md) para criar dimensões adicionais com foco em cada parâmetro `utm`. Esse método tem uma curva de aprendizado mais complexa, mas não usa eVars extras.
* Enviar cada string de consulta `utm` em uma [eVar](/help/components/dimensions/evar.md) separada. Esse método é mais simples de se implementar no geral, mas requer o uso de eVars extras.

## Exibir os relatórios no Analysis Workspace

Depois de configurar corretamente a implementação para coletar dados do código de rastreamento, é possível visualizar os relatórios no Analysis Workspace.

1. Faça logon na [Adobe Experience Cloud](https://experience.adobe.com) e selecione [!UICONTROL Adobe Analytics].
1. Crie um [projeto do espaço de trabalho](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Na lista de componentes à esquerda, arraste a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md) para a tela do espaço de trabalho.
1. Arraste a métrica desejada, como [Visitas](/help/components/metrics/visits.md) ou [Pedidos](/help/components/metrics/orders.md) à direita da tela do espaço de trabalho.

![Relatório de rastreamento de campanha](../assets/campaign-tracking-report.png)
