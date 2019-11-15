---
description: Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.
keywords: Analytics Implementation
solution: Analytics
title: Rastrear em tipos diferentes de implementação
topic: Developer and implementation
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Rastrear em tipos diferentes de implementação

Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.

Se você usar mais de um tipo de implementação (como JavaScript e solicitações de imagem codificadas), verifique se as seguintes variáveis foram especificadas e são correspondentes:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (se estiver usando SSL)

Se elas não corresponderem nas implementações, os usuários poderão ser acompanhados como visitantes separados.
