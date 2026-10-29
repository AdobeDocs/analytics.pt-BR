---
description: Saiba como os administradores podem adicionar descrições aos componentes usando um conjunto de relatórios ou o dicionário de dados.
title: Adicionar descrições de componentes
feature: Components
role: Admin
exl-id: db36ee4a-66e2-45d1-8b7a-49570b5fce93
TQID: https://experienceleague.adobe.com/8z9vnSfrxEb1nkOlTTlHrp3BdElFJmTjbsSLBGbE7Gs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
    internal-label: Data Dictionary
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b3d9fb81837398b349496ec261dc1d0ba3df3645
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 20%
---
# Adicionar descrições de componentes

As descrições ajudam os usuários a saber como usar melhor os vários componentes ao criar projetos no Analysis Workspace ou ao visualizar relatórios.

Os administradores do Analytics podem adicionar descrições de componentes (dimensões, métricas, segmentos e intervalos de datas) em um conjunto de relatórios ou usando o Dicionário de dados diretamente no Analysis Workspace.

## Conjunto de relatórios

Você pode adicionar descrições aos componentes em um conjunto de relatórios.

1. Selecione **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione o conjunto de relatórios no Gerenciador de conjuntos de relatórios para o qual você deseja fornecer descrições de componentes.
1. Selecione **[!UICONTROL Editar Configurações]** > **[!UICONTROL Conversão]** > **[!UICONTROL Variáveis de conversão]**.
1. Selecione ![Adicionar](/help/assets/icons/Add.svg) para mostrar os detalhes de uma variável de conversão.
1. Marque a caixa de seleção de **[!UICONTROL Descrição]** e adicione uma descrição.
1. Repita as etapas 4 e 5 para qualquer outra variável à qual deseja adicionar uma descrição.
1. Selecione **[!UICONTROL Salvar]**.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adicionar descrições de componentes](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/intro-to-analytics/customizing-the-ui/adding-dimension-and-metric-descriptions){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Dicionário de dados {#add-descriptions}

O dicionário de dados do Analysis Workspace ajuda os usuários e administradores a acompanhar e compreender melhor os componentes em seu ambiente do Analytics. O Dicionário de dados permite que os administradores do Analytics adicionem descrições de componentes diretamente no Analysis Workspace.

Para obter informações sobre como editar uma descrição de componente no dicionário de dados, consulte [Editar entradas de componente no Dicionário de Dados](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

Para obter informações gerais sobre o Dicionário de dados, consulte [Visão geral do Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Configurações do componente de Relatório](/help/components/vrs/vrs-components.md)
>[Entradas do componente do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Gerar descrições automaticamente

{{release-limited-testing-section}}

Em vez de escrever cada descrição manualmente, o Adobe Analytics pode usar a IA gerativa para escrever descrições para você. Você pode gerar uma descrição para um único componente ou gerar descrições para muitos componentes ao mesmo tempo.

Descrições geradas:

* Não têm mais de 3 frases de comprimento.
* Termine com o texto **[!UICONTROL Gerado pelo Adobe usando a IA]**, para que os usuários saibam que a descrição foi gerada.
* Podem ser editadas depois de geradas.

### Pré-requisitos

Antes de gerar descrições, sua organização deve concordar com determinados termos legais de IA generativa. Se sua organização não tiver concordado com esses termos, a opção para gerar descrições ficará esmaecida. Selecione o ícone de informações ![Informações](/help/assets/icons/InfoOutline.svg) ao lado da opção para saber como habilitar o recurso ou entre em contato com o administrador da organização ou com a equipe de conta da Adobe.

### Como as descrições são geradas

As descrições geradas são baseadas na definição do componente e em contexto adicional sobre como o componente é usado no conjunto de relatórios, como:

* Os itens principais de uma dimensão
* Componentes usados com frequência com o componente

Quando uma métrica calculada ou segmento faz referência a outro segmento, a descrição gerada explica a definição do segmento referenciado.

### Gerar descrições de vários locais

Você pode gerar descrições nas seguintes áreas do Adobe Analytics. Alguns locais permitem gerar descrições para vários componentes, enquanto outros não.

Selecione um local para saber como gerar descrições.

| Localização | Componentes compatíveis | Componente único | Vários componentes |
| --- | --- | --- | --- |
| [Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensões</li><li>Métricas</li><li>Métricas calculadas</li><li>Segmentos</li><li>Intervalos de datas</li></ul> | Sim | Sim |
| [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) | Segmentos | Sim | Não |
| [Gerenciador de segmentos](/help/components/segmentation/segmentation-workflow/seg-manage.md#action-bar) | Segmentos | Não | Sim |
| [Construtor de métrica calculada](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) | Métricas calculadas | Sim | Não |
| [Gerenciador de métricas calculadas](/help/components/calculated-metrics/workflow/cm-manager.md#action-bar) | Métricas calculadas | Não | Sim |
| [Construtor de intervalo de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/create.md#date-range-builder) | Intervalos de datas | Sim | Não |
| [Gerenciador de intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/manage.md#action-bar) | Intervalos de datas | Não | Sim |

{style="table-layout:auto"}