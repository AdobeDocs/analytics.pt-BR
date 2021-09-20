---
description: Use segmentos rápidos no Analysis Workspace.
title: Segmentos rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: 8cd5d5ec1525e29779a13330dfeaeae120dfdd56
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

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

