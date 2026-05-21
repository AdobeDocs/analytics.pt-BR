---
title: Domínio
description: A organização ou ISP que o visitante usa para acessar a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 54%

---

# Domínio

A [dimensão](overview.md) do &#39;Domínio&#39; relata os pontos de acesso que os visitantes usam para acessar a Internet.

## Preencher esta dimensão com dados

A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-pt/) para determinar o domínio do ponto de acesso. Vários métodos, incluindo a pesquisa de DNS reverso, são usados para determinar o domínio do ponto de acesso. Ela não requer nenhuma configuração e não tem uma variável para preencher.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa de Rede] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br).

## Itens de dimensão

Os itens de dimensão de exemplo incluem `comcast.net`, `rr.com`, `sbcglobal.net` e `amazonaws.com`. Esses domínios são pontos de acesso e não necessariamente o domínio que representa um ISP ou uma organização.

Os valores de dimensão de `None` significam que o proprietário do endereço IP do ponto de acesso não forneceu um domínio.
