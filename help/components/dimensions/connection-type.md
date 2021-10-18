---
title: Tipo de conexão
description: Como o visitante se conecta à Internet.
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---

# Tipo de conexão

A dimensão &quot;Tipo de conexão&quot; mostra como o visitante se conectou à Internet. Essa dimensão é útil para determinar como os visitantes se conectam à Internet para navegar em seu site. Você pode usá-la para otimizar o conteúdo do site com base na velocidade de conexão dos visitantes.

## Preencher esta dimensão com dados

Essa dimensão usa uma combinação da [`ct` sequência de consulta](/help/implement/validate/query-parameters.md) e da lógica do lado do servidor da Adobe. A Adobe usa as seguintes regras para determinar seu valor:

1. Se a `ct` sequência de consulta for igual a `"modem"`, defina o item de dimensão como `"Modem"`. O AppMeasurement coleta esses dados somente em navegadores não compatíveis com o Internet Explorer, tornando esse item de dimensão incomum.
1. Verifique o endereço IP da ocorrência e faça referência a uma tabela de pesquisa interna da Adobe. Se o endereço IP for de uma operadora de celular, defina o item de dimensão como `"Mobile Carrier"`.
1. Se a `ct` sequência de consulta for igual a `"lan"`, defina o item de dimensão como `"LAN/Wifi"`.
1. Se a ocorrência se originar de uma [Fonte de dados](/help/import/c-data-sources/datasrc-home.md) ou se for considerada um tipo especial de ocorrência, defina o item de dimensão como `"Not specified"`.
1. Se nenhuma das regras acima for atendida, o padrão será o valor de `"LAN/Wifi"`.

## Itens de dimensão

Os itens de dimensão incluem `LAN/Wifi`, `Mobile Carrier`, `Modem` e `Not Specified`.

* **`LAN/Wifi`**: O visitante se conectou à Internet através de uma linha fixa ou ponto de conexão Wi-Fi.
* **`Mobile Carrier`**: o visitante se conectou à Internet por meio de uma operadora de celular.
* **`Modem`**: O visitante se conectou à Internet por meio de um modem em um navegador Internet Explorer não compatível.
* **`Not Specified`**: a ocorrência não tinha um tipo de conexão.
