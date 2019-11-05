---
title: Relatórios de conversões no Adobe Analytics
description: Saiba como usar relatórios de conversão no Adobe Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Relatórios de conversões

Uma "conversão" é uma ação que um visitante faz no site e que se traduz diretamente nos indicadores principais da sua organização. Os relatórios de conversões mostram detalhes sobre como os visitantes estão convertendo.

Esta página supõe que o usuário tenha um conhecimento básico sobre o uso da Analysis Workspace. Consulte [Criar um relatório básico na Analysis Workspace para usuários](create-report.md) do Google Analytics se você ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Relatórios de objetivos

As metas fornecem aos usuários do Google Analytics uma maneira de definir a conversão de um site. Elas são a maneira padrão de criar funis, reverter o fluxo comportamental, funis multicanal e atribuição. As metas no Google Analytics não são retroativas e só podem ser configuradas na página de administração. Além disso, elas se baseiam em apenas uma página, evento, tempo gasto ou número médio de páginas.

No Adobe Analytics, o conceito de meta não é necessário, pois as métricas podem ser aplicadas em qualquer contexto. Desde que sua implementação acomode os eventos que deseja rastrear, você pode ajustar qualquer relatório de conversão e obter resultados imediatamente para dados históricos.

### Visualização de funil

O relatório de visualização de funil ajuda os analistas a se concentrarem em uma série específica de etapas necessárias para a conversão. Por exemplo, antes de realizar uma compra, um visitante em um site de comércio eletrônico precisaria acessar o carrinho de compras, a página de faturamento e envio, a página de pagamento e a página de revisão do pedido.

Na Analysis Workspace, esses dados podem ser exibidos usando a visualização de Fallout.

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Fallout para o espaço de trabalho acima da tabela de forma livre
2. Clique no ícone de componentes à esquerda e localize a dimensão **Páginas** .
3. Clique no ícone de seta ao lado da dimensão Páginas para revelar os valores da página. Os valores de dimensão têm cor amarela.
4. Localize a página desejada para agir como o primeiro ponto de contato e arraste-a para o espaço chamado 'Adicionar ponto de contato' na visualização.
5. Continue adicionando pontos de contato desejados arrastando os valores da página para a visualização.

A visualização de Fallout não está limitada apenas à dimensão Páginas. Qualquer dimensão, métrica ou segmento pode ser usada para adaptar seu relatório de fallout às necessidades de sua organização.

![Visualização da fallout](/help/technotes/ga-to-aa/assets/fallout.png)

## Relatórios de comércio eletrônico

Geralmente, os relatórios de comércio eletrônico são usados por sites que vendem produtos ou serviços para medir pedidos e receita de itens comprados. Esse recurso está disponível no Adobe Analytics e é conhecido como Relatórios de produtos.

Os relatórios de comércio eletrônico no Google Analytics e os relatórios de produto no Adobe Analytics exigem alterações de implementação personalizadas para serem usadas. Consulte a dimensão [Produtos](/help/components/c-variables/dimensionslist/reports-products.md) no guia do usuário Componentes para obter mais informações.

## Relatórios de funil de vários canais

Os relatórios de funil de vários canais fornecem dados adicionais de canal de marketing além do que os relatórios de aquisição fornecem. Esses relatórios se concentram em como os visitantes são convertidos, em vez de como os visitantes chegam ao site.

> [!NOTE]
>
> O uso de relatórios de vários canais no Adobe Analytics requer a configuração de Canais de marketing e uma implementação personalizada para acomodar a variável de produtos e o evento de compra. A Adobe recomenda trabalhar com um consultor de implementação se esses recursos ainda não estiverem configurados para seu conjunto de relatórios.

### Multicanal - Conversões assistidas

As conversões assistidas mostram quantas vezes cada canal assistiu a uma conversão. Na Analysis Workspace, a métrica Assistente de **pedidos** pode ser usada.

1. No menu Componentes, localize a dimensão do Canal **de** marketing e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste a métrica **Auxílio** de pedido para cima do cabeçalho de métrica **Ocorrências** criado automaticamente para substituí-la. Métricas adicionais podem ser arrastadas para o espaço de trabalho, se desejado.

### Multicanal - Principais caminhos de conversão

O relatório de principais caminhos de conversão mostra os principais caminhos de canal que um usuário segue antes da conversão. A Analysis Workspace usa um relatório de fluxo para visualizar os principais caminhos de conversão.

1. Clique no ícone Painéis à esquerda e arraste um painel Atribuição acima da tabela de forma livre.
2. Clique no ícone Componentes à esquerda, localize a dimensão do Canal **de** marketing e arraste-a para a caixa denominada 'Adicionar dimensão'.
3. Localize o evento de conversão desejado em Métricas (por exemplo, Pedidos) e arraste-o para a caixa denominada 'Adicionar métrica'. Observe que as métricas calculadas não são suportadas pelo painel Atribuição.
4. Clique em Construir.
5. No relatório resultante, localize a visualização 'Fluxo de canal'. Esse fluxo mostra os principais caminhos que um visitante tocou antes de uma compra.

Esta visualização de fluxo é interativa. Clique em cada canal para expandir o fluxo em ambas as direções.

![Visualização de fluxo](/help/technotes/ga-to-aa/assets/flow.png)

### Multicanal - Atraso de tempo

O relatório de desfasamento de tempo mostra o tempo em dias que um visitante levou para converter em seu site. Na Analysis Workspace, esses dados estão disponíveis usando a dimensão **Dias antes da primeira compra** . Ela só está disponível no contexto de um evento de compra implementado corretamente.

1. No menu Componentes, localize a dimensão **Dias antes da primeira compra** e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

A Adobe recomenda usar as métricas **Pedidos**, **Unidades** ou **Receita** com essa dimensão.

Para outros tipos de conversões, incluindo eventos personalizados, a dimensão **Tempo antes do evento** está disponível. Mostra o tempo, em minutos, necessário para um visitante acionar o evento na visita.

1. No menu Componentes, localize a dimensão **Tempo antes do evento** e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

A Adobe recomenda usar essa dimensão juntamente com eventos personalizados ou eventos de compra.

### Multicanal - Extensão do Caminho

O relatório de comprimento do caminho mostra o número de canais tocados antes de um evento de conversão. Na Analysis Workspace, o painel Atribuição contém esses dados em uma de suas visualizações.

1. Clique no ícone Painéis à esquerda e arraste um painel Atribuição acima da tabela de forma livre
2. Clique no ícone Componentes à esquerda, localize a dimensão do Canal **de** marketing e arraste-a para a caixa denominada 'Adicionar dimensão'.
3. Localize o evento de conversão desejado em Métricas (por exemplo, Pedidos) e arraste-o para a caixa denominada 'Adicionar métrica'. Observe que as métricas calculadas não são suportadas pelo painel Atribuição.
4. Clique em Construir.
5. No relatório resultante, localize a visualização "Pontos de contato por jornada". Este histograma mostra o número de canais que um visitante tocou antes de uma compra.
