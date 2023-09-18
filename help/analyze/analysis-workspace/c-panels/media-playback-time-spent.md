---
title: Painel Tempo gasto com a reprodução da mídia
description: Como usar e interpretar o painel Tempo gasto com a reprodução de mídia no Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 9268baf7-b50b-4c09-a722-7bfcd4172f15
source-git-commit: 95f28d537e6e7538133ebd04d185ebcfd28a13d4
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 80%

---

# Painel Tempo gasto com a reprodução da mídia

No Analysis Workspace, o Tempo gasto com a reprodução é a quantidade de tempo gasto visualizando seus fluxos de mídia em um momento específico. Inclui pausa, buffer e hora de início.

O Tempo gasto com a reprodução da mídia ajuda na análise da reprodução ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar.

Os clientes do Media Analytics podem analisar o tempo de reprodução gasto para obter informações valiosas sobre a qualidade do conteúdo e o envolvimento do visualizador e para ajudar na solução de problemas ou no planejamento de volume ou escala.

O Tempo gasto com a reprodução pode ajudá-lo a entender:

* Em que ocorreu o pico de simultaneidade

* Onde as quedas ocorreram

Veja a seguir um vídeo com uma visão geral desse painel:

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Usar o painel Tempo gasto com a reprodução de mídia

1. Acesse um conjunto de relatórios com os componentes do Media Analytics ativados.
1. Selecione o ícone do painel na extremidade esquerda e arraste o painel para o projeto do Analysis Workspace.
1. Prossiga com as seções a seguir para personalizar o painel Tempo gasto com reprodução de mídia

   * [Entradas do painel](#panel-inputs)
   * [Saída do painel](#panel-output)

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

## Visualização padrão

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

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | A tabela de forma livre não está disponível nessa visualização. Você pode baixar a fonte de dados clicando com o botão direito do mouse no gráfico de linha e baixando o arquivo CSV. |
| Por que minha granularidade mudou? | Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar o intervalo de datas completo. <p>Ao alterar de um intervalo de datas maior para menor, a granularidade será atualizada para o detalhe mais baixo permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite o painel e recrie.</p> |
| Como comparar nomes de vídeo, segmentos, tipos de conteúdo etc.? | Para compará-los em uma única visualização, arraste segmentos, dimensões ou itens de dimensão específicos no filtro de detalhamento por séries. A exibição é limitada a 10 detalhamentos. Para exibir mais de 10, você deve usar vários painéis. |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas. Esses intervalos de datas substituirão o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | Esse painel permite somente a visualização de linha para a série de tempo. |
| Posso executar a detecção de anomalias? | Não. A detecção de anomalias não está disponível para esse painel. |
