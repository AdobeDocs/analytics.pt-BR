---
title: linkLeaveQueryString
description: Permite a preservação de cadeias de caracteres de consulta em dimensões de rastreamento de link.
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '289'
ht-degree: 100%

---

# linkLeaveQueryString

Por padrão, o AppMeasurement remove as cadeias de caracteres de consulta dos URLs de rastreamento de link. Use a variável `linkLeaveQueryString` para manter as sequências de consulta nas dimensões de rastreamento de link.

Em alguns links de saída e de downloads, a parte importante do URL pode estar na cadeia de caracteres de consulta. Por exemplo, um link de download como `https://example.com/download.asp?filename=myfile.exe` contém informações importantes do link na cadeia de caracteres de consulta.

Se as informações de rastreamento de link não estiverem nos URLs do site, não será necessário usar essa variável. A remoção de cadeias de caracteres de consulta de URLs de rastreamento de link ajuda a limitar o número de valores únicos contidos na dimensão.

A ativação de `linkLeaveQueryString` se aplica a todas as dimensões de rastreamento de link (incluindo links personalizados, links de saída e links de download).

>[!TIP]
>
>Essa variável não afeta dimensões fora do rastreamento de link. Ela afeta apenas links personalizados, links de saída e links de download.

## Manter parâmetros de URL no Adobe Experience Platform Launch

[!UICONTROL Manter parâmetros de URL] é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Manter parâmetros de URL].

Marque essa caixa se desejar incluir cadeias de caracteres de consulta nas dimensões de rastreamento de link.

## s.linkLeaveQueryString no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkLeaveQueryString` é booleana. O valor padrão é `false`.

* Se essa variável estiver definida como `true`, as cadeias de caracteres de consulta serão mantidas nos URLs de rastreamento de link.
* Se essa variável for definida como `false` ou não estiver definida, as cadeias de caracteres de consulta serão removidas dos URLs de rastreamento de link.

```js
s.linkLeaveQueryString = true;
```

## Exemplo

Tenha cuidado ao definir essa variável como true, pois ela pode afetar os filtros de rastreamento de link como [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md) e [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Considere o exemplo a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
