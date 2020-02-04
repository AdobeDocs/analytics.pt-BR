---
title: account
description: Use a variável de conta para determinar o conjunto de relatórios para o qual os dados são enviados.
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# account

> [!IMPORTANT] Essa variável é removida. Use a [`s.sa()`](../functions/sa.md) função se sua implementação exigir que você modifique o destino do conjunto de relatórios.

Em versões anteriores do Adobe Analytics, a `account` variável determinava o conjunto de relatórios para o qual você deseja enviar dados. Uma ID de conjunto de relatórios é necessária para enviar dados ao Adobe Analytics.

* Se você usar o Adobe Experience Platform Launch, os conjuntos de relatórios ficarão sob a opção Gerenciamento [!UICONTROL de] biblioteca ao configurar a extensão do Adobe Analytics.
* Se você usar a `s_gi()` função para instanciar um objeto de rastreamento do Analytics, as IDs do conjunto de relatórios já existem como um argumento obrigatório na função.
