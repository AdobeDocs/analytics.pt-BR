---
title: linkLeaveQueryString
description: Permite a preservação de sequências de consulta em dimensões de rastreamento de link.
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

Por padrão, o AppMeasurement remove as sequências de caracteres de consulta dos URLs de rastreamento de link. Use a variável linkLeaveQueryString para preservar as sequências de caracteres de consulta nas dimensões de rastreamento de link.

Para alguns links de saída e links de download, a parte importante do URL pode estar na string de consulta. Por exemplo, um link de download, como `https://example.com/download.asp?filename=myfile.exe` contém informações importantes do link na string de consulta.

Se as informações de rastreamento de link não estiverem nos URLs do site, não é necessário usar essa variável. A remoção de sequências de consulta de URLs de rastreamento de link ajuda a limitar o número de valores únicos que a dimensão contém.

A ativação `linkLeaveQueryString` se aplica a todas as dimensões de rastreamento de link (incluindo links personalizados, links de saída e links de download).

> [!TIP] Essa variável não afeta dimensões fora do rastreamento de link. Ela afeta apenas links personalizados, links de saída e links de download.

## Manter parâmetros de URL no Adobe Experience Platform Launch

[!UICONTROL Manter parâmetros] de URL é uma caixa de seleção na opção [!UICONTROL Rastreamento] de link ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela a caixa de seleção [!UICONTROL Manter parâmetros] de URL.

Marque essa caixa se desejar incluir sequências de consulta nas dimensões de rastreamento de link.

## s.linkLeaveQueryString no AppMeasurement e Iniciar editor de código personalizado

A `s.linkLeaveQueryString` variável é booleana. Its default value is `false`.

* Se essa variável estiver definida como `true`, as sequências de caracteres de consulta serão preservadas nos URLs de rastreamento de link.
* Se essa variável estiver definida `false` ou não estiver definida, as sequências de caracteres de consulta serão removidas dos URLs de rastreamento de link.

```js
s.linkLeaveQueryString = true;
```

## Exemplo

Tenha cuidado ao definir essa variável como true, pois ela pode afetar os filtros de rastreamento de link como `linkInternalFilters`, `linkExternalFilters`e `linkDownloadFiletypes`.

Considere o exemplo a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
