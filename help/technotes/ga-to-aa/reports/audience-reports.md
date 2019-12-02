---
title: Relatórios de público-alvo no Adobe Analytics
description: Saiba como criar relatórios baseados no público-alvo usando a Analysis Workspace.
translation-type: tm+mt
source-git-commit: 6217430bf0ae9c0f9c6426e4bb2a8101257068e7

---


# Relatórios de público-alvo

Os relatórios de público-alvo mostram informações sobre os tipos de pessoas que visitam seu site.

Esta página supõe que o usuário tenha um conhecimento básico sobre o uso da Analysis Workspace. Consulte [Criar um relatório básico na Analysis Workspace para usuários](create-report.md) do Google Analytics se você ainda não estiver familiarizado com a ferramenta no Adobe Analytics.

## Usuários ativos

Os usuários ativos mostram o número cumulativo de usuários do site nos 1, 7, 14 ou 28 dias anteriores. Embora a Adobe não tenha o cálculo exato usado no Google Analytics, você pode usar a métrica Visitantes únicos para ver uma contagem desduplicada de usuários no site com base no intervalo de datas selecionado.

Para obter um gráfico de linhas de visitantes únicos:

1. Clique no ícone Visualizações à esquerda e arraste a visualização de Linha para a área de trabalho acima da tabela de forma livre vazia.
2. Clique no ícone Componentes à esquerda e arraste a métrica Visitantes **** únicos para o espaço menor chamado 'Solte uma métrica aqui'.
3. Se desejar uma granularidade diferente, arraste o intervalo de datas desejado (por exemplo, **Dia**, **Semana**, **Mês** etc.) na parte superior do cabeçalho da dimensão de data existente.

Consulte Visitantes [](/help/components/c-variables/c-metrics/metrics-unique-visitors.md) únicos no guia do usuário Componentes para obter detalhes sobre como a Adobe calcula visitantes únicos.

## Valor de tempo de vida

O valor da vida útil é um recurso que requer implementação especializada adicional em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para obter esses dados.

## Análise de coorte

A Análise de coorte mostra a frequência com que os mesmos usuários retornam ao site.

Para criar uma tabela de coorte:

1. Clique no ícone Visualização à esquerda e arraste a visualização da Tabela de coorte para a área de trabalho.
2. Clique no ícone Componentes à esquerda e arraste a métrica **Visitas** para os Critérios de inclusão e de retorno.
3. Clique em Construir.

Consulte Análise [de](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) coorte no guia do usuário da Analysis Workspace para obter detalhes sobre personalizações adicionais para a visualização de coorte.

## Públicos-alvo

O relatório de Públicos-alvo no Google Analytics requer a configuração de públicos-alvo. Os públicos-alvo também exigem configuração na Adobe por meio do Adobe Audience Manager. Consulte o guia do usuário do Adobe Audience Manager para obter mais informações.

## Explorador de usuários

O relatório do Explorador de usuários permite que um analista visualize visitas individuais por meio de identificadores anônimos. A Adobe não exibe os identificadores de backend fora dos feeds de dados, que são exportações brutas de dados no nível de ocorrência.

* Se esses dados forem desejados na Analysis Workspace, é possível trabalhar com um consultor de implementação para passar o valor do cookie identificador único anônimo para uma eVar. Observe que isso só funciona com implementações menores, consistindo em menos de 1 milhão de visitantes únicos por mês.
* Se esses dados forem desejados nos feeds de dados, as colunas concatenadas `visid_high` e `visid_low` são a maneira mais comum de identificar visitantes únicos. Saiba mais sobre os Feeds [de](/help/export/analytics-data-feed/data-feed-overview.md) dados no guia do usuário Exportar.

## Relatórios de demografia e interesses

Os dados demográficos e de interesses fornecem informações sobre a idade, o gênero e os interesses dos usuários do site. Esses dados são coletados pelo Google através de suas habilidades de rastreamento entre sites.

Dados demográficos e de interesse não são coletados automaticamente pela Adobe. No entanto, se sua organização obtiver esses dados, você poderá usar Atributos do cliente, um recurso na plataforma da Adobe Experience Cloud. Permite o controle total da organização de dados por atributos, e não se limita a apenas demografia ou interesses.

Consulte a Ajuda dos atributos do cliente para obter mais informações.

## Geo - Idioma

O relatório de idioma geográfico mostra o tráfego do site pela configuração de idioma no navegador do visitante.

Para criar um relatório de idioma:

1. No menu Componentes, localize a dimensão **Idioma** e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão [Idioma](/help/components/c-variables/dimensionslist/reports-languages.md) no guia do usuário Componentes para obter mais informações.

## Geo - Localização

O relatório de localização geográfica fornece uma exibição de mapa mundial, dividindo dados por país.

Para criar um relatório de localização geográfica:

1. Clique no ícone Visualizações à esquerda e arraste a visualização do Mapa para a área de trabalho acima da tabela de forma livre vazia.
2. Clique no ícone Componentes à esquerda e arraste a métrica Visitantes **** únicos para o espaço chamado 'Adicionar métrica'.
3. Clique em Construir.

Se a tabela também for desejada além do mapa:

1. No menu Componentes, localize a dimensão **Países** e arraste-a até a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte Dimensões de [segmentação](/help/components/c-variables/dimensionslist/reports-geosegmentation.md) geográfica no guia do usuário Componentes para obter mais informações.

## Comportamento - Novo vs Retorno

O relatório novo vs recorrente oferece uma visualização simplificada das primeiras sessões (novas visitas) vs. sessões subsequentes (visitas de retorno).

Para criar um novo relatório de visitas vs. retorno:

1. No menu de componentes, localize o segmento Visitas **pela** primeira vez e arraste-o para a grande área da tabela de forma livre chamada 'Soltar uma dimensão aqui'. Observe que **primeiras visitas** é um segmento, enquanto o Workspace normalmente usa dimensões para representar linhas.
2. Localize o segmento Visitas **de** retorno e arraste-o para a parte superior do cabeçalho da linha Segmentos. Isso adiciona o segmento como uma dimensão abaixo de Primeiras visitas, permitindo uma comparação fácil.
3. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Se um gráfico de linha também for desejado:

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Linha para o espaço de trabalho acima da tabela de forma livre
2. Use ctrl+clique (Windows) ou cmd+clique (Mac) em cada linha na tabela de forma livre para realçá-los. Isso permite que ambas as tendências apareçam na visualização de linha.
3. Clique no pequeno ponto colorido arredondado no canto superior esquerdo da visualização de linha e clique na caixa de seleção 'Bloquear seleção'.

## Comportamento - Frequência e Idade

O relatório de frequência e recenticidade é aproximadamente igual à dimensão Número **de** visitas na Analysis Workspace.

1. No menu de componentes, localize a dimensão Número **de** visitas e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão Número [da](/help/components/c-variables/dimensionslist/reports-visitor-number.md) visita no guia do usuário Componentes para obter mais informações.

## Comportamento - Envolvimento

O relatório de envolvimento é aproximadamente igual à dimensão **Tempo gasto por visita - Classificado** .

1. No menu de componentes, localize a dimensão **Tempo gasto por visita - Classificado** e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão [Tempo gasto por visita](/help/components/c-variables/dimensionslist/reports-time-spent-per-visit.md) no guia do usuário Componentes para obter mais informações.

## Tecnologia - Navegador e SO

Há várias dimensões principais disponíveis no relatório Navegador e SO.

* A dimensão principal **do Navegador** também está disponível na Analysis Workspace como uma dimensão.
* A dimensão principal do Sistema **** Operacional também está disponível na Analysis Workspace como uma dimensão.
* A dimensão principal de Resolução **de** tela está disponível na Analysis Workspace como a dimensão Resolução **do** monitor.
* A dimensão principal de Cores **de** tela está disponível na Analysis Workspace como a dimensão Profundidade **de** cor.
* A dimensão principal da versão **do** Flash não está disponível no Adobe Analytics, no entanto, esses dados podem ser coletados por uma eVar, se desejado.

1. No menu de componentes, localize a dimensão desejada anotada acima e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte as seguintes páginas no guia do usuário Componentes para obter mais informações sobre suas respectivas dimensões:

* [Navegador](/help/components/c-variables/dimensionslist/reports-browsers.md)
* [Sistema operacional](/help/components/c-variables/dimensionslist/reports-operating-system.md)
* [Resolução do Monitor](/help/components/c-variables/dimensionslist/reports-technology.md)
* [Intensidade de cor](/help/components/c-variables/dimensionslist/reports-color-depth.md)

## Tecnologia - Rede

O relatório de rede é aproximadamente igual à dimensão **Domínio** .

1. No menu de componentes, localize a dimensão **Domínio** e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão [Domínio](/help/components/c-variables/dimensionslist/reports-domains.md) no guia do usuário Componentes para obter mais informações.

## Dispositivo móvel - Visão geral

O relatório de visão geral móvel é aproximadamente igual à dimensão Tipo **de dispositivo** móvel. Observe que o valor "Outros" equivale ao tráfego de desktop.

1. No menu de componentes, localize a dimensão Tipo **de dispositivo** móvel e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão Tipo [de dispositivo](/help/components/c-variables/dimensionslist/reports-device-types.md) móvel no guia do usuário Componentes para obter mais informações.

## Dispositivos móveis

O relatório de dispositivos móveis é aproximadamente igual à dimensão Dispositivo **** móvel.

1. No menu de componentes, localize a dimensão Dispositivo **** móvel e arraste-a para a grande área da tabela de forma livre chamada 'Solte uma dimensão aqui'.
2. Arraste as métricas desejadas para o espaço de trabalho ao lado da métrica **Ocorrências** criada automaticamente. Consulte o guia [de tradução de](common-metrics.md) métricas para obter detalhes sobre como obter cada métrica respectiva.

Consulte a dimensão Dispositivo [](/help/components/c-variables/dimensionslist/reports-devices.md) móvel no guia do usuário Componentes para obter mais informações.

## Personalizado

Os relatórios personalizados são definidos com base em cada implementação. Trabalhe com o administrador do Analytics e/ou consultor de implementação de sua organização para interpretar esses relatórios. Normalmente, uma organização mantém um Documento [de design de](/help/implement/prepare/solution-design.md) solução para rastrear os valores de variáveis personalizadas e como eles são preenchidos.

## Análise comparativa

Os relatórios de Benchmarking permitem que você veja como as facetas dos seus dados se comparam às médias do setor. A Adobe não compartilha dados de benchmarking entre seus clientes no momento.

## Fluxo de usuários

O relatório de fluxo está disponível em ambas as plataformas. Para criar um relatório de fluxo:

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Fluxo para o espaço de trabalho acima da tabela de forma livre
2. Localize a dimensão **Páginas** e clique no ícone Seta para revelar os valores da página. Os valores de dimensão têm cor amarela.
3. Localize o valor da página desejada para começar e arraste-o para o espaço chamado 'Dimensão ou item' no centro
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.
