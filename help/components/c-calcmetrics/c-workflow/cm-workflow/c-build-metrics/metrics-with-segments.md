---
description: Segmentar métricas individuais permite comparar métricas em um mesmo relatório. (Somente métricas derivadas)
title: Métricas segmentadas
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Métricas segmentadas

Segmentar métricas individuais permite comparar métricas em um mesmo relatório. (Somente métricas derivadas)

## Comparação de segmentos {#section_29A6E0070F084BFDB6228FA9CE106F48}

Suponha que você deseja comparar diferentes aspectos dos segmentos de &quot;Visitantes dos EUA&quot; com os dos segmentos de &quot;Visitantes internacionais&quot;. É possível criar métricas para obter insights como:

* Qual é a diferença de comportamento de navegação no conteúdo entre os dois grupos? (Outro exemplo seria: qual é a diferença da taxa de conversão entre os dois segmentos?)
* Como uma porcentagem do total de visitantes, quantos visitantes dos EUA navegam por determinadas páginas em relação aos visitantes internacionais?
* Quais são as maiores diferenças em termos de conteúdo acessado por esses diferentes segmentos?

Vamos explorar a primeira pergunta: qual é a diferença no comportamento de navegação no conteúdo entre os dois grupos?

1. Se você não tiver um segmento para comparação, crie um segmento interno no Criador de métricas calculadas chamado “Visitantes alemães”, onde “Países” corresponda a “Alemanha”. Basta arrastar a dimensão Países para a tela Definição e selecionar Alemanha como o valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Também é possível fazer isso no [Construtor de relatórios](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md), mas simplificamos o fluxo de trabalho, disponibilizando dimensões no Criador de métricas calculadas.

   >[!NOTE]
   >
   >&quot;Internal&quot; means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. You can however, make it public by hovering over the &quot;i&quot; icon next to it and clicking **[!UICONTROL Make public]**.

1. Caso não possua um segmento comparável, crie um segmento chamado “Visitantes internacionais” no qual &quot;Países” seja diferente de &quot;Alemanha”.
1. Crie e salve uma métrica chamada “Visitantes alemães”. Para fazer isso, arraste o segmento Alemanha para a tela Definição e, em seguida, arraste a métrica Visitantes únicos dentro dele:

   ![](assets/german-visitors.png)

1. Repita a Etapa 3 com o segmento de Visitantes internacionais e a métrica Visitantes únicos, e crie uma métrica Visitantes internacionais.
1. In Analysis Workspace, drag the **[!UICONTROL Page]** Dimension into a Freeform Table and drag the 2 new calculated metrics next to each other to the top:

   ![](assets/workspace-pages.png)

1. Or, in [!UICONTROL Reports & Analytics], open the [!UICONTROL Pages] report and click **[!UICONTROL Show Metrics]**, then apply the new US Visitors and International Visitors segmented metrics to see how their content browsing behavior compares.

   ![](assets/pages-report.png)

## Comparação das porcentagens dos totais {#section_846CB89725F04388AE0352DB20189EE8}

É possível adicionar outro nível de apuramento por meio da comparação entre o comportamento de navegação dos visitantes em porcentagens normalizadas. Para fazer isso, crie duas novas métricas, “% do total de visitantes alemães” e “% do total de visitantes internacionais”:

1. Solte o segmento Visitantes alemães (ou internacionais) na tela.
1. Solte outro segmento Visitantes alemães (ou internacionais) abaixo. Mas, desta vez, clique no ícone de configurações (engrenagem) e selecione o Tipo de métrica &quot;Total&quot;. O Formato deve ser &quot;Porcentagem&quot;. O operador deve ser &quot;dividido por&quot;. No final, você terá a seguinte definição de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica ao seu projeto:

   ![](assets/cm_percent_total.png)

## Comparação de diferenças nas porcentagens (usando contêineres) {#section_13D6353259B74C09B37BA6378A501938}

Caso queira ver imediatamente as maiores diferenças ente o comportamento de navegação de visitantes dos EUA e de visitantes internacionais, você pode criar uma métrica que subtraia as porcentagens das duas navegações. Para fazer isso, é possível usar a funcionalidade de contêiner, que funciona como parênteses ao redor dos dois conjuntos de métricas.

1. In the [!UICONTROL Definition] canvas, click **[!UICONTROL Add]** > **[!UICONTROL Container]**:

   ![](assets/cm_add_container.png)

1. Solte a métrica &quot;% do total de visitantes dos EUA&quot; criada anteriormente no primeiro contêiner. Ele será expandido para sua definição completa:

   ![](assets/cm_container_us.png)

1. Crie outro contêiner abaixo e solte nele a métrica &quot;% do total de visitantes internacionais&quot;.
1. Altere o operador entre os dois contêineres para um sinal de menos (-).

   ![](assets/cm_container_intl.png)

1. Salve a métrica (certifique-se de nomeá-la como &quot;Diferença de % entre visitantes dos EUA e visitantes internacionais&quot;, por exemplo).
1. Quando aplicada ao relatório, é possível ver as principais diferenças nas porcentagens, bem como classificar o relatório apropriadamente.

   ![](assets/cm_diff_percent.png)

