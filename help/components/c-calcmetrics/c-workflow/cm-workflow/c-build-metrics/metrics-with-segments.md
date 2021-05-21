---
description: 'Segmentar métricas individuais permite comparar métricas em um mesmo relatório. '
title: Métricas segmentadas
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '449'
ht-degree: 100%

---

# Métricas segmentadas

No Criador de métrica calculada, você pode aplicar segmentos à definição de métricas. Isso é útil se você quer derivar novas métricas para usar em sua análise. Lembre-se, as definições de segmento podem ser atualizadas por meio do Construtor de segmentos. Se forem feitas alterações, o segmento será atualizado automaticamente em qualquer lugar em que for aplicado, inclusive se fizer parte de uma definição de métrica calculada.

![](assets/german-visitors.png)

## Criar uma métrica segmentada {#create}

Suponha que você deseje comparar diferentes aspectos dos segmentos de &quot;Visitantes alemães&quot; com os dos segmentos de &quot;Visitantes internacionais&quot;. É possível criar métricas para obter insights como:

* Qual é a diferença de comportamento de navegação no conteúdo entre os dois grupos? (Outro exemplo seria: qual é a diferença da taxa de conversão entre os dois segmentos?)
* Como uma porcentagem do total de visitantes, quantos visitantes alemães navegam por determinadas páginas em comparação com os visitantes internacionais?
* Quais são as maiores diferenças em termos de conteúdo acessado por esses diferentes segmentos?

1. Se você não tiver um segmento para comparação, crie um segmento adhoc no Criador de métrica calculada chamado “Visitantes alemães”, em que “Países” corresponda a “Alemanha”. Basta arrastar a dimensão Países para a tela Definição e selecionar Alemanha como o valor:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Também é possível fazer isso no [Construtor de relatórios](/help/components/segmentation/segmentation-workflow/seg-build.md), mas simplificamos o fluxo de trabalho, disponibilizando dimensões no Criador de métricas calculadas. &quot;Adhoc&quot; significa que o segmento não está visível na lista **[!UICONTROL Segmentos]** no painel à esquerda. Entretanto, é possível torná-lo público ao passar o mouse sobre o ícone &quot;i&quot; e clicar em **[!UICONTROL Tornar público]**.

1. Caso não possua um segmento comparável, crie um segmento chamado “Visitantes internacionais” no qual &quot;Países” seja diferente de &quot;Alemanha”.
1. Crie e salve uma métrica chamada “Visitantes alemães”. Para fazer isso, arraste o segmento Alemanha para a tela Definição e, em seguida, arraste a métrica Visitantes únicos dentro dele:

   ![](assets/german-visitors.png)

1. Repita a Etapa 3 com o segmento de Visitantes internacionais e a métrica Visitantes únicos, e crie uma métrica Visitantes internacionais.
1. Na Analysis Workspace, arraste a dimensão **[!UICONTROL Página]** para uma Tabela de forma livre e arraste as 2 novas métricas calculadas para ficarem próximas na parte superior:

   ![](assets/workspace-pages.png)

## Porcentagem do total de métricas {#percent-total}

Você pode levar o exemplo acima um passo além comparando seu segmento a uma população total. Para fazer isso, crie duas novas métricas, “% do total de visitantes alemães” e “% do total de visitantes internacionais”:

1. Solte o segmento Visitantes alemães (ou internacionais) na tela.
1. Solte outro segmento Visitantes alemães (ou internacionais) abaixo. Mas, desta vez, clique no ícone de configurações (engrenagem) e selecione o Tipo de métrica &quot;Total&quot;. O Formato deve ser &quot;Porcentagem&quot;. O operador deve ser &quot;dividido por&quot;. No final, você terá a seguinte definição de métrica:

   ![](assets/cm_metric_total.png)

1. Aplique esta métrica ao seu projeto:

   ![](assets/cm_percent_total.png)
