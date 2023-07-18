---
description: Use a visualização de fluxo em um projeto do Espaço de trabalho.
title: Configurar uma visualização de fluxo
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
source-git-commit: d1c2966bfd7cb5e397de23adf45bb38fca34e416
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 62%

---

# Configurar uma visualização de fluxo

As Visualizações de fluxo ajudam você a entender a jornada decorrente ou que leva a um evento de conversão específico em seu site ou aplicativo. Ela rastreia um caminho pelas suas dimensões (e itens de dimensão) ou métricas.

As visualizações de fluxo permitem configurar o início ou o fim do caminho em que você está interessado ou analisar todos os caminhos que fluem por uma dimensão ou item de dimensão.

![Nova interface de usuário de fluxo](assets/new-flow.png)

## Criar uma visualização de fluxo {#configure}

1. Adicione um painel em branco ao projeto e clique no ícone de visualizações no painel à esquerda.

   Ou

   Adicione uma visualização de qualquer uma das maneiras descritas na seção &quot;Adicionar visualizações a um painel&quot; no [Visão geral das visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Ancore a visualização de Fluxo usando uma das seguintes opções:

   * [!UICONTROL **Começa com**] (métricas, dimensões ou itens) ou
   * [!UICONTROL **Contém**] (dimensões ou itens), ou
   * [!UICONTROL **Termina com**] (métricas, dimensões ou itens)

   Cada uma dessas categorias é mostrada na tela como uma “área”. É possível preencher a área de lançamento de 3 maneiras:

   * Use o menu suspenso para selecionar métricas ou dimensões.
   * Arraste dimensões ou métricas do painel esquerdo.
   * Comece digitando o nome de uma dimensão ou métrica e selecione-a quando ela aparecer na lista suspensa.

   >[!IMPORTANT]
   >
   >Métricas calculadas não podem ser usadas na variável  **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]** campos.

1. Se você escolher uma métrica, também precisará fornecer uma [!UICONTROL **Definição de caminho do Dimension**] para usar como o caminho conduzindo ou saindo do componente selecionado, como mostrado aqui. O padrão é [!UICONTROL **Página**].

   ![Dimensão de definição de caminho](assets/pathing-dim.png)

1. (Opcional) Selecione **[!UICONTROL Mostrar configurações avançadas]** para configurar qualquer uma das seguintes opções:

   ![configurações avançadas](assets/adv-settings.png)

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Rótulos de quebra de linha]** | Normalmente, os rótulos nos Elementos de fluxo são truncados para não poluir visualmente a tela, mas é possível tornar todos os rótulos visíveis ao selecionar esta caixa.  Padrão = desmarcado. |
   | **[!UICONTROL Incluir instâncias repetidas]** | As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas, por exemplo, recarregamentos de página. No entanto, as repetições não podem ser removidas das Visualizações de fluxo que incluem dimensões com vários valores, como listVars, listProps, s.product, eVars de merchandising etc. <p>Essa opção está desativada por padrão.</p> |
   | **[!UICONTROL Limite para a primeira/última ocorrência]** | Limite os caminhos para aqueles que começam/terminam com a primeira/última ocorrência de uma dimensão/item/métrica. Consulte a seção abaixo, [Exemplo de cenário para &quot;limitar à primeira/última ocorrência&quot;](#example-scenario-for-limit-to-firstlast-occurrence), para obter uma explicação mais detalhada. |
   | **[!UICONTROL Número de colunas]** | O número de colunas desejado no diagrama de Fluxo. |
   | **[!UICONTROL Itens expandidos por coluna]** | O número de itens desejado em cada coluna. |
   | **[!UICONTROL Container de fluxo]** | <ul><li>Visita</li><li>Visitante</li></ul> Permite alternar entre Visita e Visitante para analisar a definição do caminho do visitante. Essas configurações ajudam você a entender o envolvimento no nível dos visitantes (ao longo das visitas) ou restringir a análise a uma só visita. |

1. Selecionar **[!UICONTROL Build]**.

>[!INFO]
>
>**Exemplo:** Suponha que você queira rastrear o caminho que os usuários tomaram para e das páginas mais populares do site.
>
>Para fazer isso, você
>1. Comece a criar uma visualização de fluxo conforme descrito acima.
>1. Arraste o [!UICONTROL **Página**] dimensão na **[!UICONTROL Contém]** e selecione [!UICONTROL **Build**].
>1. A visualização de Fluxo é criada com a página mais visualizada visível no nó de foco no centro da visualização. Você também pode ver as principais páginas que entram nessa página (à esquerda do nó de foco), bem como as principais páginas que saem dessa página de foco (à direita do nó de foco).
>1. Analise os dados no fluxo, conforme descrito em [Exibir e alterar a saída do Fluxo](#view-and-change-the-flow-output).


## Exibir e alterar a saída do fluxo {#output}

![saída do fluxo](assets/flow-output.png)

Um resumo da configuração de fluxo é exibido na parte superior do diagrama. A espessura de um caminho no diagrama é proporcional à sua atividade, com caminhos com mais atividade aparecendo mais grossos do que aqueles com menos atividade.

Para detalhar ainda mais os dados, você tem várias opções:

* O diagrama de fluxo é interativo. Passe o mouse sobre o diagrama para alterar os detalhes exibidos.

* Quando você seleciona em um nó no diagrama, os detalhes dele são exibidos. Selecione no nó novamente para recolhê-lo.

  ![node-details](assets/node-details.png)

* É possível filtrar uma coluna para exibir apenas determinados resultados, como incluir e excluir, especificar critérios e assim por diante.

* Selecione o sinal de mais (+) à esquerda para expandir uma coluna.

* Use as opções de clique com o botão direito explicadas abaixo para personalizar ainda mais a saída.

* Selecione o ícone de lápis ao lado do resumo da configuração para editar ainda mais o fluxo ou recriá-lo com opções diferentes.

* Além disso, é possível exportar e analisar posteriormente o diagrama de Fluxo como parte de um arquivo .CSV de um projeto. Basta ir até **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**.

## Filtragem

Acima de cada coluna, um filtro é exibido quando você passa o mouse sobre ele. Ao selecionar o filtro, você obtém a mesma caixa de diálogo de filtro que existe na tabela de Forma livre hoje. Esse filtro funciona da mesma forma que na tabela de Forma livre.

* Use as configurações avançadas para incluir ou excluir determinados critérios com nossa lista de operadores.
* Depois de filtrar um item da lista, essa coluna específica refletirá a filtragem. O filtro o reduz para mostrar apenas o item permitido no filtro, ou remove todos os itens, exceto o item que você deseja no filtro.
* Todas as colunas downstream e upstream devem persistir, desde que haja dados fluindo para os nós restantes.
* Depois de aplicado, o ícone de filtro aparece em azul acima da coluna em que está filtrando.
* Para remover um filtro, selecione o ícone de filtro para abrir o menu de filtro. Remova os filtros aplicados e selecione **[!UICONTROL Salvar]**. O fluxo deve retornar ao estado anterior e não filtrado.

## Opções de clique com o botão direito do mouse {#right-click}

| Opção | Descrição |
|--- |--- |
| [!UICONTROL Recomeçar] | Retomar ao criador de diagrama de Forma livre, no qual você pode criar um novo diagrama de Fluxo. |
| [!UICONTROL Criar segmento para este caminho] | Criar um segmento. Isso leva você ao Construtor de segmentos, onde você pode configurar o novo segmento. |
| [!UICONTROL Detalhamento] | Detalhe o nó por Dimensões, Métricas ou Tempo disponíveis. |
| [!UICONTROL Tendência] | Crie um diagrama de tendências para o nó. |
| Mostrar próxima coluna / Mostrar coluna anterior | Revela a próxima coluna (direita) ou a coluna anterior (esquerda) da visualização. |
| Ocultar coluna | Oculta a coluna selecionada da visualização. |
| [!UICONTROL Expandir toda a coluna] | Expanda uma coluna para exibir todos os nós. Por padrão, somente os cinco principais nós são exibidos. |

## Exemplo de cenário para “limitar à primeira/última ocorrência”

Ao usar essa opção, lembre-se de que:

* **[!UICONTROL Limitar à primeira/última ocorrência]** conta somente a primeira/última ocorrências na série. Todas as outras ocorrências dos critérios **[!UICONTROL Começa com]** ou **[!UICONTROL Termina com]** são descartados.
* Se usada com um fluxo **[!UICONTROL Começa com]**, somente a primeira ocorrência que corresponde aos critérios de início é incluída.
* Se usada com um fluxo **[!UICONTROL Termina com]**, somente a última ocorrência que corresponde aos critérios finais será incluída.
* As séries utilizadas diferem de acordo com o container. Se estiver usando o container **[!UICONTROL Visita]**, a série de ocorrências será a sessão. Se estiver usando o container **[!UICONTROL Visitante]**, a série de ocorrências será todas as ocorrências de um determinado usuário no intervalo de datas fornecido.
* A opção **[!UICONTROL Limitar à primeira/última ocorrência]** pode ser definida nas configurações avançadas ao usar uma Métrica ou Item de dimensão nos campos “Inicia com” ou “Termina com”.

Exemplo de série de ocorrências:

Início > Produtos > Adicionar ao carrinho > Produtos > Adicionar ao carrinho > Faturamento > Confirmação de pedido

### Considere uma análise de fluxo usando as seguintes configurações:

* Comece com[!UICONTROL  Adicionar ao carrinho] (Item de dimensão)
* Dimensão da definição de caminho de [!UICONTROL Página] 
* Container de [!UICONTROL Visita]

Se a opção **[!UICONTROL Limitar à primeira/última ocorrência]** estiver *desativada*, essa única série de ocorrências contará duas ocorrências de “Adicionar ao carrinho”.
Saída de fluxo esperada:
“Adicionar ao carrinho” (2) —> “Produtos” (1)
-> “Faturamento” (1)

No entanto, se a opção **[!UICONTROL “Limitar à primeira/última ocorrência”]** estiver *ativada*, somente a primeira ocorrência de “Adicionar ao carrinho” será incluída na análise.
Saída de fluxo esperada:
“Adicionar ao carrinho” (1) —> “Produtos” (1)

### Considere a mesma série de ocorrências, mas use as seguintes configurações:

* Termina com [!UICONTROL Adicionar ao carrinho] (Item de dimensão)
* Dimensão da definição de caminho de [!UICONTROL Página]
* Container de [!UICONTROL Visita]

Se a opção **[!UICONTROL Limitar à primeira/última ocorrência]** estiver *desativada*, essa única série de ocorrências contará duas ocorrências de “Adicionar ao carrinho”.
Saída de fluxo esperada:
“Produtos” (2) &lt;— “Adicionar ao carrinho” (2)

No entanto, se a opção **[!UICONTROL Limitar à primeira/última ocorrência]** está *ativada*, somente a última ocorrência de [!UICONTROL Adicionar ao carrinho] seria incluída na análise.
Saída de fluxo esperada:
“Produtos” (1) &lt;— “Adicionar ao carrinho” (1)
