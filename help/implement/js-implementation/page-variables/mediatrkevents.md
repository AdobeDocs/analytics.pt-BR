---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# Media.trackEvents

A variável identifica quais eventos devem ser enviados com uma ocorrência de mídia.

<!-- 

media_trackEvents.xml

 -->

Ela só é aplicável com JavaScript e [!UICONTROL ActionSource].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | s.Media.trackEvents="None" |

**Sintaxe e valores possíveis** {#section_66A978EF56914BEAAE73359A268A1B4A}

Nomes de eventos como event1 ou purchase.

**Exemplos** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Armadilhas, dúvidas e dicas** {#section_030B11C64EE84D46A85CA550DB732D28}

Não deixe de preencher [!UICONTROL trackVars] com "events" sempre que essa variável for preenchida.
