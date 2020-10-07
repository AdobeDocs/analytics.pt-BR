---
title: Limitar um VRS a determinadas datas
description: Entenda como limitar um intervalo de datas do VRS para se concentrar apenas em dados agrupados.
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---


# Limitar um VRS a determinadas datas

Quando ativamos a sutura, a sutura start em uma data específica. Vamos supor que a data seja 1º de junho. O CDA VRS conterá dados não agrupados antes de 1º de junho. Você pode ocultar todos os dados no VRS antes de 1º de junho para que sua análise possa se concentrar nos intervalos de datas após o início da sutura.

Você pode limitar os dados do VRS a determinadas datas, fazendo o seguinte:

## Etapa 1: Criar VRS com um intervalo de datas diário acumulado

Quando você configurar o VRS, em Componentes, adicione um intervalo de datas que tenha um start fixo, com um intervalo de datas diário continuado. O start fixo deve ser o dia em que a costura começou.

![](assets/rolling-daily.png)

## Etapa 2: Criar um segmento &quot;excluir&quot;

Em seguida, crie um segmento de ocorrência que coloque o intervalo de datas em um container excluído dentro de outro container excluído. É uma &quot;exclusão&quot;.

O motivo para a &quot;exclusão&quot; é que os intervalos de datas devem substituir o intervalo de datas do relatório. Portanto, se você incluir apenas 1º de junho, isso sempre fará com que a data do relatório entre 1º de junho e 1º de junho. Isto conduzirá a resultados indesejáveis. Quando você &quot;exclui&quot;, ele substitui esse comportamento e limita apenas os dados que podem ser obtidos no intervalo de datas apropriado.

![](assets/exclude-exclude.png)

## Etapa 3: Aplicar este segmento ao seu CDA VRS

![](assets/apply-segment.png)

## Etapa 4: Veja os resultados no relatórios

Observe que o relatórios agora start na data desejada, no mesmo dia em que a emenda foi implementada pela primeira vez:

![](assets/report-limited-dates.png)