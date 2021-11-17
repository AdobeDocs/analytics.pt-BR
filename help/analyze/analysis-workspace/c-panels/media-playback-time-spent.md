---
title: Painel Tempo gasto com a reprodução da mídia
description: Como usar e interpretar o painel Tempo gasto com a reprodução de mídia no Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 6347601c5c1b8e84f37db308717799dea43bd26d
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 99%

---

# Painel Tempo gasto com a reprodução da mídia

Os clientes do Media Analytics podem analisar o tempo de reprodução gasto para entender onde ocorreu o pico de simultaneidade ou onde ocorreram quedas para fornecer insights valiosos sobre a qualidade do conteúdo e o engajamento do visualizador e para ajudar na solução de problemas ou no planejamento de volume ou escala.

Esta é uma visão geral em vídeo do painel:

>[!VIDEO](https://video.tv.adobe.com/v/338699/?quality=12&learn=on)

No Analysis Workspace, o Tempo gasto com a reprodução é a quantidade de tempo gasto visualizando os fluxos de mídia em um momento específico e inclui os períodos de pausa, buffer e tempo para iniciar.

O Tempo gasto com a reprodução da mídia ajuda na análise da reprodução ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar. Para acessar o painel Tempo gasto com a reprodução da mídia, navegue até um conjunto de relatórios com os componentes do Media Analytics ativados. Em seguida, clique no ícone do painel na extremidade esquerda e arraste o painel para o Projeto do Analysis Workspace.

Esse painel também inclui uma nova funcionalidade no calendário, que permite selecionar e exibir menos de 24 horas. Você pode fazer isso para todo o painel ou pode criar segmentos usando períodos consecutivos para rastrear a entrada/saída de visualizações em programas ou seções de programas. Depois de colocar pelo menos dois desses segmentos de data, você verá um botão de opção para Exibição de sequência de data, que sobreporá as linhas com um início comum do eixo x ou exibirá em sequência com seu início específico do eixo x.

## Entradas do painel {#Input}

Você pode configurar o painel Tempo gasto com a reprodução de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| Intervalo de datas do painel | O padrão do intervalo de datas do painel é Hoje. Você pode editá-lo para exibir um único dia ou muitos meses de cada vez.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Granularidade | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Números de resumo do painel | Para visualizar os detalhes de data ou hora do tempo gasto com a reprodução, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O Mínimo mostra detalhes para o vale. O total soma o tempo total gasto com a reprodução para a seleção. O padrão do painel mostra somente o Máximo, mas você pode alterá-lo para mostrar Mínimo, Total ou qualquer combinação dos três.<br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| Detalhamento por séries | Como opção, você pode detalhar sua visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas.<p>- É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.</p><p>- Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.</p>- Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o filtro de detalhamento por séries. |
| Formato de tempo | Você pode visualizar o tempo gasto com a reprodução em Horas:Minutes:Segundos (padrão) ou em Minutos (que é exibido em números inteiros, arredondados para .5). |
| Exibição da sequência de data | Se você tiver colocado pelo menos dois segmentos de intervalo de datas como detalhamentos de séries, verá a opção de selecionar sobreposição (padrão) ou sequencial. A sobreposição exibirá as linhas com um início comum do eixo x para que sejam executadas em paralelo, enquanto as sequenciais exibirão as linhas com seu início específico do eixo x. Se os dados se alinharem (por exemplo, o segmento 1 termina às 20h44 e o segmento 2 começa às 20h45), as linhas serão exibidas em sequência. |

### Visualização padrão

![Visualização padrão](assets/mpts_default_view.png)

## Saída do painel {#Output}

O painel Tempo gasto com a reprodução de mídia retorna um gráfico de linhas e números de resumo para incluir detalhes sobre o tempo máximo, mínimo e/ou a soma do tempo gasto com a reprodução. Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou.

A qualquer momento, você pode editar e reconstruir o painel clicando no lápis de edição na parte superior direita.

Se você selecionou o detalhamento por séries, uma linha no gráfico de linha e um número de resumo é exibida para cada:

![saída do tempo gasto com a reprodução de mídia](assets/mpts_outputs1.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é Tempo gasto com a reprodução.

| Métrica | Descrição |
|---|---|
| Tempo gasto com a reprodução | Total de horas:minutes:segundos (ou minutos) do conteúdo exibido durante a granularidade selecionada, incluindo pausa, buffer e tempo para iniciar. |

## Perguntas frequentes {#FAQ}

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | <p></p><p>A tabela de forma livre não está disponível nessa visualização. Você pode baixar a fonte de dados clicando com o botão direito do mouse no gráfico de linha e baixando o arquivo CSV.</p> |
| <p>Por que minha granularidade mudou?</p> | <p>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar o intervalo de datas completo.</p><p></p><p>Ao alterar de um intervalo de datas maior para menor, a granularidade será atualizada para o detalhe mais baixo permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite o painel e recrie.</p> |
| <p></p><p>Como comparar nomes de vídeo, segmentos, tipos de conteúdo etc.?</p> | <p>Para compará-los em uma única visualização, arraste segmentos, dimensões ou itens de dimensão específicos no filtro de detalhamento por séries.</p><p></p><p>A visualização é limitada a 10 detalhamentos. Para exibir mais de 10, você deve usar vários painéis.</p> |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas. Esses intervalos de datas substituirão o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | <p></p><p>Esse painel permite somente a visualização de linha para a série de tempo.</p> |
| Posso executar a detecção de anomalias? | <p></p><p>Não. A detecção de anomalias não está disponível para esse painel.</p> |
