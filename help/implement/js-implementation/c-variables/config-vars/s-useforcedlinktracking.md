---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.useForcedLinkTracking

Esse sinalizador é usado para desativar o rastreamento forçado de link para alguns navegadores. O rastreamento forçado de links é ativado por padrão para os navegadores FireFox 20 e posteriores, e WebKit.

When `useForcedLinkTracking` is enabled, the AppMeasurement file overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. O arquivo AppMeasurement executa a chamada de rastreamento de link e manipula o evento de navegação manualmente, em vez de usar a ação padrão do navegador.

No JavaScript H.25.4 (lançado em fevereiro de 2013), as limitações de escopo a seguir foram adicionadas aos links acompanhados quando `useForcedLinkTracking` estava ativada. O rastreamento de link forçado automático se aplica apenas a:

* Tags `<A>` e `<AREA>`.
* A tag deve ter um atributo `HREF`
* O `HREF` não pode começar com `#`, `about:` ou `javascript:`.
* O atributo `TARGET` não deve ser definido ou o `TARGET` precisa se referir à janela atual (`_self`, `_top` ou o valor de `window.name`).

Valor padrão = true

## Exemplo

`s.useForcedLinkTracking = false`

