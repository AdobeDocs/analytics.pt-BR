---
title: Múltiplos Conjuntos de relatórios
description: Saiba como trabalhar com vários conjuntos de relatórios em um único projeto do Analysis Workspace.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
TQID: https://experienceleague.adobe.com/IrWsvooPWqWmbDAD-70CgI71gEPJCQY-1wFHFyuJsyc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 69%

---

# Vários conjuntos de relatórios

Você pode criar projetos no Analysis Workspace com dados de mais de um conjunto de relatórios. Os conjuntos de relatórios são escolhidos no nível do painel, então é possível escolher um conjunto de relatórios diferente para cada painel dentro do mesmo projeto do Workspace.

Esse recurso é útil se você deseja:

* Comparar dados de duas regiões diferentes, e os dados estão em dois conjuntos de relatórios diferentes. É possível criar tabelas e visualizações para comparar os dados lado a lado.

* Criar um painel de métricas e visualizações para gerar relatórios para outras organizações. Você pode extrair dados de vários conjuntos de relatórios para o mesmo projeto.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Vários conjuntos de relatórios](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Aplicar o conjunto de relatórios a todos os painéis

Você pode aplicar um conjunto de relatórios a todos os painéis ao mesmo tempo clicando com o botão direito do mouse em qualquer cabeçalho do painel e selecionando **[!UICONTROL Aplicar o conjunto de relatórios a todos os painéis]**.

![](assets/apply-rs-all-panels.png)

## Painel ativo

Você pode reconhecer o painel ativo pela borda azul clara ao redor dele. Basta selecionar dentro de um painel para transformar esse painel no painel ativo.

>[!TIP]
>
>Você pode arrastar e soltar em qualquer painel que esteja no mesmo conjunto de relatórios que o painel ativo. Ao arrastar para um painel inativo do mesmo conjunto de relatórios, o painel ficará ativo.
>

## Trabalhe com vários conjuntos de relatórios

![](assets/mrs-ui.png)

1. Crie um novo projeto com 2 ou mais painéis no Espaço de trabalho.

1. Arraste e solte componentes (métricas, dimensões, segmentos, intervalos de datas) no painel. Certifique-se de que os painéis tenham dados e visualizações específicos para o conjunto de relatórios.


   >[!NOTE]
   >
   >Algumas vezes, um banner é exibido ao carregar um projeto (ou alternar para um conjunto de relatórios) em que nem todos os componentes incluídos no projeto estão incluídos no conjunto de relatórios. Os componentes ausentes serão listados. Siga [estas instruções](/help/admin/admin-console/permissions/product-profile.md) para definir permissões das métricas/dimensões necessárias.
   >

   ![](assets/incompat-rs.png)

   Você tem três opções para lidar com essa incompatibilidade:
   * Habilitar as dimensões/métricas necessárias.
   * Alterar o conjunto de relatórios.
   * Continuar com alguns componentes ausentes. Isso resultará em componentes sem nenhum dado e/ou em visualizações em branco.

1. Altere o painel para que use um conjunto de relatórios diferente e observe como o rótulo do componente (conjunto de relatórios atualmente ativo) e os componentes listados são atualizados com base no novo conjunto de relatórios.

1. Use o atalho do teclado (ao arrastar `shift`) para transformar um painel inativo em um painel ativo.

1. (Opcional) Você também pode ir para outros construtores de componentes do Analytics e garantir que eles passaram a mostrar um rótulo de conjunto de relatórios que indica

   * Onde um segmento será criado: [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md).
   * Onde uma métrica calculada será criada: [Construtor de métrica calculada](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md).
   * Onde um alerta será criado: [Construtor de alertas](/help/components/alerts/alert-builder.md).
