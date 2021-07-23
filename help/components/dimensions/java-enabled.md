---
title: Java ativado
description: Determina se o Java está ativado no navegador.
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 90%

---

# Java ativado

A dimensão “Java ativado” determina se o navegador tem o Java ativado no momento. É útil nos casos em que você deseja introduzir a funcionalidade baseada em Java no seu site e deseja saber quantos visitantes já têm o Java ativado. Para aqueles que têm o Java desativado, você pode fornecer uma alternativa ou instruções sobre como ativá-lo.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`v` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados detectando se o Java está ativado no navegador. Se você usar uma biblioteca do AppMeasurement (por meio de tags no Adobe Experience Platform), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `v` que contém “Y” ou “N” se quiser usar essa dimensão.

## Itens de dimensão

Os itens de dimensão são “Ativado”, “Desativado” e “Desconhecido”.

* **Ativado**: o Java está ativado no navegador. A sequência de consulta `v` continha o valor “Y”.
* **Desativado**: o Java está desativado no navegador ou o navegador não é compatível com o Java. A sequência de consulta `v` continha o valor “N”.
* **Desconhecido**: o AppMeasurement não pôde determinar a compatibilidade com o Java. A sequência de consulta `v` não estava presente na solicitação de imagem.
