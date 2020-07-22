---
title: Java ativado
description: Determina se o Java está ativado no navegador.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 1%

---


# Java ativado

A dimensão &#39;Java ativado&#39; determina se o navegador no momento tem o Java ativado. É útil nos casos em que você deseja introduzir a funcionalidade baseada em Java no seu site e desejar saber quantos visitantes já têm o Java ativado. Para aqueles que têm o Java desativado, você pode fornecer uma alternativa ou instruções sobre como ativá-lo.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`v` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados detectando se o Java está ativado no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `v` query que contém &quot;Y&quot; ou &quot;N&quot; se desejar usar essa dimensão.

## Itens de dimensão

Os itens de dimensão incluem &quot;Ativado&quot;, &quot;Desativado&quot; e &quot;Desconhecido&quot;.

* **Ativado**: O Java está ativado no navegador. A string de `v` query continha o valor &quot;Y&quot;.
* **Desativado**: O Java está desativado no navegador ou não é compatível com o Java. A string de `v` query continha o valor &quot;N&quot;.
* **Desconhecido**: O AppMeasurement não pôde determinar o suporte a Java. A cadeia de caracteres do `v` query não estava presente na solicitação de imagem.
