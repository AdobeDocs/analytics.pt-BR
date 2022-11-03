---
title: Recusa no gerenciamento de consentimento
description: Veja quais configurações de privacidade um visitante recusou.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 5%

---

# Recusa no gerenciamento de consentimento

A dimensão &quot;Recusa de gerenciamento de consentimento&quot; exibe quais configurações de privacidade um visitante recusou explicitamente. Você pode usar essa dimensão para filtrar dados com base nas configurações de privacidade ou ver os motivos mais comuns de recusa de privacidade.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da seguinte [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` quando definido como `1`. If `cm.ssf` igual `0` ou está em branco, essa variável não faz nada.
* `contextData.['opt.dmp']` quando definido como `N`. If `opt.dmp` igual `Y`, o [Aceitação no gerenciamento de consentimento](cm-opt-in.md) é preenchida.
* `contextData.['opt.sell']` quando definido como `N`. If `opt.sell` igual `Y`, o [Aceitação no gerenciamento de consentimento](cm-opt-in.md) é preenchida.

Sua organização determina a lógica para implementar essas variáveis de dados de contexto. Eles não persistem além da ocorrência em que estão definidos, portanto, é necessário definir cada variável de dados de contexto em cada página.

## Itens de dimensão

Os itens de Dimension incluem os três valores a seguir:

* **`SSF`**: O visitante recusou [Encaminhamento pelo lado do servidor](/help/admin/admin/c-server-side-forwarding/ssf.md). Esse item de dimensão está presente quando a variável de dados de contexto `cm.ssf` igual `1`. Consulte [Visão geral da privacidade de dados](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) no guia do usuário do Audience Manager para obter mais informações.
* **`DMP`**: O visitante recusou o compartilhamento nas plataformas de gerenciamento de dados. Esse item de dimensão está presente quando a variável de dados de contexto `opt.dmp` igual `N`. A ocorrência não é encaminhada ao Adobe Audience Manager.
* **`SELL`**: O visitante recusou o compartilhamento ou a venda dos dados a terceiros. Essa dimensão está presente quando a variável de dados de contexto `opt.sell` igual `N`.
