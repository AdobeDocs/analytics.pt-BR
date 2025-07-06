---
description: Saiba como segmentar métricas individuais que permitem fazer comparações de métricas na mesma visualização.
title: Métricas segmentadas
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 1%

---

# Métricas segmentadas

No [Construtor de métrica calculada](cm-build-metrics.md#definition-builder), você pode aplicar segmentos à definição de métricas. A aplicação de segmentos é útil se você deseja usar métricas para um subconjunto de seus dados em análise.

>[!NOTE]
>
>As definições de segmento são atualizadas por meio do [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md). Se você fizer uma alteração em um segmento, ele será atualizado automaticamente em todos os lugares em que for usado, inclusive se fizer parte de uma definição de métrica calculada.
>

Você deseja comparar métricas para os alemães que interagem com sua marca e pessoas de fora da Alemanha. Assim, você pode responder a perguntas como:

1. Quantos alemães contra internacionais estão visitando suas [páginas mais populares](#popular-pages).
1. Quantos alemães x internacionais no [total](#totals) interagiram online com sua marca este mês.
1. Quais são as [porcentagens](#percentages) de alemães e internacionais que visitaram suas páginas populares?

Consulte as seções abaixo para ilustrar como as métricas segmentadas podem ajudar você a responder a essas perguntas. Se for caso disso, são feitas referências a documentação mais pormenorizada.

## Páginas populares

1. [Crie uma métrica calculada](../cm-workflow.md) de um projeto do Workspace, denominado `Germany`.
1. No [Construtor de métrica calculada](cm-build-metrics.md), [crie um segmento](/help/components/segmentation/segmentation-workflow/seg-build.md), denominado `Germany`, que esteja usando o campo Países.

   >[!TIP]
   >
   >No Criador de métrica calculada, é possível criar um segmento diretamente usando o painel Componentes.
   >   

   Seu segmento pode se parecer com.

   ![Segmento Alemanha](assets/segment-germany.png)

1. De volta ao Criador de métrica calculada, use o segmento para atualizar a métrica calculada.

   ![Métrica calculada Alemanha](assets/germany-visits.png)

Repita as etapas acima para a versão internacional da sua métrica calculada.

1. Crie uma métrica calculada a partir do seu projeto do Workspace, intitulado `Non Germany visits`.
1. No Criador de métrica calculada, crie um segmento, intitulado `Not Germany`, que esteja usando o campo País do CRM dos dados do CRM para determinar de onde uma pessoa vem.

   Seu segmento deve parecer com.

   ![Segmento Alemanha](assets/segment-not-germany.png)

1. De volta ao Criador de métrica calculada, use o segmento para atualizar a métrica calculada.

   ![Métrica calculada Alemanha](assets/non-germany-visits.png)


1. Crie um projeto no Analysis Workspace, onde você pode ver as páginas visitadas por visitantes alemães e não alemães.

   ![Visualização da tabela de forma livre do Workspace mostrando alemães vs. internacionais](assets/workspace-german-vs-international.png)


## Totais

1. Crie duas novas métricas calculadas com base no Total geral. Abra cada um dos segmentos criados anteriormente, renomeie o segmento, defina o **[!UICONTROL Tipo de métrica]** para **[!UICONTROL Pessoas]** como **[!UICONTROL Total geral]** e use **[!UICONTROL Salvar como]** para salvar o segmento usando o novo nome. Por exemplo:

   ![Métrica total para a Alemanha](assets/calculated-metric-germany-total.png)

1. Adicione uma nova visualização de Tabela de forma livre ao projeto do Workspace, mostrando o total de páginas deste ano.

   ![Visualização da tabela de forma livre do Workspace mostrando o total de pessoas do alemão vs. internacional](assets/workspace-german-vs-international-totals.png)


## Porcentagens

1. Crie duas novas métricas calculadas que calculam uma porcentagem a partir das métricas calculadas criadas anteriormente.

   ![Visualização da tabela de forma livre do Workspace mostrando o percentual de pessoas total alemão vs. internacional](assets/calculated-metric-germany-total-percentage.png)


1. Atualize seu projeto do Workspace.

   ![Visualização da tabela de forma livre do Workspace mostrando o total de pessoas do alemão vs. internacional](assets/workspace-german-vs-international-totals-percentage.png)

