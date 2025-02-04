---
description: Especifique os pontos de contato para criar uma sequência de fallout multidimensional.
title: Configurar uma visualização de fallout
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
source-git-commit: be6056f9e7a64b47ab544594149ebfbe134f1c04
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 34%

---

# Configurar uma visualização de fallout

Você pode especificar os pontos de contato para criar uma sequência de fallout multidimensional. Geralmente, um ponto de contato é uma página no seu site. Contudo, pontos de contato não estão limitados a páginas. Por exemplo, você pode adicionar eventos, como unidades, bem como pessoas únicas e visitas de retorno. Você também pode adicionar dimensões, como uma categoria, tipo de navegador ou termo de pesquisa interno.

Você também pode adicionar segmentos em um ponto de contato. Por exemplo, você pode querer comparar segmentos, como usuários do iOS e do Android™. Arraste os segmentos desejados para o topo do fallout e as informações sobre os segmentos são adicionadas ao relatório de fallout. Se quiser mostrar apenas esses segmentos, você pode remover a linha de base Todas as visitas.

Não há limitação no número de etapas que podem ser adicionadas ou no número de dimensões usadas.

Você pode definir a definição de caminho em dimensões, métricas e segmentos. Por exemplo, suponha que alguém esteja pesquisando sapatos e camisetas em uma página e camisetas e meias em outra. O próximo relatório de fluxo do produto para sapatos será camisetas e meias, e NÃO camisetas.

## Usar

1. Adicione uma visualização de ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Arraste uma página, por exemplo, página inicial, da dimensão Página para o menu suspenso *Adicionar ponto de contato*.

   ![A página inicial da dimensão Página inicial arrastada para o campo Adicionar Ponto de Contato.](assets/fallout-drag.png)

   Passe o mouse sobre um ponto de contato para ver o fallout e outras informações sobre o nível, como o nome do ponto de contato e a contagem de pessoas no ponto. E veja a taxa de sucesso desse ponto de contato (bem como compare a taxa de sucesso com outros pontos de contato).

   Os números circulados, na área em cinza da barra, apresentam o fallout entre os pontos de contato (e não o fallout geral daquele ponto). O **[!UICONTROL ponto de contato %]** mostra o fallthrough bem-sucedido da etapa anterior para a etapa atual no relatório de fallout.

   É possível adicionar uma única página ao relatório de fallout, ao invés de uma dimensão inteira. Clique na seta para a direita ![ChevronRight](/help/assets/icons/ChevronRight.svg) na dimensão de página para escolher uma página específica para adicionar ao relatório de Fallout.

1. Continue a adicionar pontos de contato até concluir a sequência.

   Você pode **combinar vários pontos de contato** arrastando um ou mais componentes adicionais para um ponto de contato.

   >[!NOTE]
   >
   >Vários segmentos são unidos com AND, mas vários itens, como itens de dimensão e métricas, são unidos com OR.

   ![Página:CamerRoll ou Página: pontos de contato de câmera destacados.](assets/fallout-or.png)

1. Você também pode **restringir pontos de contato individuais ao próximo evento** (em vez de *eventualmente*) dentro do caminho. Sob cada ponto de contato, há um seletor com as opções **[!UICONTROL Caminho eventual]** e **[!UICONTROL Próximo evento]**, conforme mostrado aqui:

   ![O modo de exibição Todas as Visitas mostrando a opção Caminho Eventual foi realçado. ](assets/fallout-nexthit.png)

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Caminho eventual]** (padrão) | São contadas as pessoas que *eventualmente* aparecerão na próxima página do caminho, mas não necessariamente no próximo evento. |
   | **[!UICONTROL Próximo evento]** | São contados os que serão direcionados para a próxima página no caminho no próximo evento. |


## Configurações 

Como parte da visualização, configurações específicas estão disponíveis.

| Contêiner de fallout | Descrição |
|--- |--- |
| **[!UICONTROL Sessão]** ou **[!UICONTROL Pessoa]** | Alterne entre [!UICONTROL Sessão] e [!UICONTROL Pessoa] para analisar a definição de caminho da pessoa. O padrão é [!UICONTROL Pessoa]. Essas configurações ajudam você a entender o engajamento de pessoas (em sessões) ou restringir a análise a uma única sessão. |


## Menu de contexto

Como parte da visualização, opções específicas do menu de contexto estão disponíveis.

![Opções de fallout](assets/fallout-options.png)

| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Ponto de contato de tendência]** | Veja os dados de tendência para um ponto de contato em um gráfico de linha, com alguns dados de detecção de anomalias pré-construídos. |
| **[!UICONTROL Ponto de contato de tendência (%)]** | Executa a tendência da porcentagem total de fallout. |
| **[!UICONTROL Colocar todos os pontos de contato em tendência (%)]** | Exibe a tendência de todas as porcentagens dos pontos de contato no fallout (exceto **[!UICONTROL Todas as pessoas]**, se incluído), no mesmo gráfico. |
| **[!UICONTROL Analisar fallthrough neste ponto de contato]** | Visualize o que as pessoas fizeram entre dois pontos de contato (este ponto de contato e o próximo ponto de contato), se continuaram até o próximo ponto de contato. Isso cria uma tabela de forma livre, mostrando suas dimensões. Você pode substituir dimensões e outros elementos da tabela. |
| **[!UICONTROL Analisar fallout neste ponto de contato]** | Veja o que as pessoas que não entraram no funil fizeram imediatamente depois da etapa selecionada. |
| **[!UICONTROL Criar segmento a partir do ponto de contato]** | Crie um novo segmento a partir do ponto de contato selecionado. |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

