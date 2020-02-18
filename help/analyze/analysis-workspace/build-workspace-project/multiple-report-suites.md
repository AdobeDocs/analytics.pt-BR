---
title: Vários conjuntos de relatórios no Workspace
description: Saiba como e por que criar projetos no Workspace com vários conjuntos de relatórios
translation-type: tm+mt
source-git-commit: 1a08003170ba07a722927e935ecda26e1d189235

---


# Vários conjuntos de relatórios no Workspace

>[!IMPORTANT]
>Vários conjuntos de relatórios no Workspace estão atualmente em versão limitada.

Agora você pode criar projetos na Analysis Workspace com dados de mais de um conjunto de relatórios. Os conjuntos de relatórios agora são escolhidos no nível do painel, portanto, você pode escolher um conjunto de relatórios diferente para cada painel dentro do mesmo projeto do Workspace.

Esse recurso é útil se você desejar, por exemplo,

* Compare dados de duas regiões diferentes e os dados residem em dois conjuntos de relatórios diferentes. É possível criar tabelas e visualizações para comparar os dados lado a lado.

* Crie um painel de métricas e visualizações para criar relatórios para outras organizações. Agora é possível extrair dados de vários conjuntos de relatórios para o mesmo projeto.

## Painel ativo

Estamos introduzindo o conceito de &quot;painel ativo&quot; versus &quot;painel inativo&quot; com este recurso. Você pode reconhecer o painel ativo pela borda azul clara ao redor dele. Basta clicar dentro de um painel para transformar esse painel no painel ativo.

>[!IMPORTANT]
>Você pode arrastar e soltar em qualquer painel que esteja no mesmo conjunto de relatórios que seu painel ativo. Ao arrastar para um painel inativo do mesmo conjunto de relatórios, o painel ficará ativo.

| Tarefa | Painel ativo | Painel inativo |
|---|---|---|
| Alterar conjunto de relatórios | Sim | Não |
| Arrastar e soltar componentes | Sim | Sim, para qualquer painel que esteja no mesmo conjunto de relatórios que seu painel ativo. |
| Visualizações de arrastar e soltar | Sim | Sim, para qualquer painel que esteja no mesmo conjunto de relatórios que seu painel ativo. |

## Trabalhar com vários conjuntos de relatórios

![](assets/mrs-ui.png)

1. Crie um novo projeto com 2 ou mais painéis no Workspace.

1. Arraste e solte componentes (métricas, dimensões, segmentos, intervalos de datas) no painel. Certifique-se de que os painéis tenham dados e visualizações específicos para o conjunto de relatórios.


   >[!NOTE]
   >Às vezes, um banner é exibido ao carregar um projeto (ou ao alternar para um conjunto de relatórios) onde nem todos os componentes incluídos no projeto são incluídos no conjunto de relatórios. Os componentes ausentes serão listados. Siga [estas instruções](/help/admin/admin-console/permissions/product-profile.md) para definir permissões para as métricas/dimensões necessárias.

   ![](assets/incompat-rs.png)

   Você tem três opções para lidar com essa incompatibilidade:
   * Ativar as dimensões/métricas necessárias
   * Alterar o conjunto de relatórios.
   * Continue com alguns componentes ausentes. Isso resultará em nenhum dado para esses componentes e/ou visualizações em branco.

1. Altere o painel para um conjunto de relatórios diferente e observe como o rótulo do componente (conjunto de relatórios atualmente ativo) e os componentes listados são atualizados com base no novo conjunto de relatórios.

1. Use um atalho de teclado (`shift` ao arrastar) para transformar um painel inativo em um painel ativo.

1. (Opcional) Você também pode ir para outros construtores de componentes do Analytics e garantir que eles agora mostrem uma etiqueta de conjunto de relatórios indicando

   * Onde um segmento será criado: Construtor [de segmentos](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).
   * Onde uma métrica calculada será criada: Construtor [](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)de métricas calculadas.
   * Quando um alerta for criado: Construtor [de alertas](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html).