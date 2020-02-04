---
title: linkExternalFilters
description: Use a variável linkExternalFilters para ajudar no rastreamento automático do link de saída.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkExternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. Se `trackExternalLinks` `true`estiver, uma solicitação de imagem será enviada para a Adobe logo que um visitante clicar em um link para sair do site. As variáveis `linkTrackExternalFilters` e `linkTrackInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável contiver um valor, o rastreamento automático de link de saída se comporta de maneira semelhante à lista de permissões. Se um clique em um link não corresponder a nenhum `linkExternalFilters` valor, ele não será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se `linkLeaveQueryString` for `true`, a string de consulta também será examinada.

> [!TIP] Use essa variável somente se você souber exatamente quais domínios deseja considerar como links de saída. Muitas organizações acham que o uso `linkInternalFilters` é suficiente para as necessidades de rastreamento de link de saída e não é usado `linkExternalFilters`.

Se você usar ao mesmo tempo `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder `linkExternalFilters` e **não corresponder** `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

## Links externos - Rastrear no lançamento da plataforma Adobe Experience

O campo Rastrear é uma lista separada por vírgulas de filtros (geralmente domínios) sob a opção Rastreamento [!UICONTROL de] links ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela o campo Links [!UICONTROL de saída - Rastrear] .

Coloque filtros que você deseja sempre considerar externos neste campo. Separe vários domínios por vírgula sem espaço.

## s.linkExternalFilters no AppMeasurement e no editor de código personalizado Iniciar

A `s.linkExternalFilters` variável é uma string que contém filtros (como domínios) que você considera links de saída. Separe vários domínios usando uma vírgula sem espaços.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Considere o exemplo de implementação a seguir como se ele estivesse em `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is not considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
