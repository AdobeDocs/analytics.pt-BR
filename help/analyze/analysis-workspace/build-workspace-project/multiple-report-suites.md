---
title: Vários conjuntos de relatórios no Workspace
description: Saiba como e por que criar projetos no Workspace com vários conjuntos de relatórios
translation-type: tm+mt
source-git-commit: 7f79d5c041959e4093b2aaacb64c948b0593262f

---


# Vários conjuntos de relatórios no Workspace

>[!IMPORTANT]
>Este recurso está atualmente em testes Beta e será lançado no início de 2020.

Agora você pode criar projetos na Analysis Workspace com dados de mais de um conjunto de relatórios. Os conjuntos de relatórios agora são escolhidos no nível do painel, portanto, você pode escolher um conjunto de relatórios diferente para cada painel dentro do mesmo projeto do Workspace.

Esse recurso é útil se você desejar, por exemplo,

* Compare dados de duas regiões diferentes e os dados residem em dois conjuntos de relatórios diferentes. É possível criar tabelas e visualizações para comparar os dados lado a lado.

* Crie um painel de métricas e visualizações para criar relatórios para outras organizações. Agora é possível extrair dados de vários conjuntos de relatórios para o mesmo projeto.

## Painel ativo

Estamos introduzindo o conceito de "painel ativo" versus "painel inativo" com este recurso. O painel ativo é reconhecível pela borda azul clara ao seu redor. Basta clicar dentro de um painel para tornar esse painel ativo.

>[!IMPORTANT]
>Você pode arrastar e soltar componentes **somente no painel** ativo, mesmo se outros painéis tiverem o mesmo conjunto de relatórios. Se quiser alterar o painel ao arrastar e soltar, use um atalho: pressione `shift` enquanto arrasta para alterar um painel inativo para um painel ativo.

| Tarefa | Painel ativo | Painel inativo |
|---|---|---|
| Alterar conjunto de relatórios | Sim | Não |
| Arrastar e soltar componentes | Sim | Não |
| Visualizações de arrastar e soltar | Sim | Não |

## Trabalhar com vários conjuntos de relatórios

![](assets/mrs-ui.png)

1. Crie um novo projeto com 2 ou mais painéis no Workspace.

1. Arraste e solte componentes (métricas, dimensões, segmentos, intervalos de datas) no painel. Certifique-se de que os painéis tenham dados e visualizações específicos para o conjunto de relatórios.


   >[!NOTE]
   >Às vezes, uma mensagem "Conjunto de relatórios incompatível" aparece ao carregar um projeto (ou ao alternar para um conjunto de relatórios), onde nem todos os componentes incluídos no projeto são incluídos no conjunto de relatórios. Os componentes ausentes serão listados. Siga [estas instruções](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles) para definir permissões para as métricas/dimensões necessárias.

   ![](assets/incompat-rs.png)

   1. Você tem três opções para lidar com essa incompatibilidade:
   * Continue com alguns componentes ausentes.
   * Recurso Desfazer.
   * Alterar o conjunto de relatórios.

1. Altere o painel para um conjunto de relatórios diferente e observe como o rótulo do componente (conjunto de relatórios atualmente ativo) e os componentes listados são atualizados com base no novo conjunto de relatórios.

1. Use o atalho do teclado (`shift` ao arrastar) para transformar um painel inativo em um painel ativo.

1. (Opcional) Você também pode ir para outros construtores de componentes do Analytics e garantir que eles agora mostrem uma etiqueta de conjunto de relatórios indicando

   * Onde um segmento será criado (Construtor de segmentos).
   * Onde uma métrica calculada será criada (Criador de métricas calculadas).
   * Onde um alerta será criado (Criador de alertas).