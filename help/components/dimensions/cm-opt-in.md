---
title: Aceitação no gerenciamento de Consentimento
description: Veja em quais configurações de privacidade um visitante optou por participar.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 91%

---

# Aceitação no gerenciamento de Consentimento

A [dimensão](overview.md) da &#39;Aceitação no Gerenciamento de consentimento&#39; exibe as configurações de privacidade para as quais um visitante optou. Você pode usar essa dimensão para filtrar dados com base nas configurações de privacidade ou ver os motivos mais comuns de aceitação de privacidade.

## Preencher esta dimensão com dados

Essa dimensão coleta dados das seguintes [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` quando definido como `Y`. Se `opt.dmp` igual a `N`, a dimensão [Recusa do gerenciamento de consentimento](cm-opt-out.md) é preenchida.
* `contextData.['opt.sell']` quando definido como `Y`. Se `opt.sell` igual a `N`, a dimensão [Recusa do gerenciamento de consentimento](cm-opt-out.md) é preenchida.

Sua organização determina a lógica para implementar essas variáveis de dados de contexto. Eles não persistem além da ocorrência em que estão definidos, portanto, é necessário definir cada variável de dados de contexto em cada página.

## Itens de dimensão

Os itens de dimensão incluem os dois valores a seguir:

* **`DMP`**: o visitante optou por compartilhar nas plataformas de gerenciamento de dados. Esse item de dimensão está presente quando a variável de dados de contexto `opt.dmp` é igual a `Y`.
* **`SELL`**: o visitante optou por compartilhar ou vender os dados a terceiros. Essa dimensão está presente quando a variável de dados de contexto `opt.sell` é igual a `Y`.
