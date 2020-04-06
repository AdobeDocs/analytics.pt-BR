---
title: dc
description: Uma variável removida que permite determinar qual data center usar.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# dc

>[!IMPORTANT] Essa variável foi removida. Use [`trackingServer`](trackingserver.md) no lugar dela.

Em versões anteriores do Adobe Analytics, a Adobe exigia que especificasse para qual data center desejava enviar os dados. Enviar ocorrências para o data center errado resultou em perda de dados.

A Adobe melhorou essa experiência ao permitir que qualquer implementação envie ocorrências para `sc.omtrdc.net`. Não é mais necessário especificar o data center.
