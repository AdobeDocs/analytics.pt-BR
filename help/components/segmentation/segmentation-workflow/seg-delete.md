---
description: Lista alguns itens que devem ser considerados antes de excluir segmentos.
title: Excluir segmentos
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 39%

---

# Excluir segmentos

Este artigo lista algumas considerações que você deve ter em mente antes de excluir segmentos.

Ao excluir um segmento:

* Os relatórios e painéis agendados com esse segmento aplicado continuam funcionando normalmente. Por exemplo, o segmento ou painel continua a usar o segmento excluído.
* Os relatórios agendados não são atualizados quando você edita um segmento com o mesmo nome. Este é um exemplo: suponha que você tenha dois segmentos com o mesmo nome em conjuntos de relatórios diferentes:

  | Nome do segmento | Conjunto de relatórios |
  |---|---|
  | Visitas da Califórnia | mainprod |
  | Visitas da Califórnia | maindev |

  Você tem um marcador que faz referência ao segmento para o conjunto de relatórios [!UICONTROL mainprod]. Em seguida, você exclui esse segmento, pois o segmento é uma duplicata. O marcador continuará a funcionar, com referência à definição do segmento excluído. Se você alterar a definição do segmento para o segmento restante para incluir a Ilha de Catalina e Tijuana no México, o segmento aplicado ao marcador não mudará. O segmento usará a definição antiga. Para corrigir isso, atualize o marcador para fazer referência à nova definição. Se você não tiver certeza se um marcador, painel ou relatório agendado está usando um segmento excluído, é possível alterar o nome do segmento restante para indicar se o marcador está usando o segmento restante.
