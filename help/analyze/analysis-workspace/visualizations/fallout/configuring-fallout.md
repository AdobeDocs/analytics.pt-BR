---
description: Saiba como configurar e especificar os pontos de contato para criar uma sequência de fallout multidimensional.
title: Configurar Uma Visualização De Fallout
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
source-git-commit: 89cc33528d3907d955a543f3e43774a1065e149a
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 44%

---

# Configurar uma visualização de fallout

Você pode especificar os pontos de contato para criar uma sequência de fallout multidimensional. Geralmente, um ponto de contato é uma página do site. No entanto, os pontos de contato não estão limitados a páginas. Por exemplo, é possível adicionar eventos, como unidades, bem como usuários únicos e visitas de retorno. Também é possível adicionar dimensões, como uma categoria, tipo de navegador ou termo de pesquisa interna.

Você pode até mesmo adicionar segmentos em um ponto de contato. Por exemplo, você pode querer comparar segmentos, como usuários de iOS e Android™. Arraste os segmentos desejados para o topo do fallout e as informações sobre os segmentos serão adicionadas ao relatório de fallout. Se quiser exibir somente esses segmentos, é possível remover a linha de base Todas as visitas.

Não há limite para o número de etapas que é possível adicionar ou o número de dimensões usadas.

É possível definir o caminho em dimensões, métricas e segmentos. Por exemplo, suponha que alguém esteja pesquisando sapatos e camisetas em uma página e camisetas e meias na página seguinte. O próximo relatório de fluxo do produto para sapatos será camisetas e meias, e NÃO camisetas.

## Usar

1. Adicione uma visualização de ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL fallout]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Arraste um componente para o menu suspenso **[!UICONTROL Adicionar ponto de contato]**.

   Por exemplo, é possível adicionar uma única página ao relatório de fallout, em vez da dimensão inteira. Clique na seta para a direita ![ChevronRight](/help/assets/icons/ChevronRight.svg) na dimensão de página para escolher uma página específica, como **[!UICONTROL página inicial]**, para adicionar ao relatório de Fallout.

   ![A página inicial da dimensão Página inicial arrastada para o campo Adicionar ponto de contato.](assets/fallout-drag.png)

1. Continue a adicionar pontos de contato até concluir a sequência.

   Os números circulados, na área em cinza da barra, apresentam o fallout entre os pontos de contato (e não o fallout geral daquele ponto). A **[!UICONTROL % do ponto de contato]** apresenta o nível de sucesso ao passar da etapa anterior para a etapa atual no relatório de fallout.

   ![A Página:CamerRoll ou Página: pontos de contato da câmera destacados.](assets/fallout-or.png)

   Ao adicionar pontos de contato, siga um destes procedimentos:

   * Combine vários componentes arrastando um ou mais componentes adicionais em um único ponto de contato.

     >[!NOTE]
     >
     >Para unir vários segmentos, utilize o operador AND, mas para unir vários itens, como itens de dimensão e métricas, utilize OR.

   * Reordenar pontos de contato arrastando-os para um nível diferente na hierarquia de fallout.

   * Combine um ponto de contato com outro. Para combinar pontos de contato, arraste um ponto de contato para outro. Solte-o quando vir a palavra **[!UICONTROL Combinar]**.

     ![Combinar pontos de contato](assets/fallout-combine-touchpoints.png)

   * Restringir pontos de contato individuais ao próximo evento (em vez de *eventualmente*) dentro do caminho. Abaixo de cada ponto de contato, há um seletor com as opções **[!UICONTROL Caminho eventual]** e **[!UICONTROL Próximo evento]**, conforme mostrado aqui:

     ![A exibição Todas as visitas mostrando a opção Caminho eventual realçada.](assets/fallout-nexthit.png)

     | Opção | Descrição |
     |---|---|
     | **[!UICONTROL Caminho eventual]** (padrão) | São contados os visitantes que *eventualmente* chegarão à próxima página do caminho, mas não necessariamente no próximo evento. |
     | **[!UICONTROL Próximo evento]** | São contados os visitantes que chegarão à próxima página do caminho no próximo evento. |

   * Passe o mouse sobre um ponto de contato para ver o fallout e outras informações sobre esse nível. As informações incluem o nome do ponto de contato, a contagem de pessoas e a taxa de sucesso. Você também pode comparar a taxa de sucesso com outros pontos de contato.

     ![Dica de ferramenta do ponto de contato](assets/fallout-tooltip.png)


## Configurações 

Como parte da visualização, há configurações específicas disponíveis.

| Container de fallout | Descrição |
|--- |--- |
| **[!UICONTROL Sessão]** ou **[!UICONTROL Pessoa]** | Alterne entre [!UICONTROL Sessão] e [!UICONTROL Pessoa] para analisar a definição de caminho da pessoa. O padrão é [!UICONTROL Pessoa]. Essas configurações ajudam você a entender o engajamento de pessoas (em sessões) ou restringir a análise a uma única sessão. |


## Menu de contexto

Como parte da visualização, há opções específicas do menu de contexto disponíveis.

### Acessar o menu de contexto

Você pode acessar o menu de contexto de uma das seguintes maneiras:

* Passe o mouse sobre um ponto de contato na visualização e selecione **[!UICONTROL Clique para analisar]**.

  ![Acessar menu de contexto a partir do cursor](assets/fallout-tooltip-analyze.png)

* Clique com o botão direito do mouse em um ponto de contato na visualização.

  ![Opções de fallout](assets/fallout-options.png)

### Opções do menu de contexto

As seguintes opções de menu de contexto estão disponíveis:

| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Tendência de ponto de contato]** | Veja os dados de tendência de um ponto de contato em um gráfico de linha, com alguns dados de detecção de anomalias pré-construídos. |
| **[!UICONTROL Tendência de ponto de contato (%)]** | Calcula a tendência da porcentagem total de fallout. |
| **[!UICONTROL Tendência de todos os pontos de contato (%)]** | Exibe a tendência de todas as porcentagens de pontos de contato do fallout (exceto **[!UICONTROL Todas as pessoas]**, se incluso) no mesmo gráfico. |
| **[!UICONTROL Analisar fallthrough neste ponto de contato]** | Visualize o que os visitantes fizeram entre dois pontos de contato (este ponto de contato e o próximo ponto de contato), se continuaram até o próximo ponto de contato. Essa opção cria uma tabela de forma livre mostrando suas dimensões. É possível substituir dimensões e outros elementos da tabela. Por exemplo, uma tabela rotulada como **[!UICONTROL Fallthrough: Todos os visitantes > Página é igual a qualquer página inicial]** e contém **[!UICONTROL Página]** como a dimensão e **[!UICONTROL Visitantes únicos]** segmentado pelo [segmento rápido somente de projeto](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Fallthrough: Todos os visitantes > Página é igual a qualquer página inicial]** como a métrica. Inspecione o segmento para entender como o segmento de fallthrough é determinado. |
| **[!UICONTROL Fallout de detalhamento neste ponto de contato]** | Veja o que os visitantes que não passaram pela funnel fizeram imediatamente após a etapa selecionada. Essa opção cria uma tabela de forma livre mostrando suas dimensões. É possível substituir dimensões e outros elementos da tabela. Por exemplo, uma tabela rotulada como **[!UICONTROL Fallout: Todos os visitantes > Página é igual a qualquer página inicial]** e contém **[!UICONTROL Página]** como a dimensão e **[!UICONTROL Visitantes únicos]** segmentado pelo [segmento rápido somente de projeto](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Fallthrough: Todos os visitantes > Página é igual a qualquer um do segmento inicial]** como a métrica. Inspecione o segmento para entender como o segmento de fallout é determinado. |
| **[!UICONTROL Criar segmentos a partir do ponto de contato]** | Crie um novo segmento a partir do ponto de contato selecionado. |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto da visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

