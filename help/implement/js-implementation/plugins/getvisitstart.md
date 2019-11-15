---
description: Determina se uma nova visita começará.
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitStart

Determina se uma nova visita começará.

**Variáveis de configuração**

Nenhum

**Parâmetros**

c = (string) nome do cookie para rastreamento.

**Devoluções**

(número inteiro) 1 na primeira página da visita; caso contrário, 0.

**Solicitações de exemplo**

```
s.eVar50 = s.getVisitStart("s_visit");
```

