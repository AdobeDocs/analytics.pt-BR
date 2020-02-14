---
title: Relatórios de aquisição no Adobe Analytics
description: Saiba como criar relatórios baseados em aquisição usando a Analysis Workspace.
translation-type: tm+mt
source-git-commit: 2e3896501a036e20f9f392c325e0c8ff1d586fba

---


# Relatórios de aquisição

Os relatórios de aquisição mostram como você obtém visitantes do site.

No Adobe Analytics, esses relatórios são conhecidos como Canais **de marketing**. Eles exigem alguma configuração inicial básica, mas permitem uma exibição muito mais personalizada dos canais.

> [!IMPORTANT]
>
> Configure suas regras de processamento do Canal de marketing para usar esses relatórios. Consulte [Introdução aos Canais](/help/components/c-marketing-channels/c-getting-started-mchannel.md) de marketing para obter informações sobre como configurar melhor os Canais de marketing em sua organização.

Esta página supõe que o usuário tenha um conhecimento básico sobre o uso da Analysis Workspace. Consulte [Criar um relatório básico na Analysis Workspace para usuários](create-report.md) do Google Analytics se você ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Todo o tráfego - Canais

Mostra uma exibição agregada de todos os canais que os visitantes usam para acessar seu site.

1. No menu Componentes, localize a dimensão do Canal **de** marketing e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

## Todo o tráfego - Mapeamentos de árvores

Mostra um mapa de tráfego de canal. Este relatório é semelhante a Todos os Tráfego - Canais, mas é mostrado de uma forma diferente.

1. Clique no ícone Visualizações à esquerda e arraste a visualização do Mapa de árvore para a área de trabalho acima da tabela de forma livre vazia.
2. Clique no ícone Componentes à esquerda e arraste a dimensão **Canal** de marketing para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
3. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.
4. Observe que métricas adicionais criam mapas de árvore adicionais. Se apenas um mapa de árvore for desejado:
   1. Clique na célula superior da métrica desejada para representar o mapa de árvore.
   2. Clique com a tecla Shift pressionada na última célula da mesma coluna de métrica para realçar a coluna azul. Se feito corretamente, um mapa de árvore está presente na visualização.
   3. Clique no ponto colorido no canto superior direito da visualização do mapa de árvore e clique na caixa de seleção &#39;Bloquear seleção&#39;.

Os mapas de árvore podem ser aplicados a qualquer dimensão, não apenas aos Canais de marketing.

## Todo o tráfego - Origem/Médio

Relatórios de origem e médio mostram os domínios que levaram o tráfego para o site.

* A dimensão principal **Origem** está disponível na Analysis Workspace como a dimensão Domínio **de** referência.
* A dimensão principal **Média** está disponível na Analysis Workspace como a dimensão Tipo **de** referenciador.
* A dimensão principal **Palavra-chave** está disponível na Analysis Workspace como a dimensão **Pesquisar palavra-chave** .

1. No menu de componentes, localize a dimensão desejada anotada acima e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte as seguintes páginas no guia do usuário Componentes para obter mais informações sobre suas respectivas dimensões:

* [Domínio de referência](/help/components/c-variables/dimensionslist/reports-referring-domains.md)
* [Tipo de referenciador](/help/components/c-variables/dimensionslist/reports-ref-types.md)
* [Palavra-chave de pesquisa](/help/components/c-variables/dimensionslist/reports-search-keywords.md)

## Todo o tráfego - Referências

* A dimensão principal **Origem** está disponível na Analysis Workspace como a dimensão Domínio **de** referência.
* A dimensão principal da Página **de** aterrissagem está disponível na Analysis Workspace como a dimensão da Página **de** entrada.

1. No menu de componentes, localize a dimensão Domínio **de** referência ou Página **de** entrada e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão Domínio [](/help/components/c-variables/dimensionslist/reports-referring-domains.md) de referência no guia do usuário Componentes para obter mais informações.

## Relatórios do Google Ads e do Console de pesquisa

A Adobe usa um recurso na Analysis Workspace chamado Advertising Analytics para trazer dados de publicidade e pesquisa de várias plataformas, incluindo o Google.

O recurso de análise de publicidade exige configuração para retornar os dados. Consulte a Ajuda [do](/help/integrate/c-advertising-analytics/overview.md) Advertising Analytics para obter detalhes sobre como ativar essas dimensões adicionais na Analysis Workspace.

## Relatórios Social 

Os relatórios sociais fornecem informações semelhantes ao relatório Comportamento respectivo, exceto no contexto das redes sociais. Esses dados estão disponíveis na Analysis Workspace ao combinar uma dimensão com um segmento.

Às vezes, os visitantes chegam ao site por meio de vários canais na mesma sessão. Por exemplo, um visitante clica em uma página de mídia social e alguns minutos depois visita um mecanismo de pesquisa para acessar seu site. Nesses casos, domínios não sociais podem aparecer neste relatório. Se você deseja excluir domínios não sociais, classifique o relatório por visitas ou crie uma cópia do segmento para ser baseada em ocorrências em vez de visitas. See [Segmentation Containers](/help/components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social - Referências de rede

O relatório Referências de rede mostra quais domínios de rede social direcionaram o tráfego para o site. Esses dados estão disponíveis na Analysis Workspace usando a dimensão Domínio **de** referência e o segmento **Visitas de sites** sociais.

1. No menu Componentes, localize a dimensão Domínio **** de referência e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. No menu Componentes, localize o segmento **Visitas de sites** sociais e arraste para a pequena área acima da tabela de forma livre chamada &#39;Solte um segmento aqui&#39;.
3. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

### Social - Páginas de aterrissagem

O relatório de Páginas iniciais mostra em quais páginas os visitantes chegaram depois de clicar em um link por meio de uma rede social. Esses dados estão disponíveis na Analysis Workspace usando a dimensão Página **de** entrada e o segmento **Visitas de sites** sociais.

1. No menu Componentes, localize a dimensão Página **de** entrada e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. No menu Componentes, localize o segmento **Visitas de sites** sociais e arraste para a pequena área acima da tabela de forma livre chamada &#39;Solte um segmento aqui&#39;.
3. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

### Social - Conversões

O relatório de Conversões mostra dados de comércio eletrônico no contexto das redes sociais. É necessária uma implementação adicional para usar esses relatórios em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados estejam configurados corretamente para a Analysis Workspace.

### Social - Plug-ins

O relatório Plug-ins mostra como os visitantes interagem com plug-ins de mídia social incorporados em seu site. A implementação adicional é necessária para uso na Analysis Workspace. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados sejam coletados com precisão.

### Social - Fluxo de usuários

O relatório de fluxo Usuários mostra os dados de definição de caminho no contexto de visitantes que chegam por uma rede social.

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Fluxo para o espaço de trabalho acima da tabela de forma livre
2. Clique no ícone Componentes à esquerda e arraste o segmento **Visitas de sites** sociais para a pequena área logo acima da visualização de fluxo chamada &#39;Soltar um segmento aqui&#39;.
3. Localize a dimensão **Páginas** e clique no ícone Seta para revelar os valores da página. Os valores de dimensão têm cor amarela.
4. Localize o valor da página desejada para começar e arraste-o para o espaço chamado &#39;Dimensão ou item&#39; no centro
5. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

## Campanhas - Todas

O relatório de campanhas está disponível na Analysis Workspace usando a dimensão Código **de** rastreamento. Observe que o uso da dimensão Código de rastreamento requer implementação adicional para coletar dados.

É possível coletar parâmetros de UTM no Adobe Analytics usando variáveis personalizadas (eVars). A Adobe recomenda trabalhar com um consultor de implementação para garantir que os valores do código de rastreamento sejam coletados com precisão no Adobe Analytics.

1. No menu Componentes, localize a dimensão Código **de** rastreamento e arraste-a até a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

## Campanhas - Palavras-chave pagas

O relatório de palavras-chave pagas mostra o desempenho de cada palavra-chave depois que um visitante clica em um link de pesquisa pago de um mecanismo de pesquisa. A dimensão Palavras-chave de **pesquisa - Pagas** está disponível na Analysis Workspace, mas requer uma configuração única da detecção de pesquisa paga para coletar dados. Consulte Detecção [de pesquisa](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga no Guia do usuário de administração para obter detalhes sobre a configuração.

1. No menu Componentes, localize a dimensão Palavra-chave de **pesquisa - Paga** e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

## Campanhas - Palavras-chave orgânicas

O relatório de palavras-chave orgânicas mostra o desempenho de cada palavra-chave depois que um visitante clica em um link de pesquisa orgânico de um mecanismo de pesquisa. Palavras-chave de **pesquisa - A dimensão Natural** está disponível na Analysis Workspace. Observe que se a detecção de pesquisa paga não estiver configurada, essa dimensão coleta palavras-chave pagas e naturais.

1. No menu Componentes, localize a dimensão Palavra-chave de **pesquisa - Natural** e arraste-a para a grande área da tabela de forma livre chamada &#39;Solte uma dimensão aqui&#39;.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

## Análise de custo

Este relatório mostra os dados de desempenho de visita, custo e receita para seus canais de marketing pagos. A Adobe fornece um produto dedicado para fornecer insight chamado Adobe Advertising Cloud. Se sua organização estiver interessada em usar este produto, entre em contato com o Gerente de conta de sua organização.
