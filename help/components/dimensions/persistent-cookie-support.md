---
title: Suporte a cookie persistente
description: Determina se o visitante pode aceitar cookies persistentes.
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 11%

---

# Suporte a cookie persistente

A dimensão &quot;Suporte a cookies persistentes&quot; mostra se a ocorrência usou um identificador de visitante que se originou de uma fonte persistente. A fonte persistente mais comum é de um cookie, mas também pode usar cabeçalhos de dispositivos móveis e outras fontes.

## Preencher esta dimensão com dados

O Adobe determina o valor desse lado do servidor de dimensão com base na fonte do identificador da ocorrência. Não há uma maneira de defini-la diretamente. Funciona imediatamente em todas as implementações.

## Itens de dimensão

* **`Enabled`**: O identificador de visitante da ocorrência vem de uma fonte que normalmente persiste. Os exemplos mais comuns incluem `aid`, `fid` ou `mid` parâmetros de cadeias de caracteres de consulta, pois eles derivam seus valores de um cookie.
* **`Disabled`**: O identificador de visitante da ocorrência veio de uma fonte que o Adobe não reconhece como persistente, como IP + sequência de agente do usuário. Esse item de dimensão também inclui IDs de visitante personalizadas usando a variável [`visitorID`](/help/implement/vars/config-vars/visitorid.md) .

## Diferença entre &quot;Suporte a cookies&quot; e &quot;Suporte a cookies persistentes&quot;

* **Suporte** a cookies: O AppMeasurement tenta definir um cookie genérico. O item de dimensão se baseia se o cookie foi definido com êxito.
* **Suporte** a cookie persistente: O item de dimensão se baseia se o identificador da ocorrência se originou de uma fonte persistente, como um cookie.
