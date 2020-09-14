---
description: 'Segmentar métricas individuais permite comparar métricas em um mesmo relatório. '
title: Métricas segmentadas
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: 234a2eadfe02322daa886d2edbea042f8ad99e1e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 59%

---


# Métricas segmentadas

No construtor de métricas calculadas, você pode aplicar segmentos na definição de métricas. Isso é útil se você quiser derivar novas métricas para usar na sua análise. Lembre-se de que as definições de segmentos podem ser atualizadas pelo construtor de segmentos. Se forem feitas alterações, o segmento será atualizado automaticamente em qualquer lugar em que for aplicado, incluindo se fizer parte de uma definição de métrica calculada.

![](assets/german-visitors.png)

## Criar uma métrica segmentada {#create}

Digamos que você queira comparar diferentes aspectos de um segmento &quot;Visitantes alemães&quot; com os de um segmento &quot;Visitantes internacionais&quot;. É possível criar métricas para obter insights como:

* Qual é a diferença de comportamento de navegação no conteúdo entre os dois grupos? (Outro exemplo seria: qual é a diferença da taxa de conversão entre os dois segmentos?)
* Como uma porcentagem do total de visitantes, quantos visitantes alemães navegam em determinadas páginas, em relação aos visitantes internacionais?
* Quais são as maiores diferenças em termos de conteúdo acessado por esses diferentes segmentos?

1. Se você não tiver um segmento comparável, crie um segmento adhoc diretamente no Criador de métricas calculadas chamado &quot;Visitantes alemães&quot;, onde &quot;Países&quot; seja igual a &quot;Alemanha&quot;. Basta arrastar a dimensão Países para a tela Definição e selecionar Alemanha como o valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Também é possível fazer isso no [Construtor de relatórios](/help/components/segmentation/segmentation-workflow/seg-build.md), mas simplificamos o fluxo de trabalho, disponibilizando dimensões no Criador de métricas calculadas. &quot;Adhoc&quot; means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. Entretanto, é possível torná-lo público ao passar o mouse sobre o ícone &quot;i&quot; e clicar em **[!UICONTROL Tornar público]**.

1. Caso não possua um segmento comparável, crie um segmento chamado “Visitantes internacionais” no qual &quot;Países” seja diferente de &quot;Alemanha”.
1. Crie e salve uma métrica chamada “Visitantes alemães”. Para fazer isso, arraste o segmento Alemanha para a tela Definição e, em seguida, arraste a métrica Visitantes únicos dentro dele:

   ![](assets/german-visitors.png)

1. Repita a Etapa 3 com o segmento de Visitantes internacionais e a métrica Visitantes únicos, e crie uma métrica Visitantes internacionais.
1. Na Analysis Workspace, arraste a dimensão **[!UICONTROL Página]** para uma Tabela de forma livre e arraste as 2 novas métricas calculadas para ficarem próximas na parte superior:

   ![](assets/workspace-pages.png)

## Porcentagem do total de métricas {#percent-total}

Você pode levar o exemplo acima um passo adiante comparando seu segmento a uma população total. Para fazer isso, crie duas novas métricas, &quot;% do total de Visitantes alemães&quot; e &quot;% do total de Visitantes internacionais&quot;:

1. Solte o segmento Visitantes alemães (ou internacionais) na tela.
1. Solte outro segmento Visitantes alemães (ou internacionais) abaixo. Mas, desta vez, clique no ícone de configurações (engrenagem) e selecione o Tipo de métrica &quot;Total&quot;. O Formato deve ser &quot;Porcentagem&quot;. O operador deve ser &quot;dividido por&quot;. No final, você terá a seguinte definição de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica ao seu projeto:

   ![](assets/cm_percent_total.png)

