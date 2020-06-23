---
title: account
description: Use a variável de conta para determinar o conjunto de relatórios para o qual os dados são enviados.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# account

>[!IMPORTANT] Essa variável foi removida. Use a função [`s.sa()`](../functions/sa-method.md) se a implementação exigir que modifique o destino do conjunto de relatórios.

Em versões anteriores do Adobe Analytics, a variável `account` determinava o conjunto de relatórios para o qual você deseja enviar dados. É necessária uma ID de conjunto de relatórios para enviar dados ao Adobe Analytics.

* Se você usar o Adobe Experience Platform Launch, os conjuntos de relatórios ficarão na opção [!UICONTROL Gerenciamento de biblioteca] ao configurar a extensão do Adobe Analytics.
* Se você usar a função [`s_gi()`](../functions/s-gi.md) para instanciar um objeto de rastreamento do Analytics, as IDs do conjunto de relatórios já existem como um argumento obrigatório na função.
