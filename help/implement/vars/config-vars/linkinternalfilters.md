---
title: linkInternalFilters
description: Use a variável linkInternalFilters para ajudar no rastreamento automático do link de saída.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkInternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do seu site. Se [`trackExternalLinks`](trackexternallinks.md) estiver ativada, uma solicitação de imagem será enviada para a Adobe logo que um visitante clicar em um link para sair do site. As variáveis [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável contiver um valor, o rastreamento automático de link de saída se comporta de maneira semelhante à lista negra. Se um clique em um link não corresponder a nenhum `linkInternalFilters` valor, ele será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se [`linkLeaveQueryString`](linkleavequerystring.md) estiver ativada, a string de consulta também será examinada.

Se você usar ao mesmo tempo `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder `linkExternalFilters` e **não corresponder** `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

> [!NOTE] `linkInternalFilters` e filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos são recursos separados que atendem a fins diferentes. A `linkInternalFilters` variável funciona especificamente para o rastreamento de link de saída. Filtros internos de URL são uma configuração de administrador que ajuda com dimensões de fontes de tráfego como Domínio de referência.

## Links externos - Nunca rastrear no lançamento da plataforma Adobe Experience

O campo Nunca rastrear é uma lista separada por vírgulas de filtros (geralmente domínios) sob o [!UICONTROL Link Tracking] acordeão ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Amplie o [!UICONTROL Link Tracking] acordeão, que revela o [!UICONTROL Outbound Links - Never Track] campo.

Coloque filtros que você deseja que nunca sejam rastreados como links de saída neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkInternalFilters no AppMeasurement e Iniciar editor de código personalizado

A `s.linkInternalFilters` variável é uma string que contém filtros (como domínios) que você considera internos ao site. Separe vários filtros usando uma vírgula sem espaços.

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
