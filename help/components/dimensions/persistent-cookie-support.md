---
title: Suporte a cookie persistente
description: Determina se o visitante pode aceitar cookies persistentes.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 100%

---

# Suporte a cookie persistente

A dimensão &quot;Suporte a cookies persistentes&quot; mostra se a ocorrência usou um identificador de visitante que se originou de uma origem persistente. A origem persistente mais comum é de um cookie, mas também pode usar cabeçalhos de dispositivos móveis e outras origens.

## Preencher esta dimensão com dados

A Adobe determina o valor do lado do servidor dessa dimensão com base na origem do identificador da ocorrência. Não há uma maneira de defini-la diretamente. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

* **`Enabled`**: o identificador de visitante da ocorrência vem de uma origem que normalmente persiste. Os exemplos mais comuns incluem `aid`, `fid` ou `mid` parâmetros de sequência de consulta, pois eles derivam seus valores de um cookie.
* **`Disabled`**: o identificador de visitante da ocorrência veio de uma origem que a Adobe não reconhece como persistente, como IP + sequência de agente do usuário. Esse item de dimensão também inclui IDs de visitante personalizadas usando a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Diferença entre &quot;Suporte a cookies&quot; e &quot;Suporte a cookies persistentes&quot;

* **Suporte a cookies**: o AppMeasurement tenta definir um cookie genérico. O item de dimensão se baseia no caso de o cookie ter sido definido com êxito.
* **Suporte a cookies persistentes**: o item de dimensão se baseia no caso de o identificador da ocorrência tiver vindo de uma origem persistente, como um cookie.
