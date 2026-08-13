---
title: Tipo de conexão
description: Como o visitante se conecta à Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 236
ht-degree: 94%

---

# Tipo de conexão

A [dimensão](overview.md) de &#39;Tipo de conexão&#39; mostra como o visitante se conectou à Internet. Essa dimensão é útil para determinar como os visitantes se conectam à Internet para navegar em seu site. Você pode usá-la para otimizar o conteúdo do site com base na velocidade de conexão dos visitantes.

## Preencher esta dimensão com dados

Essa dimensão usa uma combinação da [`ct` sequência de consulta](/help/implement/validate/query-parameters.md) e da lógica do lado do servidor da Adobe. A Adobe usa as seguintes regras para determinar seu valor:

1. Se a `ct` sequência de consulta for igual a `"modem"`, defina o item de dimensão como `"Modem"`. O AppMeasurement coleta esses dados somente em navegadores não compatíveis com o Internet Explorer, tornando esse item de dimensão incomum.
1. Verifique o endereço IP da ocorrência e faça referência a uma tabela de pesquisa interna da Adobe. Se o endereço IP for de uma operadora de celular, defina o item de dimensão como `"Mobile Carrier"`.
1. Se a `ct` sequência de consulta for igual a `"lan"`, defina o item de dimensão como `"LAN/Wifi"`.
1. Se a ocorrência se originar de uma [Fonte de dados](/help/import/data-sources/overview.md) ou se for considerada um tipo especial de ocorrência, defina o item de dimensão como `"Not specified"`.
1. Se nenhuma das regras acima for atendida, o padrão será o valor de `"LAN/Wifi"`.

## Itens de dimensão

Os itens de dimensão incluem `LAN/Wifi`, `Mobile Carrier`, `Modem` e `Not Specified`.

* **`LAN/Wifi`**: O visitante se conectou à Internet através de uma linha fixa ou ponto de acesso Wi-Fi.
* **`Mobile Carrier`**: o visitante se conectou à Internet por meio de uma operadora de celular.
* **`Modem`**: O visitante se conectou à Internet por meio de um modem em um navegador Internet Explorer não compatível.
* **`Not Specified`**: a ocorrência não tinha um tipo de conexão.
