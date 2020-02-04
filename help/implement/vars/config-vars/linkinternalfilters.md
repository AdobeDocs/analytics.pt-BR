---
title: linkInternalFilters
description: Use a variável linkInternalFilters para ajudar no rastreamento automático do link de saída.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkInternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. Se `trackExternalLinks` `true`estiver, uma solicitação de imagem será enviada para a Adobe logo que um visitante clicar em um link para sair do site. As variáveis `linkTrackExternalFilters` e `linkTrackInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável contiver um valor, o rastreamento automático de link de saída se comporta de maneira semelhante à lista negra. Se um clique em um link não corresponder a nenhum `linkInternalFilters` valor, ele será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se `linkLeaveQueryString` for `true`, a string de consulta também será examinada.

Se você usar ao mesmo tempo `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder `linkExternalFilters` e **não corresponder** `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

> [!NOTE] Os filtros de URL interno `linkInternalFilters` e interno são recursos separados que atendem a fins diferentes. A `linkInternalFilters` variável funciona especificamente para o rastreamento de link de saída. Os filtros internos de URL são uma configuração de administrador que ajuda com dimensões de fontes de tráfego como Domínio de referência. See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## Links externos - Nunca rastrear no lançamento da plataforma Adobe Experience

O campo Nunca rastrear é uma lista separada por vírgulas de filtros (geralmente domínios) sob a opção Rastreamento [!UICONTROL de] link ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela o campo Links [!UICONTROL de saída - Nunca rastrear] .

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
