---
title: referenciador
description: Substitua o referenciador coletado automaticamente em uma ocorrência.
feature: Appmeasurement Implementation
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 80%

---

# referenciador

A variável `referrer` substitui o referenciador coletado automaticamente nos relatórios. Essa variável é útil em situações em que o referenciador pode ser perdido, como durante redirecionamentos ou no encaminhamento temporário do visitante a um processador de pagamento. Essa variável ajuda a preencher as dimensões &quot;Referenciador&quot; e &quot;Domínio de referência&quot;.

## Referenciador que usa o Web SDK

O referenciador é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

O Web SDK inclui automaticamente `web.webReferrer.URL` em cada evento enviado, se disponível.

## Referenciador que usa a extensão do Adobe Analytics

Você pode definir o referenciador ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Definir Variáveis].
6. Localize a seção [!UICONTROL Referenciador].

É possível atribuir ao referenciador qualquer valor de string, incluindo elementos de dados.

## s.referrer no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.referrer` é uma string que contém o URL da página anterior. Essa variável pode armazenar no máximo 255 bytes; valores maiores que 255 bytes são truncados. O AppMeasurement define essa variável automaticamente como `document.referrer`; não é necessário definir essa variável, a menos que você deseje substituir o valor coletado automaticamente.

```js
s.referrer = "https://example.com";
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Evite definir essa variável para valores que não são URLs. Não remova o protocolo do URL.

## Exemplo

Muitas organizações lidam com implementações baseadas em redirecionamentos. Você pode usar o utilitário [`Util.getQueryParam()`](../functions/util-getqueryparam.md) para obter o referenciador do URL se o site o acomodar. Certifique-se de que o URL codifica todos os valores incluídos na string de consulta.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
