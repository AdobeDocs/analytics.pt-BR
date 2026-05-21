---
title: Dispositivos únicos
description: O número de dispositivos exclusivos.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
TQID: https://experienceleague.adobe.com/7KUpaGPuFGBHTXj8L4MKnjOsi1YQtA8KUCIXSa-NtXc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 73%

---

# Dispositivos únicos

A [métrica](overview.md) de &quot;Dispositivos exclusivos&quot; é uma [métrica de Análise entre dispositivos](../cda/overview.md) que conta o número de dispositivos não identificados exclusivos e dispositivos virtuais exclusivos. Dispositivos não identificados são dispositivos que geraram ocorrências anônimas. Dispositivos virtuais exclusivos são pessoas distintas identificadas por dispositivo.

## Como essa métrica é calculada

Para cada dispositivo, some todas as pessoas distintas vinculadas a ele (incluindo anônimo se o dispositivo contiver ocorrências não compiladas).

Observe que essa métrica não é igual a [Visitantes únicos](unique-visitors.md) em conjuntos de relatórios que não são CDA. Por exemplo, um dispositivo é compartilhado por três contas diferentes. Se todas as três contas visitarem seu site em uma janela de relatório, o relatório resultante mostrará três dispositivos exclusivos no CDA. Os mesmos dados fora do CDA mostrariam 1 Visitante único.

## Exemplo

1. João acessa seu site por telefone através de um anúncio, mas não fez logon.
1. João quer fazer uma compra, mas preferiria fazê-la no computador da família porque já está conectado lá. No computador da família, ele faz uma compra.
1. No dia seguinte, ela verifica seu pedido no celular e se autentica por lá.
1. A esposa de Bob, Alice, navega em seu site enquanto está conectada na própria conta no computador da família.
1. O irmão de Bob, Charles, também navega em seu site enquanto efetuava login na própria conta no computador da família.

![Contagem de dispositivos exclusivos](/help/components/metrics/assets/Unique_Devices_Count.png)

A visualização desses dados em um conjunto de relatórios virtuais CDA antes da [Repetição](/help/components/cda/replay.md) identifica potencialmente ocorrências não autenticadas e mostraria:

* **5 dispositivos exclusivos**: 1 para João não autenticado + 2 para João + 1 para Alice + 1 para Carlos
* **4 [Pessoas](people.md)**: 1 [pessoa não identificada](unidentified-people.md) + 3 [pessoas identificadas](identified-people.md).
