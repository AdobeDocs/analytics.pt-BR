---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forcedLinkTrackingTimeout

Esse valor especifica o tempo máximo de espera. Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. Se a chamada de link de rastreamento for concluída antes do tempo limite, `doneAction` será executado imediatamente. Se você perceber que as chamadas de link de rastreamento não estão sendo concluídas, talvez precise aumentar esse tempo limite.

Valor padrão = 250

Exemplo: `s.forcedLinkTrackingTimeout = 500`
