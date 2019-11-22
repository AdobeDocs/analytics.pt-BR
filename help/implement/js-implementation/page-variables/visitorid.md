---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# visitorID

Os visitantes podem ser identificados pela variável ou pelo endereço IP/Agente do usuário.


<!-- 

visitorID.xml

 -->

A *`visitorID`* pode conter até 100 caracteres alfanuméricos e não deve conter hífen.

Se você definir explicitamente uma ID personalizada, ela sempre será utilizada antes de outros métodos de ID.

Esta é a ordem de uso: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Tamanho máximo** | ** Parâmetro de depuração** | ** Relatórios preenchidos** | ** Valor padrão** |
|---|---|---|---|
| 100 bytes | vid | n/a | "" |

**Sintaxe e valores possíveis** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] A variável *`visitorID`* não deve conter hífen.

**Exemplos** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Configurações** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Nenhum
