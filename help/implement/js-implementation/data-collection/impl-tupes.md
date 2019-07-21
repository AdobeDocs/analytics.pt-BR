---
description: Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.
keywords: Implementação do Analytics
seo-description: Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.
seo-title: Rastrear em tipos de implementação diferentes
solution: Analytics
title: Rastrear em tipos de implementação diferentes
topic: Desenvolvedor e implementação
uuid: a -7a 3229 a -79 a 2-4 dc 2-b 0 be -4 b 8 fac 2 efa 3 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rastrear em tipos de implementação diferentes

Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.

Se você usar mais de um tipo de implementação (como JavaScript e solicitações de imagem codificadas), verifique se as seguintes variáveis foram especificadas e são correspondentes:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (se estiver usando SSL)

Se elas não corresponderem nas implementações, os usuários poderão ser acompanhados como visitantes separados.
