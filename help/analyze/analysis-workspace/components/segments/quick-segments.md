---
description: Use segmentos rápidos no Analysis Workspace.
title: Segmentos rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# Segmentos rápidos

Você pode criar segmentos rápidos em um projeto para ignorar a complexidade do [construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) completo. Para uma comparação do que os segmentos rápidos podem fazer em relação aos segmentos de nível de componente completos, acesse [aqui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Os segmentos rápidos estão atualmente em testes limitados e ainda não estão disponíveis no geral.

## Criar segmentos rápidos

1. Em uma tabela de Forma livre, clique no ícone filter+ no cabeçalho do painel:

   ![](assets/quick-seg1.png)

   Observe que:

   - Há apenas um contêiner de segmento que permite incluir uma dimensão/métrica/intervalo de datas no segmento (ou excluí-lo dele).
   - É possível definir o contêiner como nível de Ocorrência, Visita ou Visitante. O padrão é Ocorrência.

1. Adicione uma dimensão/métrica/intervalo de datas de uma das três formas a seguir:

   - Comece a digitar e o construtor de Segmentos rápidos encontra automaticamente o componente apropriado.
   - Use a lista suspensa para localizar o componente.
   - Arraste e solte componentes do painel esquerdo.

1. Especifique a primeira regra, como `Page equals workspace`. É possível ter até três regras nas definições de segmento. Basta clicar no sinal &quot;+&quot; para adicionar outra regra. Você pode adicionar qualificadores &quot;AND&quot; ou &quot;OR&quot; às regras, mas não pode misturar &quot;AND&quot; e &quot;OR&quot; em uma única definição de segmento.

   Este é um exemplo de um segmento que combina dimensões e métricas:

   ![](assets/quick-seg2.png)

1. Clique em **[!UICONTROL Aplicar]** para aplicar este segmento ao painel.
O segmento aparece na parte superior. Observe sua barra lateral cinza, em oposição à barra azul para segmentos em nível de componente à esquerda.

   ![](assets/quick-seg3.png)

## Tornar os segmentos rápidos públicos

Você pode escolher se deseja tornar os segmentos públicos (globais) seguindo estas etapas:

1. Passe o mouse sobre o segmento rápido e clique no ícone &quot;i&quot;.
1. Clique em **[!UICONTROL Abrir construtor]**.
Isso abre o segmento no Construtor de segmentos.
   >[!NOTE]
   >Depois de aplicar ou salvar o segmento no Construtor de segmentos, não é mais possível editá-lo no Construtor de segmentos rápidos.
1. Clique em **[!UICONTROL OK]**.
1. No Construtor de segmentos, clique em **[!UICONTROL Aplicar]**.
1. Retorne ao Workspace e observe como o segmento agora tem uma barra lateral azul, sinalizando que faz parte da biblioteca de componentes.

   ![](assets/quick-seg4.png)

