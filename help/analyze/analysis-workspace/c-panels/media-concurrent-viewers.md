---
title: Painel de visualizadores simultâneos de mídia
description: Como usar e interpretar o painel Visualizadores simultâneos de mídia no Analysis Workspace.
feature: Painéis
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 12%

---


# Painel de visualizadores simultâneos de mídia

Os clientes do Media Analytics podem analisar visualizadores simultâneos para entender onde ocorreu o pico de simultaneidade ou onde ocorreram quedas, para fornecer informações valiosas sobre a qualidade do conteúdo e engajamento do visualizador e para ajudar na solução de problemas ou no planejamento de volume ou escala.

No Analysis Workspace, Visualizadores simultâneos é o número de visitantes únicos que visualizam seus fluxos de mídia em um ponto específico do tempo, independentemente do número de sessões.

O painel Visualizadores simultâneos de mídia permite a análise de visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar.  Para acessar o painel Visualizadores simultâneos de mídia, navegue até um conjunto de relatórios com os componentes do Media Analytics ativados. Em seguida, clique no ícone do painel na extremidade esquerda e arraste o painel para o projeto do Analysis Workspace.

## Entradas do painel {#Input}

Você pode configurar o painel Visualizadores simultâneos de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| Intervalo de datas do painel | O padrão do intervalo de datas do painel é Hoje.  Você pode editá-la para visualizar um único dia ou muitos meses de cada vez. <br> <br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar o intervalo de datas completo. |
| Granularidade | O padrão de granularidade é Minuto. <br> <br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar o intervalo de datas completo. |
| Números de resumo do painel | Para visualizar os detalhes de data ou hora de visualizadores simultâneos, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O Mínimo mostra detalhes para o vale.  O padrão do painel mostra Somente máximo, mas você pode alterá-lo para mostrar Mínimo ou Máximo e Mínimo.<br><br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| Desagregação por séries | Como opção, você pode detalhar sua visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas. <br><br>- É possível visualizar até 10 linhas por vez. Os detalhamentos são limitados a um único nível.<br><br>- Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.<br><br>- Para comparar intervalos de datas, arraste 2 ou mais intervalos de datas para o filtro de detalhamento de séries. |

### Exibição padrão

![Exibição padrão](assets/concurrent-viewers-default.png)


### Exibição de detalhamento de séries

![exibição de detalhamento de séries](assets/concurrent-viewers-series-breakdown.png)

## Saída do painel {#Output}

O painel Visualizadores simultâneos de mídia retorna um gráfico de linha e números de resumo para incluir detalhes para o máximo e/ou mínimo de visualizadores simultâneos.  Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou.

A qualquer momento, você pode editar e recriar o painel clicando no lápis de edição na parte superior direita.

Se você selecionou o detalhamento da série, uma linha no gráfico de linha e um número de resumo é exibida para cada:

![saída de visualizadores simultâneos](assets/concurrent-viewers-output.png)

### Fonte de dados

A única métrica que pode ser usada neste painel são Visualizadores simultâneos:

| Métrica | Descrição |
|---|---|
| Visualizadores simultâneos | Número de visitantes únicos que visualizam seus fluxos de mídia em um ponto específico do tempo, independentemente do número de sessões.<br><br>Isso é diferente dos relatórios do Visualizador simultâneo na seção Relatórios, que usa Sessões ativas simultâneas.  O uso de contas de visitantes únicos para remover &quot;picos&quot; indesejados em mostrar limites (onde as sessões estão terminando e iniciando ao mesmo tempo). |

Uma tabela de forma livre não está disponível nesta exibição.  Para visualizar a fonte de dados, clique com o botão direito do mouse no gráfico de linha e baixe como um arquivo .csv .  As desagregações das séries serão incluídas.


![saída de visualizadores simultâneos](assets/concurrent-viewers-download-csv.png)

## Perguntas frequentes {#FAQ}

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | A tabela de forma livre não está disponível nesta exibição.  Você pode baixar a fonte de dados clicando com o botão direito do mouse no gráfico de linha e baixando o arquivo CSV. |
| Por que minha granularidade mudou? | Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar o intervalo de datas completo.<br><br>Ao alterar de um intervalo de datas maior para menor, a granularidade será atualizada para o detalhe mais baixo permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite o painel e recrie. |
| Como faço para comparar nomes de vídeo, segmentos, tipos de conteúdo etc? | Para compará-los em uma única visualização, arraste segmentos, dimensões ou itens de dimensão específicos no filtro de detalhamento da série.<br><br>A exibição é limitada a 10 detalhamentos.  Para visualizar mais de 10, você deve usar vários painéis. |
| Como faço para comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos de série arrastando 2 ou mais intervalos de data.  Esses intervalos de datas substituirão o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | Esse painel permite somente a visualização de linha para a série de tempo. |
| Posso executar a detecção de anomalias? | Não.  A detecção de anomalias não está disponível para este painel. |
| Por que usar visitantes únicos em vez de sessões ativas? | O uso de visitantes únicos permite a remoção de picos indesejados nos limites da exibição (onde as sessões estão terminando e começando ao mesmo tempo). |
| O que significa ter visualizadores simultâneos com maior granularidade do que um minuto? | Com uma granularidade maior que um minuto, visualizadores simultâneos é a soma de visualizadores simultâneos exclusivos para todos os minutos dentro desse intervalo de tempo.  Por exemplo, visualizadores simultâneos de granularidade em nível de hora é a soma de visualizadores simultâneos exclusivos para todos os minutos da hora. |
| E se eu quiser ver mais de um dia na granularidade de nível de minuto? | Para acessar os dados em granularidade de nível minuto por até 1 mês por vez, use as APIs do Analytics 2.0. Para obter mais informações, consulte [Obter dados de relatório JSON de visualizadores simultâneos com APIs do Analytics 2.0](https://docs.adobe.com/content/help/en/media-analytics/using/media-reports/media-default-reports/get-concurrent-json20.html). |
| O painel Espaço de trabalho mostra as mesmas informações que o Relatório de visualizadores simultâneos? | Não.  No Analysis Workspace, Visualizadores simultâneos é definido como o número de visitantes únicos que visualizam seu fluxo de mídia em um ponto específico do tempo, independentemente do número de sessões.<br><br>Isso é diferente dos relatórios do Visualizador simultâneo na seção Relatórios, que usa Sessões ativas simultâneas.  Usar contas de visitantes únicos para remover picos indesejados em mostrar limites, onde as sessões estão terminando e iniciando ao mesmo tempo. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
