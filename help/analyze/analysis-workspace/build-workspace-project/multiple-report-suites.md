---
title: Vários conjuntos de relatórios
description: Saiba como trabalhar com vários conjuntos de relatórios em um único projeto do Analysis Workspace.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 71%

---

# Vários conjuntos de relatórios

Você pode criar projetos no Analysis Workspace com dados de mais de um conjunto de relatórios. Os conjuntos de relatórios são escolhidos no nível do painel, então é possível escolher um conjunto de relatórios diferente para cada painel dentro do mesmo projeto do Workspace.

Esse recurso é útil se você deseja:

* Comparar dados de duas regiões diferentes, e os dados estão em dois conjuntos de relatórios diferentes. É possível criar tabelas e visualizações para comparar os dados lado a lado.

* Criar um painel de métricas e visualizações para gerar relatórios para outras organizações. Você pode extrair dados de vários conjuntos de relatórios para o mesmo projeto.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Vários conjuntos de relatórios](https://video.tv.adobe.com/v/37063?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

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
   * Ativar as dimensões/métricas necessárias.
   * Alterar o conjunto de relatórios.
   * Continuar com alguns componentes ausentes. Isso resultará em componentes sem nenhum dado e/ou em visualizações em branco.

1. Altere o painel para que use um conjunto de relatórios diferente e observe como o rótulo do componente (conjunto de relatórios atualmente ativo) e os componentes listados são atualizados com base no novo conjunto de relatórios.

1. Use o atalho do teclado (ao arrastar `shift`) para transformar um painel inativo em um painel ativo.

1. (Opcional) Você também pode ir para outros construtores de componentes do Analytics e garantir que eles passaram a mostrar um rótulo de conjunto de relatórios que indica

   * Onde um segmento será criado: [Construtor de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=pt-BR).
   * Onde uma métrica calculada será criada: [Construtor de métrica calculada](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR).
   * Onde um alerta será criado: [Construtor de alertas](https://experienceleague.adobe.com/docs/analytics/components/alerts/alert-builder.html?lang=pt-BR).
