---
description: Exibe as médias das métricas no grupo de relatório Campanhas. Métricas padrão são click-throughs, Total de vendas, Pedidos e Receita.
seo-description: Exibe as médias das métricas no grupo de relatório Campanhas. Métricas padrão são click-throughs, Total de vendas, Pedidos e Receita.
seo-title: Funil de Conversão de Campanha
solution: Analytics
title: Funil de Conversão de Campanha
topic: 'Relatórios  '
uuid: b 0 a 90917-e 4 c 7-40 da -854 e -58649 de 09742
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Funil de Conversão de Campanha

Exibe as médias das métricas no grupo de relatório Campanhas. Métricas padrão são click-throughs, Total de vendas, Pedidos e Receita.

**[!UICONTROL Campanhas]** &gt; **[!UICONTROL Funil de conversão de campanha]**

A parte superior do gráfico de funil exibe os dados de conversão. A parte inferior exibe estatísticas de todos os eventos na área superior, com base em Pedidos e até duas outras métricas, Receita e Unidades.

Observe as seguintes informações ao interpretar dados de funil de conversão:

* Estatísticas dos períodos de tempo atuais podem não estar completas ao visualizar dados, que podem afetar tendências do dia anterior ao atual.
* Quando nenhum filtro é aplicado ao funil, a métricas de Visitas representa as visitas de conversão, ou visitas quando a variável de campanha, qualquer variável de eVar ou um evento bem-sucedido foram disparados. Visitas nas quais nenhuma dessas propriedades foram enviadas aos relatórios não são incluídas nesse total.
* Quando um filtro é aplicado ao funil, a métrica de Visitas representa instâncias (ou click-throughs). Este valor é o número total de vezes que uma variável específica foi populada por usuários do site, excluindo instâncias que não atendem aos requisitos de filtro. Uma única visita pode envolver múltiplas instâncias.
* É possível que níveis mais profundos do funil relatem números mais altos do que níveis mais rasos. Por exemplo, você poderá ver mais pedidos que click-throughs, ou mais finalizações do que visualizações de produtos. Existem diversos motivos para que isto ocorra:

   * Você pode ter mais pedidos do que click-throughs se a variável de Código de rastreamento estiver definida para uma expiração longa de cookie (ex: um mês) e o usuário fizer somente um click-through, retornar diversas vezes e fizer pedidos durante o período, antes do valor do Código de rastreamento expirar.
   * Você pode ter mais finalizações do que visualizações de produtos se o usuário for capaz de ignorar a página de visualização de produto (no caso de uma página de upsell), ou se o usuário for capaz de salvar seu carrinho de comprar e retornar depois para concluir o pedido. Se a visualização do produto ocorrer antes do intervalo de datas selecionado e a finalização ocorrer posteriormente, você verá uma finalização e nenhuma visualização de produto. Caso perceba essa diferença, isso não indica que existe um problema com o relatório ou algum erro de implementação. Em vez disso, você pode utilizar esses dados para compreender como os usuários interagem com site, mesmo que eles não se encaixem no funil da forma esperada.

