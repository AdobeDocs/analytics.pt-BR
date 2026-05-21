---
title: Frequência de retorno
description: A quantidade de tempo entre a visita atual e a anterior.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 94%

---

# Frequência de retorno

A [dimensão](overview.md) de &#39;Frequência de retorno&#39; mostra o tempo decorrido entre as visitas de visitantes recorrentes. Quando um visitante retorna ao seu site, a Adobe verifica há quanto tempo a visita anterior foi realizada e classifica a ocorrência no item de dimensão apropriado. Essa dimensão é importante para ajudar a medir o apelo de seu site e a relevância para os visitantes ao longo do tempo. Também pode ajudar a identificar o impacto do conteúdo e das promoções do site nos visitantes.

>[!TIP]
>
>Essa dimensão não inclui visitantes novos.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

Os dados para essa dimensão são definidos na primeira ocorrência da visita e persistem para toda a visita. O valor não pode mudar no meio da visita.

## Itens de dimensão

Os itens de dimensão incluem compartimentos que se baseiam no tempo, dependendo do tempo decorrido desde a visita anterior.

* Menos de 1 dia
* 1 a 3 dias
* 3 a 7 dias
* 7 a 14 dias
* 14 dias a 1 mês
* Mais de 1 mês

## Os itens de dimensão aparecem em compartimentos fora do intervalo de datas do projeto

Quando você define o período de um projeto, é comum ver o atributo de itens de dimensão para visitas fora do período. Por exemplo, um visitante acessa seu site em julho, e retorna duas vezes em um mesmo dia de setembro. A dimensão Frequência de retorno para o mês de setembro mostraria uma visita em &quot;Mais de 1 mês&quot; e uma visita em &quot;Menos de 1 dia&quot;.
