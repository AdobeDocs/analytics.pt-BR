---
title: referenciador
description: Substitua o referenciador coletado automaticamente para uma ocorrência.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# referenciador

A `referrer` variável substitui o referenciador coletado automaticamente nos relatórios. Essa variável é útil em situações em que o referenciador pode ser perdido, como durante redirecionamentos ou o encaminhamento temporário do visitante para um processador de pagamento. Essa variável ajuda a preencher as dimensões &quot;Referenciador&quot; e &quot;Domínio de referência&quot;.

## Referenciador no Adobe Experience Platform Launch

Você pode definir o referenciador ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Localize a [!UICONTROL Referrer] seção.

É possível definir o referenciador com qualquer valor de string, incluindo elementos de dados.

## s.referrer no editor de código personalizado do AppMeasurement e do Launch

A `s.referrer` variável é uma string que contém o URL da página anterior. Essa variável pode armazenar no máximo 255 bytes; valores maiores que 255 bytes são truncados. O AppMeasurement define automaticamente essa variável como `document.referrer`; não é necessário definir essa variável, a menos que você deseje substituir o valor coletado automaticamente.

```js
s.referrer = "https://example.com";
```

Evite definir essa variável para valores não URL.

## Exemplo

Muitas organizações lidam com implementações em torno de redirecionamentos. Você pode usar o [`Util.getQueryParam()`](../functions/util-getqueryparam.md) utilitário para obter o referenciador do URL se o site o acomodar. Certifique-se de que o URL codifica todos os valores incluídos na string de consulta.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
