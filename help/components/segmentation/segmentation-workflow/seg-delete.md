---
description: Lista alguns itens que devem ser considerados antes de excluir segmentos.
title: Excluir segmentos
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: b96210a478c46f5d9cbf49c6288b698dc47d64fe
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 91%

---

# Excluir segmentos

Lista alguns itens que devem ser considerados antes de excluir segmentos.

Quando você exclui um segmento,

* Os relatórios e painéis agendados com esse segmento aplicado continuam a funcionar normalmente, ou seja, o segmento ou painel continua a usar o segmento excluído.
* Os relatórios agendados não são atualizados quando você edita um segmento com o mesmo nome. Exemplo: imagine que você tem 2 segmentos com o mesmo nome em conjuntos de relatórios diferentes:

  | Nome do segmento | Conjunto de relatórios |
  |---|---|
  | Visitas da Califórnia | mainprod |
  | Visitas da Califórnia | maindev |


  Você tem um marcador que faz referência ao segmento para o conjunto de relatórios `mainprod`. Em seguida, você exclui esse segmento, pois é uma duplicata. O marcador continuará a funcionar, com referência à definição do segmento excluído. Se você alterar a definição do segmento para o segmento restante para incluir a Ilha de Catalina e Tijuana no México, o segmento aplicado ao marcador não mudará. Usará a definição antiga. Para corrigir isso, atualize o marcador para fazer referência à nova definição. Se você não tiver certeza se um marcador, painel ou relatório agendado está usando um segmento excluído, é possível alterar o nome do segmento restante para que fique mais clara se o marcador usa o segmento restante.
