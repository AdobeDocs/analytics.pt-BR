---
description: Use a visualização de mapa em um projeto do Espaço de trabalho.
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: e0d14f6dd7be438f3dad979abcfc279e710873e7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 60%

---

# Mapa {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Mapa"
>abstract="Essa visualização representa as métricas ao sobrepô-las em um mapa. Essa visualização é útil para identificar dados em diferentes regiões geográficas."

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

_Este artigo documenta a Visualização de mapa no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Atualmente, não há visualização de mapa disponível em_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]



A visualização do ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL Mapa]** no Analysis Workspace

* permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas),
* é útil para identificar e comparar dados de métrica em diferentes regiões geográficas,
* podem suportar duas fontes de dados: latitude/longitude do uso de dispositivos móveis ou dimensão geográfica para uso na web,
* suporta exportação de PDF e
* utiliza o WebGL para exibição de gráficos. Se os drivers de gráficos não suportarem a renderização de WebGL, talvez seja necessário atualizá-los.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualização de mapa no Analysis Workspace](https://video.tv.adobe.com/v/23559/?quality=12){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Usar

1. Adicionar uma visualização de ![Mapa](/help/assets/icons/Globe.svg) [!UICONTROL Mapa]. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Você só pode arrastar uma visualização de Mapa na parte superior de uma tabela de Forma livre.

   ![Configuração do mapa](assets/map-configuration.png){width="50%"}

1. Nas listas suspensas, selecione uma métrica. Ou arraste uma métrica da lista de métricas (incluindo métricas calculadas).
1. Especifique a fonte de dados da qual deseja desenhar. Essa caixa de diálogo será exibida somente se o rastreamento de localização estiver ativado para dados de aplicativos móveis.

   | Origem | Descrição |
   | --- | --- |
   | **[!UICONTROL Lat/long móveis]** | Esta opção representa dados do aplicativo móvel. Esta opção estará visível somente se tiver sido habilitada para o conjunto de relatórios em [!UICONTROL Analytics] > [!UICONTROL Administrador] > [!UICONTROL Conjuntos de relatórios] > (selecione o conjunto de relatórios) > [!UICONTROL Editar configurações] >  [!UICONTROL Gerenciamento de dispositivos móveis] > [!UICONTROL Habilitar rastreamento de localização]. Essas configurações são o padrão (se o rastreamento de localização estiver ativado). |
   | **[!UICONTROL Dimensão geográfica]** | Esta opção representa dados de segmentação geográfica sobre a localização do visitante com base no endereço IP do visitante. Esses dados são transformados em [!UICONTROL País], [!UICONTROL Região] e [!UICONTROL Cidade]. Observe que eles não atingem o nível de DMA ou Código postal. Quase todos os conjuntos de relatórios têm essa dimensão ativada. Se o seu não tiver, entre em contato com o Atendimento ao cliente da Adobe para ativar os relatórios geográficos. |

1. Selecione **[!UICONTROL Criar]**.

   Uma visualização de mapa mundial com bolhas é gerada.

   ![](assets/bubble-world-view.png)

1. Agora você pode:

   * **Aplicar zoom** neste mapa para aumentar determinadas áreas ao clicar duas vezes no mapa ou usar a roda de rolagem. O zoom do mapa muda conforme a localização do cursor. Por meio da interação de zoom, a dimensão necessária (país > estado > cidade) é automaticamente atualizada, de acordo com o nível de zoom.
   * **Comparar** duas ou mais visualizações de mapa no mesmo projeto ao colocá-las lado a lado.
   * **Mostrar comparações periódicas (anuais (year-over-year), por exemplo)**:

      * Mostrar números negativos: por exemplo, se estiver traçando uma métrica anual, o mapa pode apresentar -33% em Nova York.
      * Com métricas do tipo *percent*, o agrupamento calcula a média das porcentagens juntas.
      * Um esquema de cores verde/vermelho: Positivo/Negativo

   * **Girar** o mapa em 2D ou 3D ao manter pressionada a tecla [!UICONTROL Ctrl] e mover o mapa.

   * **Alternar** para uma exibição diferente, como mapa de calor, usando as [configurações](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritas abaixo. Observe que a exibição de propagação é a configuração padrão.

1. **Salve** o projeto para salvar todas as configurações do mapa (coordenadas, zoom, rotação).
1. A tabela de forma livre, abaixo da visualização, pode ser preenchida arrastando dimensões e métricas de localização do painel esquerdo.



## Configurar

Para reconfigurar a visualização de mapa, selecione ![Editar](/help/assets/icons/Edit.svg).


## Configurações 

Para definir configurações para a visualização, selecione ![Configuração](/help/assets/icons/Setting.svg).

| Configuração | Descrição |
|--- |--- |
| **[!UICONTROL Tipo de mapa]** | |
| [!UICONTROL Bolhas] | Faz a plotagem de eventos usando propagações. Um gráfico de propagação é um gráfico de muitas variáveis, que é um cruzamento entre um gráfico de dispersão e um gráfico de área proporcional. Essa exibição é a padrão. |
| Mapa de calor | Faz a plotagem de eventos usando um mapa de calor. Um mapa de calor é uma representação gráfica de dados onde os valores individuais contidos em uma matriz são representados como cores. |
| **[!UICONTROL Estilos]** | |
| [!UICONTROL Tema de cores] | Mostra o esquema de cor do mapa de calor e das propagações. Você pode optar por Coral, Vermelho, Verde ou Azul. O padrão é Coral. |
| [!UICONTROL Estilo do mapa] | Você pode escolher entre Básico, Ruas, Brilhante, Claro, Escuro e Satélite. |
| **[!UICONTROL Raio do cluster]** | Agrupa os pontos de dados que estão dentro do número especificado de pixels. O padrão é 50. |
| **[!UICONTROL Valor Máximo Personalizado]** | Permite alterar o limite para o valor máximo do mapa; a definição desse valor ajusta a escala para os valores de propagações/mapa de calor (cor e tamanho) relacionados ao valor máximo personalizado que foi definido. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)

-->

