---
description: A variável pageType só é usada para designar uma página de erro 404 (Página não encontrada).
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Configuração incorreta da variável do tipo de página
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configuração incorreta da variável do tipo de página

A variável pageType só é usada para designar uma página de erro 404 (Página não encontrada).

Ela só tem um valor possível, que é errorPage.

```js
pageType="errorPage"
```

Em uma Página de erro 404, a variável *`pageName`* não deve ser preenchida. A variável *`pageType`* deve ser definida somente em uma página de erro 404 designada. As páginas com conteúdo nunca devem ter um valor na variável *`pageType`*. Para páginas que contêm conteúdo, você deve definir a variável como mostrado abaixo:

```js
pageType=""
```

É melhor excluir a variável completamente das páginas contendo conteúdo. Esta prática é recomendada para evitar a confusão com relação à finalidade da variável.
