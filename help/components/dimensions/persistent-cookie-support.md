---
title: Suporte a cookie persistente
description: Determina se o visitante pode aceitar cookies persistentes.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 90%

---

# Suporte a cookie persistente

A [dimensão](overview.md) de &#39;Suporte a cookies persistentes&#39; mostra se a ocorrência usou um identificador de visitante que se originou de uma origem persistente. A origem persistente mais comum é de um cookie, mas também pode usar cabeçalhos de dispositivos móveis e outras origens.

## Preencher esta dimensão com dados

A Adobe determina o valor do lado do servidor dessa dimensão com base na origem do identificador da ocorrência. Não há uma maneira de defini-la diretamente. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

* **`Enabled`**: o identificador de visitante da ocorrência vem de uma origem que normalmente persiste. Os exemplos mais comuns incluem `aid`, `fid` ou `mid` parâmetros de sequência de consulta, pois eles derivam seus valores de um cookie.
* **`Disabled`**: o identificador de visitante da ocorrência veio de uma origem que a Adobe não reconhece como persistente, como IP + sequência de agente do usuário. Esse item de dimensão também inclui IDs de visitante personalizadas usando a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Diferença entre &quot;Suporte a cookies&quot; e &quot;Suporte a cookies persistentes&quot;

* **Suporte a cookies**: o AppMeasurement tenta definir um cookie genérico. O item de dimensão se baseia no caso de o cookie ter sido definido com êxito.
* **Suporte a cookies persistentes**: o item de dimensão se baseia no caso de o identificador da ocorrência tiver vindo de uma origem persistente, como um cookie.
