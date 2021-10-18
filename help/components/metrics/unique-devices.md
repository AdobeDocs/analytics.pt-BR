---
title: Dispositivos únicos
description: O número de dispositivos exclusivos.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: db88bd439c036e97cca641f31f4fc3101a368636
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 100%

---

# Dispositivos únicos

A métrica &quot;Dispositivos exclusivos&quot; é uma métrica de [Análise entre dispositivos](../cda/overview.md) que conta o número de dispositivos não identificados exclusivos e dispositivos virtuais exclusivos. Dispositivos não identificados são dispositivos que geraram ocorrências anônimas. Dispositivos virtuais exclusivos são pessoas distintas identificadas por dispositivo.

## Como essa métrica é calculada

Para cada dispositivo, some todas as pessoas distintas vinculadas a ele (incluindo anônimo se o dispositivo contiver ocorrências não compiladas).

Observe que essa métrica não é igual a [Visitantes únicos](unique-visitors.md) em conjuntos de relatórios que não são CDA. Por exemplo, um dispositivo é compartilhado por três contas diferentes. Se todas as três contas visitarem seu site em uma janela de relatório, o relatório resultante mostrará três dispositivos exclusivos no CDA. Os mesmos dados fora do CDA mostrariam 1 Visitante único.

## Exemplo

1. João acessa o seu site no celular por meio de um anúncio, mas não fez logon.
1. Bob quer fazer uma compra, mas preferiria fazê-la no computador da família porque ele já está conectado lá. No computador da família, ele faz uma compra.
1. No dia seguinte, ele verifica seu pedido no celular e se autentica por lá.
1. A esposa de Bob, Alice, navega em seu site enquanto está conectada na própria conta no computador da família.
1. O irmão de Bob, Charles, também navega em seu site enquanto efetuava login na própria conta no computador da família.

![Contagem de dispositivos exclusivos](/help/components/metrics/assets/Unique_Devices_Count.png)

A visualização desses dados em um conjunto de relatórios virtuais CDA antes da [Repetição](/help/components/cda/replay.md) identifica potencialmente ocorrências não autenticadas e mostraria:

* **5 dispositivos exclusivos**: 1 para João não autenticado + 2 para João + 1 para Alice + 1 para Carlos
* **4 [Pessoas](people.md)**: 1 [pessoa não identificada](unidentified-people.md) + 3 [pessoas identificadas](identified-people.md).
