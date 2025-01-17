---
description: Use a visualização de mapa em um projeto do Espaço de trabalho.
title: Mapa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: de489dda1c2627ccb263ac496f8abb2794854856
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 97%

---

# Mapa {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Mapa"
>abstract="Essa visualização representa as métricas ao sobrepô-las em um mapa. Isso é útil para identificar dados em diferentes regiões geográficas."

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

*Este artigo documenta a Visualização de mapa no **Adobe Analytics**.<br/>Atualmente, não há visualização de mapa disponível em **Customer Journey Analytics**.*

>[!ENDSHADEBOX]

## Visão geral {#section_19F740FAF08D47B1AF1EF239A74FC75C}

A visualização de mapa no Analysis Workspace

* Permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas).
* É útil para identificar e comparar dados de métrica em diferentes regiões geográficas.
* Pode suportar 2 fontes de dados: latitude/longitude de uso móvel ou dimensão geográfica para uso na Web.
* Suporta exportação de PDF.
* Aproveita WebGL para exibição de gráficos. Se os drivers de gráficos não suportarem a renderização de WebGL, talvez seja necessário atualizá-los.

Veja um vídeo com uma visão geral:

>[!VIDEO](https://video.tv.adobe.com/v/23559/?quality=12)

## Criar uma visualização de mapa {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. Na lista de visualizações, solte o **[!UICONTROL Mapa]** em um painel de Forma livre:

   ![](assets/map-viz1.png)

1. Arraste uma métrica da lista de métricas (incluindo métricas calculadas).
1. Especifique a fonte de dados da qual deseja desenhar. (Esta caixa de diálogo só será exibida se você tiver um rastreamento de localização ativado para os dados do aplicativo móvel.)

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Lat/long móveis] | Esta opção representa dados do aplicativo móvel. Esta opção estará visível somente se tiver sido habilitada para o conjunto de relatórios em [!UICONTROL Analytics] > [!UICONTROL Administrador] > [!UICONTROL Conjuntos de relatórios] > (selecione o conjunto de relatórios) > [!UICONTROL Editar configurações] >  [!UICONTROL Gerenciamento de dispositivos móveis] > [!UICONTROL Habilitar rastreamento de localização]. Esta é a configuração padrão (caso o rastreamento de localização esteja ativado). |
| [!UICONTROL Dimensão geográfica] | Esta opção representa dados de segmentação geográfica sobre a localização do visitante com base no endereço IP do visitante. Esses dados são transformados em [!UICONTROL País], [!UICONTROL Região] e [!UICONTROL Cidade]. Observe que eles não atingem o nível de DMA ou Código postal. Quase todos os conjuntos de relatórios têm essa dimensão ativada. Se o seu não tiver, entre em contato com o Atendimento ao cliente da Adobe para ativar os relatórios geográficos. |

1. Clique em **[!UICONTROL Criar]**.

   A primeira exibição será uma exibição do mundo com um mapa de propagação, semelhante a este.

   ![](assets/bubble-world-view.png)

1. Agora você pode

   * **Aplicar zoom** neste mapa para aumentar determinadas áreas ao clicar duas vezes no mapa ou usar a roda de rolagem. O zoom do mapa muda conforme a localização do cursor. Por meio da interação de zoom, a dimensão necessária (país > estado > cidade) é automaticamente atualizada, de acordo com o nível de zoom.
   * **Comparar** duas ou mais visualizações de mapa no mesmo projeto ao colocá-las lado a lado.
   * **Mostrar comparações periódicas (anuais (year-over-year), por exemplo)**:

      * Mostrar números negativos: por exemplo, se estiver traçando uma métrica anual, o mapa pode apresentar -33% em Nova York.
      * Com métricas do tipo “percentual”, o clustering faz uma média das porcentagens.
      * Um esquema de cores verde/vermelho: Positivo/Negativo

   * **Girar** o mapa em 2D ou 3D ao manter pressionada a tecla [!UICONTROL Ctrl] e mover o mapa.

   * **Alternar** para uma exibição diferente, como mapa de calor, usando as [configurações](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritas abaixo. Observe que a exibição de propagação é a configuração padrão.

1. **Salve** o projeto para salvar todas as configurações do mapa (coordenadas, zoom, rotação).
1. A tabela de forma livre, abaixo da visualização, pode ser preenchida ao arrastar nas métricas e dimensões de localização do painel esquerdo:

   ![](assets/location-dimensions.png)

## Configurações de visualização de mapa {#section_5F89C620A6AA42BC8E0955478B3A427E}

Existem 2 conjuntos de configurações para o Mapa:

O **ícone de chave** no lado superior direito retorna a caixa de diálogo inicial onde você pode alterar a métrica e a fonte de dados:

![](assets/map-wrench.png)

Se você clicar no **ícone de engrenagem**, aparecerão as configurações de visualização a seguir:

| Configuração | Descrição |
|--- |--- |
| Propagações | Faz a plotagem de eventos usando propagações. Um gráfico de propagação é um gráfico de muitas variáveis, que é um cruzamento entre um gráfico de dispersão e um gráfico de área proporcional. Esta é a exibição padrão. |
| Mapa de calor | Faz a plotagem de eventos usando um mapa de calor. Um mapa de calor é uma representação gráfica de dados onde os valores individuais contidos em uma matriz são representados como cores. |
| Estilos: Tema de cores | Mostra o esquema de cor do mapa de calor e das propagações. Você pode optar por Coral, Vermelho, Verde ou Azul. O padrão é Coral. |
| Estilos: Estilo do mapa | É possível optar por Básico, Ruas, Brilho, Claro, Escuro e Satélite. |
| Raio do cluster | Agrupa os pontos de dados que estão dentro do número especificado de pixels. O padrão é 50. |
| Valor máximo personalizado | Permite alterar o limite para o valor máximo do mapa; a definição desse valor ajusta a escala para os valores de propagações/mapa de calor (cor e tamanho) relacionados ao valor máximo personalizado que foi definido. |

## Criar um mapa de calor de divisão de tempo

Veja um vídeo sobre este tópico:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)
