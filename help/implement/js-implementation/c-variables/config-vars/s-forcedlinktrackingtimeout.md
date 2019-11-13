---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.forcedLinkTrackingTimeout

O número máximo de milissegundos a fim de aguardar a conclusão do rastreamento antes de executar doneAction que foi passado para `s.tl`. Esse valor especifica o tempo máximo de espera. Se a chamada de link de rastreamento for concluída antes do tempo limite, doneAction será executado imediatamente. Se você perceber que as chamadas de link de rastreamento não estão sendo concluídas, talvez precise aumentar esse tempo limite.

Valor padrão = 250

Exemplo: `s.forcedLinkTrackingTimeout = 500`
