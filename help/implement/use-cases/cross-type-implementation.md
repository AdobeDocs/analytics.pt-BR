---
title: Rastrear em tipos diferentes de implementação
description: Use diferentes tipos de implementação e rastreie os visitantes facilmente entre eles.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '102'
ht-degree: 100%

---

# Rastrear em tipos diferentes de implementação

Essas informações são destinadas a usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem compreender as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.

Se você usar mais de um tipo de implementação (como JavaScript e solicitações de imagem codificadas), verifique se as seguintes variáveis foram especificadas e são correspondentes:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (se estiver usando SSL)

Se elas não corresponderem nas implementações, os usuários poderão ser acompanhados como visitantes separados.
