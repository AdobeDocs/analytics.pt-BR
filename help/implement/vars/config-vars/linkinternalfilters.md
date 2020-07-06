---
title: linkInternalFilters
description: Use a variável linkInternalFilters para ajudar no rastreamento automático do link de saída.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 95%

---


# linkInternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. Se o [`trackExternalLinks`](trackexternallinks.md) estiver ativado, uma solicitação de imagem será enviada para a Adobe logo que um visitante clicar em um link para sair do site. As variáveis [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável contiver um valor, o rastreamento automático de link de saída se comporta como uma lista de bloqueios. Se um clique em um link não corresponder a algum valor `linkInternalFilters`, ele será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se o [`linkLeaveQueryString`](linkleavequerystring.md) estiver ativado, a sequência de consulta também será examinada.

Se você usar `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder a `linkExternalFilters` **e** não corresponder a `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

>[!NOTE]
>
>`linkInternalFilters`  e os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) são recursos separados que atendem a diferentes objetivos. A variável `linkInternalFilters` funciona especificamente para o rastreamento de link de saída. Os filtros de URL internos são uma configuração de administrador que ajuda com dimensões de origens de tráfego, como Domínio de referência.

## Links externos - Nunca rastrear no Adobe Experience Platform Launch

O campo Nunca rastrear é uma lista de filtros separados por vírgulas (geralmente domínios) da opção [!UICONTROL Rastreamento de link] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela o campo [!UICONTROL Links de saída - Nunca rastrear].

Coloque os filtros que deseja que nunca sejam rastreados como links de saída neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkInternalFilters no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkInternalFilters` é uma cadeia de caracteres que contém filtros (como domínios) tidos como internos no site. Separe vários filtros usando uma vírgula sem espaços.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Considere o exemplo de implementação a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
