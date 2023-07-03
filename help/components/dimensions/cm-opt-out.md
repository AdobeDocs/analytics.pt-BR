---
title: Recusa no gerenciamento de consentimento
description: Veja quais configurações de privacidade um visitante recusou.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 100%

---

# Recusa no gerenciamento de consentimento

A dimensão “Recusa de gerenciamento de consentimento” exibe quais configurações de privacidade um visitante recusou explicitamente. Você pode usar essa dimensão para filtrar dados com base nas configurações de privacidade ou ver os motivos mais comuns de recusa de privacidade.

## Preencher esta dimensão com dados

Essa dimensão coleta dados das seguintes [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` quando definido como `1`. Se `cm.ssf` igual a `0` ou está em branco, essa variável não faz nada.
* `contextData.['opt.dmp']` quando definido como `N`. Se `opt.dmp` igual a `Y`, a dimensão [Aceitação do gerenciamento de consentimento](cm-opt-in.md) é preenchida.
* `contextData.['opt.sell']` quando definido como `N`. Se `opt.sell` igual a `Y`, a dimensão [Aceitação do gerenciamento de consentimento](cm-opt-in.md) é preenchida.

Sua organização determina a lógica para implementar essas variáveis de dados de contexto. Eles não persistem além da ocorrência em que estão definidos, portanto, é necessário definir cada variável de dados de contexto em cada página.

## Itens de dimensão

Os itens de dimensão incluem os três valores a seguir:

* **`SSF`**: o visitante recusou o [Encaminhamento pelo lado do servidor](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md). Esse item de dimensão está presente quando a variável de dados de contexto `cm.ssf` é igual a `1`. Consulte [Visão geral da privacidade de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=pt-BR) no guia do usuário do Audience Manager para obter mais informações. A ocorrência não é encaminhada ao Adobe Audience Manager.
* **`DMP`**: ol visitante recusou o compartilhamento nas plataformas de gerenciamento de dados. Esse item de dimensão está presente quando a variável de dados de contexto `opt.dmp` é igual a `N`. Semelhante a `SSF`, a ocorrência não é encaminhada ao Adobe Audience Manager.
* **`SELL`**: o visitante recusou o compartilhamento ou a venda dos dados a terceiros. Essa dimensão está presente quando a variável de dados de contexto `opt.sell` é igual a `N`.
