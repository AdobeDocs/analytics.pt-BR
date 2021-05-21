---
title: linkInternalFilters
description: Use a variável linkInternalFilters para ajudar no rastreamento automático do link de saída.
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# linkInternalFilters

O AppMeasurement oferece a capacidade de rastrear automaticamente links que apontam para fora do site. Se o [`trackExternalLinks`](trackexternallinks.md) estiver ativado, uma solicitação de imagem será enviada para a Adobe logo que um visitante clicar em um link para sair do site. As variáveis [`linkExternalFilters`](linkexternalfilters.md) e `linkInternalFilters` determinam quais links são considerados internos/externos.

Se essa variável tiver um valor, o rastreamento automático do link de saída se comportará como uma lista de bloqueios. Se um clique em um link não corresponder a algum valor `linkInternalFilters`, ele será considerado um link de saída. O URL inteiro é examinado em relação a essa variável. Se o [`linkLeaveQueryString`](linkleavequerystring.md) estiver ativado, a sequência de consulta também será examinada.

Se você usar `linkInternalFilters` e `linkExternalFilters` simultaneamente, o link clicado deverá corresponder a `linkExternalFilters` **e** não corresponder a `linkInternalFilters` para ser considerado um link de saída. Se um link clicado corresponder aos critérios do link de saída e do link de download, o tipo de link de download terá prioridade.

O Activity Map usa essa variável para ajudar a determinar quais links são internos ao site. A Adobe recomenda definir essa variável para implementações que usam o Activity Map.

>[!NOTE]
>
>`linkInternalFilters` e os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) são recursos separados que atendem a diferentes objetivos. A variável `linkInternalFilters` funciona especificamente para o rastreamento de link de saída. Os filtros de URL internos são uma configuração de administrador que ajuda com dimensões de origens de tráfego, como Domínio de referência.

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
