---
title: Países
description: O país de onde a ocorrência se originou.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
TQID: https://experienceleague.adobe.com/qEG8tKa7eEuYV6XgYSlf4Y8FPaCiyWxPmdtL6KkKm94
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 65%

---

# Países

A [dimensão](overview.md) de &quot;Países&quot; informa o país de onde a ocorrência se originou. Essa dimensão é útil para ajudar a determinar a origem dos visitantes dos países mais populares ao visitar seu site. Você pode usar esses dados para se concentrar nos esforços de marketing nesses países ou para garantir que a experiência do seu site seja ideal nos países com idiomas principais diferentes.

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-pt/) para manter pesquisas entre o endereço IP e o país.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa Geográfica] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br).

## Itens de dimensão

Os itens de dimensão incluem países em todo o mundo. Os valores de exemplo incluem `"United States"`, `"United Kingdom"` ou `"India"`.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Algumas operadoras fazem o backhaul do tráfego IP por meio de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
* **Proxies que obscurecem endereços IP por motivos de privacidade**: serviços como a Retransmissão Privada da Apple ocultam o endereço IP verdadeiro enviando dados aleatoriamente por meio de um intermediário ou proxy. Esse proxy substitui um endereço IP diferente antes de encaminhar para o Adobe.
