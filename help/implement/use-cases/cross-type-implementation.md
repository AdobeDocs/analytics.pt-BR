---
title: Rastrear em tipos diferentes de implementação
description: Use diferentes tipos de implementação e rastreie os visitantes perfeitamente entre eles.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Rastrear em tipos diferentes de implementação

Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.

Se você usar mais de um tipo de implementação (como JavaScript e solicitações de imagem codificadas), verifique se as seguintes variáveis foram especificadas e são correspondentes:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`*(se estiver usando SSL)

Se elas não corresponderem nas implementações, os usuários poderão ser acompanhados como visitantes separados.
