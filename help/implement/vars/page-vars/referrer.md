---
title: referenciador
description: Substitua o referenciador coletado automaticamente em uma ocorrência.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# referenciador

A variável `referrer` substitui o referenciador coletado automaticamente nos relatórios. Essa variável é útil em situações em que o referenciador pode ser perdido, como durante redirecionamentos ou no encaminhamento temporário do visitante a um processador de pagamento. Essa variável ajuda a preencher as dimensões &quot;Referenciador&quot; e &quot;Domínio de referência&quot;.

## Referenciador no Adobe Experience Platform Launch

Você pode definir o referenciador ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Referenciador].

É possível atribuir ao referenciador qualquer valor de string, incluindo elementos de dados.

## s.referrer no AppMeasurement e no editor de código personalizado do Launch

A variável `s.referrer` é uma string que contém o URL da página anterior. Essa variável pode armazenar no máximo 255 bytes; valores maiores que 255 bytes são truncados. O AppMeasurement define essa variável automaticamente como `document.referrer`; não é necessário definir essa variável, a menos que você deseje substituir o valor coletado automaticamente.

```js
s.referrer = "https://example.com";
```

Evite definir essa variável para valores que não são URLs.

## Exemplo

Muitas organizações lidam com implementações baseadas em redirecionamentos. Você pode usar o utilitário [`Util.getQueryParam()`](../functions/util-getqueryparam.md) para obter o referenciador do URL se o site o acomodar. Certifique-se de que o URL codifica todos os valores incluídos na string de consulta.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
