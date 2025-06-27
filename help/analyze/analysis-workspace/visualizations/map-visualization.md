---
description: Use a visualização de mapa para plotar dados em uma visualização de mapa geográfico
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 97%

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

_Este artigo é sobre a visualização de mapa no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Atualmente, não há uma visualização de mapa disponível no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]



A visualização de ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL mapa]** no Analysis Workspace

* permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas).
* é útil para identificar e comparar dados de métricas em diferentes regiões geográficas.
* permite o uso de duas fontes de dados: latitude e longitude para uso em dispositivos móveis ou dimensão geográfica para uso na web,
* é compatível com exportação de PDF e
* utiliza o WebGL para exibição de gráficos. Se os drivers gráficos não forem compatíveis com a renderização de WebGL, talvez seja necessário atualizá-los.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualização de mapa no Analysis Workspace](https://video.tv.adobe.com/v/30791/?quality=12&captions=por_br){target=&#34;_blank&#34;} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


## Usar

1. Adicionar uma visualização de ![Map](/help/assets/icons/Globe.svg) [!UICONTROL mapa]. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Só é possível arrastar uma visualização de mapa por cima de uma tabela de forma livre.

   ![Configuração do mapa](assets/map-configuration.png){width="50%"}

1. Nas listas suspensas, selecione uma métrica. Ou arraste uma métrica da lista de métricas (incluindo métricas calculadas).
1. Especifique a fonte de dados da qual deseja extrair. Esta caixa de diálogo é exibida apenas se o rastreamento de localização estiver habilitado para dados de aplicativos móveis.

   | Origem | Descrição |
   | --- | --- |
   | **[!UICONTROL Lat/long móveis]** | Esta opção representa dados do aplicativo móvel. Esta opção estará visível somente se tiver sido habilitada para o conjunto de relatórios em [!UICONTROL Analytics] > [!UICONTROL Administrador] > [!UICONTROL Conjuntos de relatórios] > (selecione o conjunto de relatórios) > [!UICONTROL Editar configurações] >  [!UICONTROL Gerenciamento de dispositivos móveis] > [!UICONTROL Habilitar rastreamento de localização]. Essas configurações são o padrão (se o rastreamento de localização estiver habilitado). |
   | **[!UICONTROL Dimensão geográfica]** | Esta opção representa dados de segmentação geográfica sobre a localização do visitante com base no endereço IP do visitante. Esses dados são transformados em [!UICONTROL País], [!UICONTROL Região] e [!UICONTROL Cidade]. Observe que eles não atingem o nível de DMA ou Código postal. Quase todos os conjuntos de relatórios têm essa dimensão ativada. Se o seu não tiver, entre em contato com o Atendimento ao cliente da Adobe para ativar os relatórios geográficos. |

1. Selecione **[!UICONTROL Criar]**.

   Uma visualização do mapa-múndi com propagações é gerada.

   ![](assets/bubble-world-view.png)

1. Agora você pode:

   * **Aplicar zoom** neste mapa para aumentar determinadas áreas ao clicar duas vezes no mapa ou usar a roda de rolagem. O zoom do mapa muda conforme a localização do cursor. Por meio da interação de zoom, a dimensão necessária (país > estado > cidade) é automaticamente atualizada, de acordo com o nível de zoom.
   * **Comparar** duas ou mais visualizações de mapa no mesmo projeto ao colocá-las lado a lado.
   * **Mostrar comparações periódicas (anuais (year-over-year), por exemplo)**:

      * Mostrar números negativos: por exemplo, se estiver traçando uma métrica anual, o mapa pode apresentar -33% em Nova York.
      * Com métricas do tipo *porcentagem*, o agrupamento calcula a média das porcentagens.
      * Um esquema de cores verde/vermelho: Positivo/Negativo

   * **Girar** o mapa em 2D ou 3D ao manter pressionada a tecla [!UICONTROL Ctrl] e mover o mapa.

   * **Alternar** para uma exibição diferente, como mapa de calor, usando as [configurações](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritas abaixo. Observe que a exibição de propagação é a configuração padrão.

1. **Salve** o projeto para salvar todas as configurações do mapa (coordenadas, zoom, rotação).
1. A tabela de forma livre, abaixo da visualização, pode ser preenchida por arrastar métricas e dimensões de localização do painel esquerdo para dentro dela.



## Configurar

Para reconfigurar a visualização de mapa, selecione ![Editar](/help/assets/icons/Edit.svg).


## Configurações 

Para definir configurações para a visualização, selecione ![Configuração](/help/assets/icons/Setting.svg).

| Configuração | Descrição |
|--- |--- |
| **[!UICONTROL Tipo de mapa]** | |
| **[!UICONTROL Bolhas] | Faz a plotagem de eventos usando propagações. Um gráfico de propagação é um gráfico de muitas variáveis, que é um cruzamento entre um gráfico de dispersão e um gráfico de área proporcional. Essa exibição é o padrão. |
| [!UICONTROL Mapa de calor] | Faz a plotagem de eventos usando um mapa de calor. Um mapa de calor é uma representação gráfica de dados onde os valores individuais contidos em uma matriz são representados como cores. |
| **[!UICONTROL Estilos]** | |
| [!UICONTROL Tema de cores] | Mostra o esquema de cor do mapa de calor e das propagações. Você pode optar por Coral, Vermelho, Verde ou Azul. O padrão é Coral. |
| [!UICONTROL Estilo do mapa] | É possível escolher entre Básico, Ruas, Brilhante, Claro, Escuro e Satélite. |
| **[!UICONTROL Raio do agrupamento]** | Agrupa os pontos de dados que estão dentro do número especificado de pixels. O padrão é 50. |
| **[!UICONTROL Valor máximo personalizado]** | Permite alterar o limite do valor máximo do mapa; alterar esse valor ajusta a escala dos valores de propagações e do mapa de calor (cor e tamanho) com relação ao valor máximo personalizado que foi definido. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/35004/?quality=12&captions=por_br)

-->

