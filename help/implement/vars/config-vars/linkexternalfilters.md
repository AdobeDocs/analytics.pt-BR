---
title: linkExternalFilters
description: Use a variável linkExternalFilters para ajudar no rastreamento automático do link de saída.
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 91%

---

# linkExternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) ou [`clickCollectionEnabled`](trackexternallinks.md) (SDK da Web) estiver ativado, uma solicitação de imagem será enviada à Adobe assim que o visitante clicar em um link para sair do site. As variáveis `linkExternalFilters` e [`linkInternalFilters`](linkinternalfilters.md) determinam quais links são considerados internos/externos.

Se essa variável tiver um valor, o rastreamento automático do link de saída se comportará como uma lista de permissões. Se um clique em um link não corresponder a algum valor `linkExternalFilters`, ele não será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se o [`linkLeaveQueryString`](linkleavequerystring.md) estiver ativado, a sequência de consulta também será examinada.

>[!TIP]
>
>Use essa variável somente se você souber exatamente quais domínios deseja considerar como links de saída. Muitas organizações acham que usar o `linkInternalFilters` é suficiente para as necessidades de rastreamento de link de saída, e não usam `linkExternalFilters`.

Se você usar `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder a `linkExternalFilters` **e** não corresponder a `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Links de saída no SDK da Web

Os links se qualificam automaticamente como um link de saída se o domínio de destino do link for diferente do `window.location.hostname` atual. O SDK da Web não oferece variáveis de configuração para modificar a detecção automática de link de saída. Se você precisar personalizar os domínios qualificados como um link de saída, poderá usar a lógica personalizada no retorno de chamada do `onBeforeEventSend`.

Consulte [Rastreamento de link automático](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=pt-BR#automaticLinkTracking) na documentação do SDK da Web para obter mais informações.

## Links de saída - Rastrear usando a extensão do Adobe Analytics

O campo Rastrear é uma lista de filtros separados por vírgulas (geralmente domínios) da opção [!UICONTROL Rastreamento de links] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela o campo [!UICONTROL Links de saída - Rastrear].

Coloque filtros que deseja sempre considerar como externos neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkExternalFilters no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkExternalFilters` é uma cadeia de caracteres que contém filtros (como domínios) tidos como links de saída. Separe vários domínios usando uma vírgula sem espaços.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considere o exemplo de implementação a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
