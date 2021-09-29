---
title: Dispositivos únicos
description: O número de dispositivos exclusivos.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: db88bd439c036e97cca641f31f4fc3101a368636
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 5%

---

# Dispositivos únicos

A métrica &quot;Dispositivos únicos&quot; é uma métrica [Análise entre dispositivos](../cda/overview.md) que conta o número de dispositivos não identificados exclusivos e dispositivos virtuais exclusivos. Dispositivos não identificados são dispositivos que geraram ocorrências anônimas. Dispositivos virtuais exclusivos são pessoas distintas identificadas por dispositivo.

## Como essa métrica é calculada

Para cada dispositivo, some todas as pessoas distintas vinculadas a ele (incluindo anônimo se o dispositivo contiver ocorrências não compiladas).

Observe que essa métrica não é igual a [Visitantes únicos](unique-visitors.md) em conjuntos de relatórios não CDA. Por exemplo, um dispositivo é compartilhado por 3 contas diferentes. Se todas as 3 contas visitarem seu site em uma janela de relatório, o relatório resultante mostrará 3 Dispositivos únicos no CDA. Os mesmos dados fora do CDA mostrariam 1 Visitante único.

## Exemplo

1. Bob chega ao seu site pelo telefone através de um anúncio, mas não está conectado.
1. Bob quer fazer uma compra, mas preferiria fazê-la no computador da família porque ele já está conectado lá. No computador da família, ele faz uma compra.
1. No dia seguinte, ele verifica seu pedido no telefone e se autentica lá.
1. A esposa de Bob, Alice, navega em seu site enquanto estava conectada em sua conta no computador da família.
1. O irmão de Bob, Charles, também navega em seu site enquanto efetuava login em sua conta no computador da família.

![Contagem de dispositivos únicos](/help/components/metrics/assets/Unique_Devices_Count.png)

A visualização desses dados em um conjunto de relatórios virtual do CDA antes de [Reproduzir](/help/components/cda/replay.md) possivelmente une os hits não autenticados mostraria:

* **5 dispositivos** exclusivos: 1 para Bob + 2 não autenticado para Bob + 1 para Alice + 1 para Charles
* **4  [Pessoas](people.md)**: 1 Pessoas  [Não Identificadas](unidentified-people.md)  + 3 Pessoas  [Identificadas](identified-people.md).
