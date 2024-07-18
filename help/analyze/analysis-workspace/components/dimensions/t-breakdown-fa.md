---
description: Analise dimensões e itens de dimensão no Analysis Workspace.
keywords: Analysis Workspace
title: Analisar dimensões
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 100%

---

# Analisar dimensões

Analise dimensões e itens de dimensão no Analysis Workspace.

Analise os seus dados de formas ilimitadas, de acordo com as suas necessidades específicas; crie consultas usando métricas, dimensões, segmentos, linhas do tempo e outros valores de detalhamento de análise relevantes.

1. [Crie um projeto](/help/analyze/analysis-workspace/home.md) com uma tabela de dados.
1. Na tabela de dados, clique com o botão direito em um item da linha e selecione **[!UICONTROL Detalhamento]** > *`<item>`*.

   ![Resultado da etapa](assets/fa_data_table_actions.png)

   Você pode analisar métricas por itens de dimensão ou segmentos de público-alvo em todos os períodos selecionados. É possível especificar ainda mais para um nível mais granular.

   >[!NOTE]
   >
   >O número de detalhamentos exibidos na tabela é limitado a 200. Esse limite vai aumentar para a exportação de detalhamentos.

## Aplicar modelos de atribuição a detalhamentos

Qualquer detalhamento em uma tabela também pode ter qualquer modelo de atribuição aplicado a ela. Esse modelo de atribuição pode ser o mesmo ou diferente da coluna pai. Por exemplo, você pode analisar Pedidos lineares em sua dimensão de Canais de marketing mas deseja aplicar Pedidos de forma de U aos códigos de rastreamento específicos em um Canal. Para editar o modelo de atribuição aplicado a um detalhamento, passe o mouse sobre o modelo de detalhamento e clique em **[!UICONTROL Editar]**:

![Configurações de detalhamento](assets/breakdown_settings.png)

Este é o comportamento esperado ao aplicar modelos de atribuição a detalhamentos ou editá-los:

* Se você aplicar uma atribuição quando nenhuma outra atribuição existir, a atribuição se aplicará a toda a árvore de colunas.

* Se você adicionar um detalhamento depois que uma atribuição for aplicada, ele usará o padrão para o detalhamento especificado que foi adicionado, se esta dimensão tiver um padrão. Caso contrário, ele usará o detalhamento da coluna master. Algumas dimensões têm uma alocação padrão.  Por exemplo, [!UICONTROL Hora,] dimensões e [!UICONTROL indicação] usam o [!UICONTROL Mesmo contato]. A [!UICONTROL dimensão] do produto usa [!UICONTROL o último contato]. Outras dimensões não têm um padrão e usarão a alocação de coluna master.

* Se já houver atribuições na árvore de colunas, alterar a atribuição afetará somente a que você estiver editando.

## Vídeos

Adicionar dimensões e métricas ao seu projeto no Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606/?quality=12)

Trabalhar com dimensões em uma Tabela de forma livre:

>[!VIDEO](https://video.tv.adobe.com/v/40179/?quality=12)

Veja um vídeo sobre detalhamentos de dimensão por posição:

>[!VIDEO](https://video.tv.adobe.com/v/24033/?quality=12)
