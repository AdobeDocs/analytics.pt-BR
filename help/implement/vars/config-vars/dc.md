---
title: dc
description: Uma variável desativada que permite determinar qual data center usar.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# dc

> [!IMPORTANT] Essa variável é removida. Use [`trackingServer`](trackingserver.md) em vez disso.

Em versões anteriores do Adobe Analytics, a Adobe exigia que você especificasse para qual data center deseja enviar os dados. Enviar ocorrências para o centro de dados errado resultou em perda de dados.

A Adobe melhorou essa experiência ao permitir que qualquer implementação envie ocorrências para `sc.omtrdc.net`. Não é mais necessário especificar o data center.
