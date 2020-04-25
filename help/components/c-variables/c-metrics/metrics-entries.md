---
description: As entradas representam o número de vezes em que determinado valor é capturado como o primeiro em uma visita. Entradas pode ocorrer somente uma vez por visita. Contudo, não é necessariamente a primeira ocorrência se a variável não estiver definida.
title: Entradas
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Entradas

&quot;Entradas&quot; representa o número de vezes que um determinado valor é capturado como o primeiro valor em uma visita. Entradas pode ocorrer somente uma vez por visita. Contudo, não é necessariamente a primeira ocorrência se a variável não estiver definida.

A partir de março de 2020, alteramos a forma como o valor “Nenhum” interage com as Entradas/Saídas no Analysis Workspace.  Como agora você pode ativar e desativar &quot;Nones&quot; na área de trabalho da Análise, aplicamos &quot;Nenhum&quot; após a entrada ou saída, enquanto (para evars) ela costumava ser aplicada antes.  Por exemplo, suponha que a primeira ocorrência de uma visita não tenha valor para, por exemplo, eVar21, mas a segunda ocorrência tem valor. No Reports &amp; Analytics, será exibido como &quot;Não especificado&quot; para a Entrada, mas no Analysis Workspace será exibido como o valor na segunda ocorrência.

As páginas de entrada possuem um escopo de interrupção de visita, o que significa que eles persistem em todos os hits de uma visitas. Ver [Contêineres de interrupção e segmentação](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) para obter mais informações.
