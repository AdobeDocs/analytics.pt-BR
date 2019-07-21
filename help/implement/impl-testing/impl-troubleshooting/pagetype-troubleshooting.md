---
description: A variável pageType só é usada para designar uma página de erro 404 (Página não encontrada).
keywords: Implementação do Analytics
seo-description: A variável pageType só é usada para designar uma página de erro 404 (Página não encontrada).
seo-title: Configuração incorreta da variável pagetype
solution: Analytics
subtopic: Solução de problemas
title: Configuração incorreta da variável pagetype
topic: Desenvolvedor e implementação
uuid: eafaf 58 e-ba 07-416 f -89 b 9-694687 cc 4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configuração incorreta da variável pagetype

A variável pageType só é usada para designar uma página de erro 404 (Página não encontrada).

Ela só tem um valor possível, que é errorPage.

```js
pageType="errorPage"
```

Em uma Página de erro 404, a variável *`pageName`* não deve ser preenchida. *`pageType`* A variável deve ser definida somente em uma página de erro 404 designada. Any page containing content should never have a value in the *`pageType`* variable. Para páginas que contêm conteúdo, você deve definir a variável como mostrado abaixo:

```js
pageType=""
```

É melhor excluir a variável completamente das páginas contendo conteúdo. Esta prática é recomendada para evitar a confusão com relação à finalidade da variável.
