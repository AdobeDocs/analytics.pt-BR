---
description: As configurações de linha variam de acordo com qual componente foi arrastado para a tabela.
title: Configurações de linha
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Freeform Tables
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: a3b6f3ce85003d0a8f3139a66a6cbcf953089d15
workflow-type: ht
source-wordcount: '1045'
ht-degree: 100%

---


# Configurações de linha


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurações de linha e coluna em uma tabela de forma livre](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

As configurações de linha variam de acordo com qual componente foi arrastado para a tabela. Para acessar as configurações de linha da tabela, selecione ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Configurações]** ao lado de uma dimensão, filtro, métrica, período ou detalhamento em cada um desses objetos.

![Tabela de forma livre com destaque para o ícone de Configurações de métricas](assets/row-settings.png)

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Detalhamento por posição]** | Por padrão, essa configuração é desativada e os detalhamentos são corrigidos em itens de linha estáticos. Por exemplo, imagine que você detalhou os três principais itens de dimensão de página (Página inicial, Resultados de pesquisa, Check-out) por canal de marketing. Você sai do projeto e retorna duas semanas depois. Ao abrir o projeto novamente, as 3 principais páginas foram alteradas e, agora, a Página inicial, os Resultados da pesquisa e o Check-out são as 4 a 6 principais páginas. Por padrão, os detalhamentos do canal de marketing ainda aparecerão em Página inicial, Resultados de pesquisa e Check-out, mesmo que agora estejam nas linhas 4-6. <br> Por outro lado, o **Detalhamento por posição** sempre detalha os três primeiros itens, independentemente do que sejam. Voltando ao exemplo, ao reabrir o projeto, os detalhamentos do canal de marketing são vinculados às três principais páginas da tabela. E não a Página inicial, Resultados de pesquisa e Check-out, que agora estão nas linhas 4-6. |
| **[!UICONTROL Porcentagens]** | **Calcular porcentagens por coluna** (padrão): as porcentagens visíveis em uma célula são calculadas com base no total da coluna. <br>**Calcular porcentagens por linha**: as porcentagens em células são calculadas pela linha, em vez de ao longo da coluna, com o Total geral como o denominador. Esse cálculo é útil para criar uma tendência de porcentagens. |
| **[!UICONTROL Totais de colunas]** | Essas configurações estão disponíveis somente para [linhas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostrar como soma das linhas atuais** exibe uma soma das linhas da tabela do lado do cliente, o que significa que o total *não* removerá a duplicação de métricas, como visitas ou pessoas. <br> **Mostrar total geral** exibe uma soma do lado do servidor, que representa o total das métricas desduplicadas. |

## Alterar contagem de linhas

Para alterar o número de linhas exibidas:

1. Clique no número ao lado de **[!UICONTROL Linhas]** na parte superior da primeira coluna da tabela.

   ![Tabela de forma livre mostrando a lista suspensa para o número de linhas exibidas. Há 400 linhas selecionadas.](assets/change-row-count.gif)

1. Na lista suspensa, selecione o número de linhas que deseja que a tabela exiba.


## Menu de contexto

As opções de menu de contexto a seguir estão disponíveis ao selecionar o cabeçalho da dimensão.

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Copiar seleção para a área de transferência]** | Copia a seleção da visualização para a área de transferência. |
| **[!UICONTROL Baixar itens como CSV (*nome da dimensão*)]** | Baixe imediatamente os itens de dimensão (até um máximo de 50.000) da visualização para o dispositivo local. Há um limite de 50.000 itens de dimensão para a dimensão selecionada. |
| **[!UICONTROL Baixar seleção como CSV]** | Baixe imediatamente os itens de dimensão da visualização para o dispositivo local. |
| **[!UICONTROL Criar hiperlinks para todos os itens de dimensão]** | Cria hiperlinks para todos os itens de dimensão. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Editar hiperlinks de todos os itens de dimensão]** | Edita hiperlinks em todos os itens de dimensão. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remover hiperlinks de todos os itens de dimensão]** | Remove hiperlinks de todos os itens de dimensão. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Excluir]** | Exclui a dimensão da tabela. |
| **[!UICONTROL Visualizar]** | Visualize a dimensão usando qualquer uma das visualizações disponíveis. |
| **[!UICONTROL Exibir somente as linhas selecionadas]** | Exibe somente os itens selecionados na visualização. |
| **[!UICONTROL Criar anotação a partir da seleção]** | Abre os **[!UICONTROL detalhes da anotação]** para adicionar uma anotação. |


As opções adicionais de menu de contexto a seguir estão disponíveis ao selecionar um ou mais itens de dimensão (primeira coluna) ou uma ou mais células individuais na tabela de forma livre.

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Criar hiperlink]** | Cria um hiperlink para o item. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Editar hiperlink]** | Edita um hiperlink do item. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remover hiperlink]** | Remove um hiperlink do item. Consulte [Hiperlinks para dimensões em uma tabela de forma livre](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Detalhamento]** | Detalha o item de dimensão. Selecione na lista de **[!UICONTROL Dimensões]**, **[!UICONTROL Métricas]**, **[!UICONTROL Filtros]** ou **[!UICONTROL Intervalos de datas]**. Para realizar uma pesquisa alternativa de um componente, utilize *Pesquisa*. |
| **[!UICONTROL Excluir selecionados]** | Excluir as linhas (itens) selecionadas. |
| **[!UICONTROL Seleção de tendências]** | Cria uma visualização de gráfico de linhas de tendência para a seleção. |
| **[!UICONTROL Exibir somente as linhas selecionadas]** | Exibe somente as linhas selecionadas na visualização. |
| **[!UICONTROL Exibir todas as linhas]** | Exibe todas as linhas na visualização. |
| **[!UICONTROL Criar filtro a partir da seleção]** | Abre o **[!UICONTROL Construtor de filtros]** para criar um filtro a partir da seleção. |
| **[!UICONTROL Criar público-alvo a partir da seleção]** | Abre a caixa de diálogo **[!UICONTROL Criar público-alvo]** para criar um público-alvo a partir da seleção. |

As opções adicionais de menu de contexto a seguir estão disponíveis ao selecionar um cabeçalho de coluna de métrica.

| Opção | Descrição |
|---|---|
| **[!UICONTROL Criar métrica a partir da seleção]** | Cria uma nova métrica a partir da métrica selecionada. A métrica pode ser Média, Mídia, Máximo da coluna, Mínimo da coluna, Soma da coluna. Também é possível selecionar Abrir no criador de métricas calculadas para criar uma métrica calculada. |
| **[!UICONTROL Adicionar coluna de período]** | Adiciona uma coluna de período. Há várias opções disponíveis, e o intervalo do calendário do painel determina o *intervalo de datas*: <li>**[!UICONTROL *Intervalo de datas* anterior até este intervalo de datas]**</li><li>**[!UICONTROL Esses *intervalos de datas* até este intervalo de datas]**.</li><li>**[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]**. Abre o **[!UICONTROL Construtor de intervalos de datas]** para especificar o intervalo de datas.</li>Consulte [Comparação de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md) para obter mais informações. |
| **[!UICONTROL Comparar períodos]** | Adiciona colunas de comparação de períodos. Disponível somente quando a dimensão não é baseada em tempo. São oferecidas várias opções que determinam o *intervalo de datas*: <li>**[!UICONTROL *Intervalo de datas* anterior até este intervalo de datas]**</li><li>**[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]**. Abre o **[!UICONTROL Construtor de intervalos de datas]** para especificar o intervalo de datas.</li>Consulte [Comparação de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md) para obter mais informações. |
| **[!UICONTROL Modificar modelos de atribuição]** | Permite modificar o modelo de atribuição da coluna. |
| **[!UICONTROL Comparar modelo de atribuição]** | Permite especificar um novo modelo de atribuição e compará-lo ao modelo de atribuição da coluna selecionada. Uma nova coluna é adicionada com as métricas do novo modelo de atribuição. Além disso, uma coluna de Variação porcentual é adicionada para comparação. |
| **[!UICONTROL Redefinir larguras de coluna]** | Redefine as larguras das colunas para a largura padrão. |
| **[!UICONTROL Criar anotação a partir da seleção]** | Abre os **[!UICONTROL detalhes da anotação]** para adicionar uma anotação. |
| **[!UICONTROL Criar filtro a partir da seleção]** | Abre o **[!UICONTROL Construtor de filtros]** para criar um filtro a partir da seleção. |
| **[!UICONTROL Criar público-alvo a partir da seleção]** | Abre a caixa de diálogo **[!UICONTROL Criar público-alvo]** para criar um público-alvo a partir da seleção. |

## Modificar altura da linha

Você pode definir a densidade da exibição de um projeto como **[!UICONTROL Compacta]**, **[!UICONTROL Confortável]** e **[!UICONTROL Expandida]**. [Saiba mais](/help/analyze/analysis-workspace/build-workspace-project/view-density.md).
