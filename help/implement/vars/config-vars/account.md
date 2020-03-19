---
title: account
description: Use a variável de conta para determinar o conjunto de relatórios para o qual os dados são enviados.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# account

> [!IMPORTANT] Essa variável é removida. Use a [`s.sa()`](../functions/sa-method.md) função se sua implementação exigir que você modifique o destino do conjunto de relatórios.

Em versões anteriores do Adobe Analytics, a `account` variável determinava o conjunto de relatórios para o qual você deseja enviar dados. Uma ID de conjunto de relatórios é necessária para enviar dados para o Adobe Analytics.

* Se você usar o Adobe Experience Platform Launch, os conjuntos de relatórios permanecerão sob o [!UICONTROL Library Management] acordeão ao configurar a extensão do Adobe Analytics.
* Se você usar a [`s_gi()`](../functions/s-gi.md) função para instanciar um objeto de rastreamento do Analytics, as IDs do conjunto de relatórios já existirão como um argumento obrigatório na função.
