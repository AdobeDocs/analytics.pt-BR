---
description: 'null'
seo-description: 'null'
seo-title: Otimizar o desempenho da Workspace
title: Otimizar o desempenho da Workspace
uuid: de 51 d 03 d-d 555-4 f 0 e-b 19 c -4 a 8 f 140770 fc
translation-type: tm+mt
source-git-commit: 4c400faacdc0cc405f719cb849ed02d03b0cf972

---


# Otimizar o desempenho da Workspace

Certos fatores podem influenciar o desempenho de um projeto na Analysis Workspace. É importante saber quais são os contribuidores antes de iniciar a criação de um projeto, para que possa planejar e criar o projeto da melhor forma. Abaixo segue uma lista de fatores que impactarão o desempenho e as práticas recomendadas para a otimização do seu projeto. O desempenho da Analysis Workspace é uma das prioridades da Adobe e algo que aprimoramos a cada dia.

## Complexidade da lógica de segmentos

Segmentos intricados podem ter um impacto significativo no desempenho do projeto. Fatores que adicionam complexidade a um segmento (em ordem decrescente de impacto) incluem:

* Operadores de “contém”, “contém qualquer um de”, “corresponde”, “começa com” ou “termina com”
* Segmentação sequencial, especialmente quando restrições de dimensão (Dentro/Depois de) são usadas
* Número de itens de dimensão exclusivos em dimensões usadas no segmento (por exemplo, Página = 'A' quando a Página tem 10 itens exclusivos será mais rápida que a Página = 'A' quando a Página tiver 100000 itens exclusivos)
* O número de diferentes dimensões usadas (por exemplo, Página = 'Página inicial' e Página = 'Resultados da pesquisa') será mais rápido que eVar 1 = 'vermelho' e eVar 2 = 'azul')
* Muitos operadores OR (em vez de AND)
* Recipientes aninhados que variam no escopo (por exemplo, Ocorrência dentro de Visita dentro de Visitante)

### Prática recomendada

Embora alguns dos fatores de complexidade não possam ser evitados, pense em oportunidades para reduzir a complexidade de seus segmentos. Em geral, quanto mais específico você puder ser com os critérios do seu segmento, melhor. Por exemplo:

* Com contêineres, usar um só contêiner na parte superior do segmento será mais rápido que uma série de contêineres aninhados.
* Com operadores, "igual" será mais rápido que "contém" e "igual a qualquer um" será mais rápido que "contém qualquer um".
* Com muitos critérios, operadores AND serão mais rápidos que uma série de operadores OR. Além disso, procure oportunidades para reduzir muitas instruções OR em uma instrução "igual a qualquer um".

Além disso, [classificações](/help/components/c-classifications2/c-classifications.md) podem ajudar a consolidar muitos valores em grupos concisos a partir dos quais você pode criar segmentos. A segmentação nos grupos de classificação oferece benefícios de desempenho em segmentos que contêm muitas instruções OR ou que contêm o critério “contêm”.

## Intervalo de dados solicitado

O intervalo de dados solicitado no decorrer do projeto influenciará o desempenho da Analysis Workspace.

### Prática recomendada

Quando possível, não inserir mais dados que o necessário.

Lembre-se de que os intervalos de data (componentes em roxo) substituem o painel de intervalo de data. Como resultado, caso esteja utilizando os intervalos de data como colunas (por exemplo, colunas de último mês, última semana e de ontem), o painel de intervalo de data não precisa abranger as colunas de intervalos de data. Pode simplesmente ser definido para ontem, porque os intervalos de data usados na tabela de forma livre substituirão o painel. Para mais informações sobre o uso de intervalos de data na Analysis Workspace, assista [este vídeo](https://www.youtube.com/watch?v=ybmv6EBmhn0) .

Use [date comparison options](../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764) to pull in the specific time periods of data you want to compare. Por exemplo. caso precise mostrar os dados do mês passado comparados aos do mesmo mês do ano passado, ao invés de configurar o painel para os últimos 13 meses de dados, simplesmente use a opção de comparação de períodos de tempo para apresentar o desempenho de ano por ano.

## Número de visualizações

O número de visualizações de gráfico contidas em um projeto afetará a capacidade geral de resposta da Analysis Workspace.

### Prática recomendada

Diminua o número de visualizações em seu projeto. A Analysis Workspace está fazendo diversas transformações nos bastidores em cada visual que você adiciona, sendo assim, priorize os visuais mais importantes para o consumidor do relatório e separe visuais de suporte em um projeto mais detalhado, caso necessário.

## Complexidade de visualizações (segmentos, métricas, filtros)

O tipo de visualização (por exemplo, fallout ou tabela de forma livre) adicionado a um projeto sozinho não influencia muito o desempenho do projeto. É a complexidade da visualização que aumentará o tempo de processamento. Fatores que adicionam complexidade à visualização incluem:

* Intervalo de dados solicitados, como mencionado acima
* Números de segmentos aplicados, por exemplo, segmentos usados como linhas de uma tabela de forma livre
* Uso de segmentos intricados
* Linhas ou colunas de itens estáticas em tabelas de forma livre
* Filtros aplicados a linhas em tabelas de forma livre
* Número de métricas incluídas, métricas especialmente calculadas que usam segmentos

### Prática recomendada

Caso note que seus projetos não estão carregando rápido como gostaria, tente substituir alguns segmentos por eVars e filtros, quando possível.

Caso perceba estar constantemente utilizando segmentos e métricas calculadas para pontos de dados importantes para o seu negócio, considere aprimorar sua implementação para capturar estes pontos de dados de forma mais direta. O uso de um gerenciador de tags como o Adobe Experience Platform Launch e as regras de processamento da Adobe pode fazer alterações de implementação rápidas e fáceis de implementar. Para entender melhor como simplificar segmentos complexos, consulte “Complexidade da lógica de segmento” acima.

## Número de painéis

Um painel pode conter diversas visualizações e, como resultado, o número de painéis também pode influenciar a capacidade geral de resposta da Analysis Workspace.

### Prática recomendada

Não tente adicionar tudo a um só projeto e, sim, criar projetos distintos que atendam a um propósito ou grupo de participantes específico. Use as tags para organizar projetos em temas chave e compartilhe projetos relacionados com grupos de participante.

Caso deseje mais organização nos projetos, lembre-se de que a [vinculação direta](https://www.youtube.com/watch?v=6IOEewflG2U) ao seu projeto é uma opção. Crie um índice interno de projetos de forma que os participantes possam encontrar o que precisam mais facilmente. Além disso, a Adobe está sempre procurando trazer mais opções de organização para a Analysis Workspace.

Caso necessite de muitos painéis em uma área de trabalho, reduza os painéis antes de salvar e compartilhar. Quando um projeto é carregado, a Analysis Workspace somente carregará o conteúdo dos painéis expandidos. Os painéis reduzidos não serão carregados até que o usuário os expanda. Essa abordagem auxilia de duas formas:

* Os painéis reduzidos são salvos em um tempo de carregamento geral de um projeto
* Os painéis reduzidos são uma boa forma de organizar seus projetos de maneira lógica para o consumidor do relatório

## Tamanho do conjunto de relatórios

O tamanho do conjunto de relatórios pode parecer um fator determinante, na realidade, porém, ele representa um pequeno papel no desempenho do projeto devido a como a Adobe trata o processamento de dados

## Número de pessoas acessando a Analysis Workspace neste momento

O número de pessoas acessando a Analysis Workspace ou projetos específicos ao mesmo tempo não tem um efeito significativo no desempenho da Analysis Workspace.