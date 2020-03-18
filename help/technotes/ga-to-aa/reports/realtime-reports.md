---
title: Relatórios em tempo real no Adobe Analytics
description: Saiba como obter relatórios em tempo real no Adobe Analytics direcionados para usuários mais familiarizados com o Google Analytics.
translation-type: ht
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Relatórios em Tempo real

Relatórios em tempo real mostram o que está acontecendo em seu site agora. Esses tipos de relatórios são especialmente valiosos para ver os resultados imediatos das atualizações que você faz no site. Por exemplo, uma empresa que realiza uma venda na Black Friday pode medir o tráfego para páginas específicas e determinar quais vendas priorizar com base no desempenho naquele momento.

![Relatório em tempo real](/help/technotes/ga-to-aa/assets/realtime.png)

Relatórios em tempo real são um dos poucos recursos que ainda não foram introduzidos no Analysis Workspace. Use o Reports &amp; Analytics para obter esses dados. Eles exigem configurações simples para começar a coletar dados.

Para acessar a página de configuração de relatório em tempo real (são necessárias permissões de administrador):

1. Clique em [!UICONTROL Relatórios] na navegação do cabeçalho do Adobe Analytics.
2. No menu esquerdo, clique em *[!UICONTROL Métricas do site]* > *[!UICONTROL Tempo real]*.
3. Se o conjunto de relatórios ainda não tiver o tempo real ativado, uma mensagem será exibida com um link para configurar o conjunto de relatórios. Se o conjunto de relatórios tiver o tempo real ativado, clique em [!UICONTROL Configurar] próximo ao título do relatório em tempo real.

A Adobe permite que até três relatórios em tempo real coletem dados simultaneamente. Cada relatório deve ser configurado antes de começarem a coletar dados em tempo real.

![Configuração de relatórios em tempo real](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Locais em tempo real

Os locais em tempo real informam onde os visitantes residem enquanto visitam seu site no momento atual. Para configurar um dos três relatórios em tempo real para mostrar os dados de localização:

1. Clique em [!UICONTROL Configurar] próximo ao título do relatório em tempo real.
2. Em um dos slots de relatório em tempo real:
   * Dê um nome ao seu relatório em tempo real; por exemplo, &quot;Locais&quot;.
   * Instâncias são normalmente usadas como a Métrica. Usuários/Visitantes únicos não estão disponíveis nos relatórios em tempo real no momento.
   * Para Dimensão principal, é normalmente usado País da segmentação geográfica. Região de segmentação geográfica, DMA de segmentação geográfica dos EUA e Cidade de segmentação geográfica também estão disponíveis.
   * Para as duas dimensões secundárias, use os dados adicionais de sua preferência que você gostaria de ver para esse tráfego. As dimensões secundárias não precisam ser específicas ao local.
3. Clique em [!UICONTROL Salvar e exibir relatório].

## Fontes de tráfego em tempo real

As fontes de tráfego em tempo real informam de onde os visitantes vieram enquanto visitam seu site no momento atual. Para configurar um dos três relatórios em tempo real para mostrar os dados das fontes de tráfego:

1. Clique em “Configurar” próximo ao título do relatório em tempo real.
2. Em um dos slots de relatório em tempo real:
   * Dê um nome ao seu relatório em tempo real; por exemplo, &quot;Fontes de tráfego&quot;.
   * Instâncias são normalmente usadas como a Métrica. Usuários/Visitantes únicos não estão disponíveis nos relatórios em tempo real no momento.
   * Para Dimensão primária, é normalmente usado Domínio de referência. Mecanismo de pesquisa e Palavra-chave de pesquisa também estão disponíveis.
   * Para as duas dimensões secundárias, use os dados adicionais de sua preferência que você gostaria de ver para esse tráfego. As dimensões secundárias não precisam ser específicas às fontes de tráfego.
3. Clique em [!UICONTROL Salvar e exibir relatório].

## Conteúdo em tempo real

O conteúdo em tempo real informa quais páginas seus visitantes estão visualizando no momento. Para configurar um dos três relatórios em tempo real para mostrar os dados de conteúdo:

1. Clique em [!UICONTROL Configurar] próximo ao título do relatório em tempo real.
2. Em um dos slots de relatório em tempo real:
   * Dê um nome ao seu relatório em tempo real; por exemplo, &quot;Conteúdo&quot;.
   * Instâncias são normalmente usadas como a Métrica. Usuários/Visitantes únicos não estão disponíveis nos relatórios em tempo real no momento.
   * Para Dimensão primária, é normalmente usada Página. Seção do site e Servidor também estarão disponíveis se sua implementação definir essas variáveis.
   * Para as duas dimensões secundárias, use os dados adicionais de sua preferência que você gostaria de ver para esse tráfego. As dimensões secundárias não precisam ser específicas para o conteúdo.
3. Clique em [!UICONTROL Salvar e exibir relatório].

## Eventos em tempo real

Os eventos em tempo real informam quais eventos estão ocorrendo mais em seu site. No Google Analytics, um evento captura o número de vezes que uma ação específica (geralmente uma ação não relacionada a uma exibição de página) ocorreu. Os eventos do GA são enviados com uma Categoria, Etiqueta e Ação. No Adobe Analytics, os eventos personalizados são métricas que recebem nomes amigáveis no console de administração e que podem ser analisadas ao lado de qualquer dimensão. Se você estiver procurando uma dimensão no Adobe Analytics semelhante aos eventos do Google Analytics, considere a aplicação da dimensão Link personalizado, que é usada como uma captura para coletar dados que não estão relacionados às exibições de página (além de Links de saída - para saídas - e Links de download - para downloads).

> [!NOTE] Ao usar eventos personalizados em relatórios em tempo real, o valor da dimensão deve ser definido na mesma ocorrência do evento personalizado. Por exemplo, se estiver exibindo um evento personalizado “Registros” para a dimensão “Domínio de referência”, nenhum dado será retornado sem implementação adicional. Como o domínio de referência aparece somente na primeira ocorrência e um evento personalizado normalmente aparece mais tarde na visita, os dados não podem ser associados em relatórios em tempo real. Esses dados estão disponíveis no Analysis Workspace usando a latência de processamento padrão, que normalmente é de 30 a 90 minutos.

## Conversões em tempo real

As conversões em tempo real apresentam dados de maneiras diferentes em cada plataforma. As metas no Google Analytics são semelhantes às métricas e aos eventos de sucesso no Adobe Analytics. Você pode usar a maioria das métricas no Adobe Analytics (tanto métricas personalizadas como eventos de sucesso e métricas padrão como de receita) nos Relatórios em tempo real. Assim como no Google Analytics, também é possível aplicar dimensões como nome do produto, código de rastreamento e desempenho da campanha em relatórios em tempo real.

1. Clique em [!UICONTROL Configurar] próximo ao título do relatório em tempo real.
2. Em um dos slots de relatório em tempo real:
   * Dê um nome ao seu relatório em tempo real; por exemplo, &quot;Conversões&quot;.
   * Instâncias são normalmente usadas como a Métrica. Usuários/Visitantes únicos não estão disponíveis nos relatórios em tempo real no momento.
   * Para Dimensão primária, o Código de rastreamento geralmente é usado. A dimensão Produtos também estará disponível se sua implementação a utilizar.
   * Para as duas dimensões secundárias, use os dados adicionais de sua preferência que você gostaria de ver para esse tráfego. As dimensões secundárias não precisam ser específicas para conversões.
3. Clique em [!UICONTROL Salvar e exibir relatório].

> [!NOTE] Se estiver usando eventos fora de Instâncias, como Pedidos, certifique-se de que sua implementação defina a dimensão e o evento na mesma ocorrência. Se dimensões e eventos não forem acionados na mesma ocorrência, esses dados estarão disponíveis no Analysis Workspace usando a latência de processamento padrão, que normalmente é de 30 a 90 minutos.
