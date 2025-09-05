---
title: linkInternalFilters
description: Use a variável linkInternalFilters para ajudar no rastreamento automático do link de saída.
feature: Appmeasurement Implementation
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 100%

---

# linkInternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. Se [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) ou [`clickCollectionEnabled`](trackdownloadlinks.md) (SDK da Web) estiver habilitado, uma solicitação de imagem será enviada à Adobe assim que o visitante clicar em um link para sair do site. As variáveis [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável tiver um valor, o rastreamento automático do link de saída se comportará como uma lista de bloqueios. Se um clique em um link não corresponder a algum valor `linkInternalFilters`, ele será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se o [`linkLeaveQueryString`](linkleavequerystring.md) estiver habilitado, a sequência de consulta também será examinada.

Se você usar `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder a `linkExternalFilters` **e** não corresponder a `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

O Activity Map usa essa variável para ajudar a determinar quais links são internos ao site. A Adobe recomenda definir essa variável para implementações que usam o Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) são recursos separados que atendem a diferentes objetivos. A variável `linkInternalFilters` funciona especificamente para o rastreamento de link de saída. Os filtros de URL internos são uma configuração de administrador que ajuda com dimensões de origens de tráfego, como Domínio de referência.

## Links de saída no SDK da Web

Os links se qualificam automaticamente como um link de saída se o domínio de destino do link for diferente do `window.location.hostname` atual. O SDK da Web não oferece variáveis de configuração para modificar a detecção automática de link de saída. Se você precisar personalizar os domínios qualificados como um link de saída, poderá usar a lógica personalizada no retorno de chamada do `onBeforeEventSend`.

Consulte [Rastreamento de link automático](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=pt-BR#automaticLinkTracking) na documentação do SDK da Web para obter mais informações.

## Links de saída - Nunca rastrear usando a extensão do Adobe Analytics

O campo Nunca rastrear é uma lista de filtros separados por vírgulas (geralmente domínios) da opção [!UICONTROL Rastreamento de link] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela o campo [!UICONTROL Links de saída - Nunca rastrear].

Coloque os filtros que deseja que nunca sejam rastreados como links de saída neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkInternalFilters no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkInternalFilters` é uma cadeia de caracteres que contém filtros (como domínios) tidos como internos no site. Separe vários filtros usando uma vírgula sem espaços.

```js
s.linkInternalFilters = "example.com,example.net";
```

Considere o exemplo de implementação a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
