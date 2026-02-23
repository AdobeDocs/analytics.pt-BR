---
description: Use a visualização de mapa para plotar dados em uma visualização de mapa geográfico.
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 62%

---

# Mapa {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Mapa"
>abstract="Essa visualização representa as métricas ao sobrepô-las em um mapa. Esta visualização é útil para identificar dados em diferentes áreas geográficas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Propagações"
>abstract="Marque eventos usando bolhas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Mapa de calor"
>abstract="Marcar eventos usando um mapa de calor."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo é sobre a visualização de mapa no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulte o [Mapa](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/map) da_ versão ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** deste artigo._

>[!ENDSHADEBOX]



A visualização de ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL mapa]** no Analysis Workspace

* permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas).
* é útil para identificar e comparar dados de métricas em diferentes regiões geográficas.
* permite o uso de duas fontes de dados: latitude e longitude para uso em dispositivos móveis ou dimensão geográfica para uso na web,
* é compatível com exportação de PDF e
* utiliza o WebGL para exibição de gráficos. Se os drivers gráficos não forem compatíveis com a renderização de WebGL, talvez seja necessário atualizá-los.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualização de mapa no Analysis Workspace](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/visualizations/map-visualization){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


## Usar

1. Adicionar uma visualização de ![Map](/help/assets/icons/Globe.svg) [!UICONTROL mapa]. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Só é possível arrastar uma visualização de mapa por cima de uma tabela de forma livre.

   ![Configuração do mapa](assets/map-configuration.png){width="50%"}

1. Nas listas suspensas, selecione uma métrica. Ou arraste uma métrica da lista de métricas (incluindo métricas calculadas).
1. Especifique a fonte de dados da qual deseja extrair. Esta caixa de diálogo é exibida apenas se o rastreamento de localização estiver habilitado para dados de aplicativos móveis.

   | Origem | Descrição |
   | --- | --- |
   | **[!UICONTROL Lat/long móveis]** | Esta opção representa dados do aplicativo móvel. Esta opção estará visível somente se tiver sido habilitada para o conjunto de relatórios em [!UICONTROL Analytics] > [!UICONTROL Administrador] > [!UICONTROL Conjuntos de relatórios] > (selecione o conjunto de relatórios) > [!UICONTROL Editar configurações] >  [!UICONTROL Gerenciamento de dispositivos móveis] > [!UICONTROL Habilitar rastreamento de localização]. Essas configurações são o padrão (se o rastreamento de localização estiver habilitado). |
   | **[!UICONTROL Dimensão geográfica]** | Esta opção representa dados de segmentação geográfica sobre a localização do visitante com base no endereço IP do visitante. Esses dados são transformados em [!UICONTROL País], [!UICONTROL Região] e [!UICONTROL Cidade]. Observe que eles não atingem o nível de DMA ou Código postal. Quase todos os conjuntos de relatórios têm essa dimensão ativada. Caso contrário, entre em contato com o Atendimento ao cliente da Adobe para ativar os relatórios geográficos. |

1. Selecione **[!UICONTROL Criar]**.

   Uma visualização do mapa-múndi com propagações é gerada.

   ![](assets/bubble-world-view.png)

1. Agora você pode:

   * **Aplique zoom** neste mapa para ampliar determinadas áreas clicando duas vezes no mapa ou usando a roda de rolagem. O mapa aumenta o zoom de acordo com onde você colocou o cursor. Por meio da interação do zoom, a dimensão necessária (país > estado > cidade) é atualizada automaticamente, com base no nível de zoom.
   * **Compare** duas ou mais visualizações de mapa no mesmo projeto, colocando-as lado a lado.
   * **Mostrar comparações período por período (como, ano por ano)**:

      * Mostrar números negativos: por exemplo, se você estiver plotando uma métrica ano a ano, o mapa poderá mostrar -33% sobre Nova York.
      * Com métricas do tipo *porcentagem*, o agrupamento calcula a média das porcentagens.
      * Um esquema de cor verde/vermelho: Positivo/Negativo

   * **Gire** o mapa em 2D ou 3D mantendo a tecla [!UICONTROL Ctrl] pressionada e movendo o mapa.

   * **Alternar** para um modo de exibição diferente, como o mapa de calor, usando as [configurações](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritas abaixo. Observe que a exibição em bolha é a configuração padrão.

1. **Salve** o projeto para salvar todas as configurações do mapa (coordenadas, zoom, rotação).
1. A tabela de forma livre, abaixo da visualização, pode ser preenchida por arrastar métricas e dimensões de localização do painel esquerdo para dentro dela.



## Configurar

Para reconfigurar a visualização de mapa, selecione ![Editar](/help/assets/icons/Edit.svg).


## Configurações 

Para definir configurações para a visualização, selecione ![Configuração](/help/assets/icons/Setting.svg).

| Configuração | Descrição |
|--- |--- |
| **[!UICONTROL Tipo de mapa]** | |
| **[!UICONTROL Bolhas] | Plota eventos usando bolhas. Um gráfico de bolhas é um gráfico de várias variáveis que é um cruzamento entre um gráfico de dispersão e um gráfico de área proporcional. Essa exibição é o padrão. |
| [!UICONTROL Mapa de calor] | Plota eventos usando um mapa de calor. Um mapa de calor é uma representação gráfica de dados em que os valores individuais contidos em uma matriz são representados como cores. |
| **[!UICONTROL Estilos]** | |
| [!UICONTROL Tema de cores] | Mostra o esquema de cores para o mapa de calor e bolhas. Você pode escolher entre Coral, Vermelhos, Verdes ou Azuis. O padrão é Coral. |
| [!UICONTROL Estilo do mapa] | É possível escolher entre Básico, Ruas, Brilhante, Claro, Escuro e Satélite. |
| **[!UICONTROL Raio do agrupamento]** | Agrupa os pontos de dados que estão dentro do número especificado de pixels. O padrão é 50. |
| **[!UICONTROL Valor máximo personalizado]** | Permite alterar o limite do valor máximo do mapa; alterar esse valor ajusta a escala dos valores de propagações e do mapa de calor (cor e tamanho) com relação ao valor máximo personalizado que foi definido. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/visualizations/build-a-time-parting-heatmap)

-->

