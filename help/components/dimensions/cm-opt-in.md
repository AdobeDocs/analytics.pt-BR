---
title: Aceitação no gerenciamento de Consentimento
description: Veja em quais configurações de privacidade um visitante optou por participar.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 7%

---

# Aceitação no gerenciamento de Consentimento

A dimensão &quot;Aceitação no gerenciamento de consentimento&quot; exibe quais configurações de privacidade um visitante aceitou. Você pode usar essa dimensão para filtrar dados com base nas configurações de privacidade ou ver os motivos mais comuns de aceitação de privacidade.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da seguinte [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` quando definido como `Y`. If `opt.dmp` igual `N`, o [Recusa do gerenciamento de consentimento](cm-opt-out.md) é preenchida.
* `contextData.['opt.sell']` quando definido como `Y`. If `opt.sell` igual `N`, o [Recusa do gerenciamento de consentimento](cm-opt-out.md) é preenchida.

Sua organização determina a lógica para implementar essas variáveis de dados de contexto. Eles não persistem além da ocorrência em que estão definidos, portanto, é necessário definir cada variável de dados de contexto em cada página.

## Itens de dimensão

Os itens de Dimension incluem os dois valores a seguir:

* **`DMP`**: O visitante optou por compartilhar nas plataformas de gerenciamento de dados. Esse item de dimensão está presente quando a variável de dados de contexto `opt.dmp` igual `Y`.
* **`SELL`**: O visitante optou por compartilhar ou vender os dados para terceiros. Essa dimensão está presente quando a variável de dados de contexto `opt.sell` igual `Y`.
