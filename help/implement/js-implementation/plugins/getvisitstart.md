---
description: Determina se uma nova visita começará.
keywords: Implementação do Analytics
seo-description: Determina se uma nova visita começará.
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: Desenvolvedor e implementação
uuid: 7 dd 3 e 51 f -2 f 73-4452-a 9 fb-cac 513 cd 28 eb
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getVisitStart

Determina se uma nova visita começará.

**Variáveis de configuração**

Nenhuma

**Parâmetros**

c = (string) nome do cookie para rastreamento.

**Devoluções**

(número inteiro) 1 na primeira página da visita; caso contrário, 0.

**Solicitações de exemplo**

```
s.eVar50 = s.getVisitStart("s_visit");
```

