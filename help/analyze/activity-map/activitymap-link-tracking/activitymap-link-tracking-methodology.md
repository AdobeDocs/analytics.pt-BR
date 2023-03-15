---
description: Essa seção destina-se aos Administradores do Adobe Analytics. Tem como foco os novos parâmetros de rastreamento de links e como eles garantem a singularidade do link e a consistência entre navegadores e dispositivos, além de melhorar a manipulação do reposicionamento do link em uma página.
title: Metodologia de Rastreamento de links
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 100%

---

# Metodologia de Rastreamento de links

Essa seção destina-se aos Administradores do Adobe Analytics. Tem como foco os novos parâmetros de rastreamento de links e como eles garantem a singularidade do link e a consistência entre navegadores e dispositivos, além de melhorar a manipulação do reposicionamento do link em uma página.

>[!IMPORTANT]
>
>Qualquer link cujo texto (não o href) possa conter PII (Informações de identificação pessoal) deve ser implementado de maneira explícita usando [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=pt-BR) ou excluindo a coleção de links do ActivityMap por meio de [s.ActivityMap.linkExclusions ou s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Para obter mais informações sobre como o Activity Map pode coletar dados de PII, acesse [aqui](/help/analyze/activity-map/lnk-tracking-overview.md).

O Activity Map baseia seu rastreamento de links nessas duas IDs:

* ID primária: este é o parâmetro reconhecível do link.
* Região do link: este é um parâmetro secundário, que permite aos usuários especificar uma cadeia de caracteres que representa a área total do link na página ou região. Esse parâmetro pode ser gerado automaticamente se não for fornecido pelo usuário.

## ID primária {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se o HTML tiver uma função s_objectid, então a ID primária é padronizada para s_objectid. Caso contrário, os seguintes parâmetros são usados &#x200B;&#x200B;como ID primária (nesta ordem de prioridade):

* InnerText
* AltText
* Título
* Src
* Ação

## Usar o InnerText, em vez da Ação do link (URL) {#section_70C3573E22274522A8CC035BF18EC468}

A ação do link é a medida tomada pela página da Web quando o link é clicado, geralmente o URL que é visitado depois de clicar no link. Alguns dos problemas que você pode enfrentar ao usar a Ação do link são:

* ter dois ou mais links diferentes com a mesma ID
* a leitura do link
* um link com múltiplas ações (dependendo do dispositivo em que o link é exibido)

Como resultado, usamos o InnerText com essas vantagens, em vez da Ação do link (URL):

* É uma boa representação da identidade do link. A duplicação da ID primária é significativamente reduzida, pois não é comum ter vários links com o mesmo texto.
* Isso garante a consistência da ID primária em todos os tipos de dispositivos e navegadores.
* Ela não é afetada por um reposicionamento de link na página.
* Melhora a leitura, assim os usuários podem iniciar a análise dos relatórios de Rastreamento do link fora do Activity Map.

## Região do link {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Este novo atributo permite aos usuários especificar uma cadeia de caracteres que representa a região da página onde o link está localizado.

Por exemplo, para um link “Fale Conosco”, que está localizado na seção Menu da página da Web, o usuário pode querer passar um parâmetro de região “Menu”. Da mesma forma, para um link “Fale Conosco” localizado no rodapé da página da Web, o parâmetro de região pode ser definido como “Rodapé”.

O valor da Região do link não está definido no próprio link, mas em um elemento HTML acima da árvore DOM HTML que engloba a região.
O uso da Região do link tem os seguintes benefícios:

* Ajuda a diferenciar os links com a mesma ID primária.
* As tendências em uma região são menos afetadas pelo aspecto dinâmico da página da Web.
* Os usuários podem ver os links com melhor desempenho dentro de uma região. Com Região como uma âncora, podemos mostrar as sobreposições de links que não estão visíveis atualmente na página (Ajax, Direcionamento).
* A Região pode substituir páginas, já que uma determinada região pode ser usada em várias páginas da Web. Ela ajuda a responder a perguntas como: &quot;A região de &quot;Ofertas de produtos&quot; tem um melhor desempenho na página inicial para mulheres ou para homens?&quot;
* A Região é uma dimensão relevante para analisar as páginas da Web altamente dinâmicas. Isso ocorre porque ela remove o ruído, devido aos links em mudança contínua: uma Região de “Notícias recentes” na página de aterrissagem CNN pode conter vários links dinâmicos. Mas a região vai estar sempre lá. Dessa forma, pode ser interessante direcionar a nível de Região durante muitos dias.

**Rastreamento de região personalizada**

É possível personalizar o parâmetro Região para um link (o padrão é uma ID do link): um conjunto de tags definido como “ID” vai usar todos os elementos HTML que tenham um parâmetro “id” como uma Região. Assim, definir a tag de Região para &quot;id&quot; provavelmente retornará várias regiões distintas (assim como existem diferentes &quot;IDs&quot; na página). Como alternativa, se você quiser uma implementação mais personalizada, é possível definir a tag Região para algo mais específico, como “region_id”.

Abaixo, é possível observar alguns exemplos de HTML que usam o atributo padrão de ID da região, a “id”.

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

Se desejar, é possível marcar elementos com um identificador de strings arbitrário - neste caso, “lpos” - e depois adicionar atributos com o nome “lpos”.

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## Variáveis de configuração {#configuration-vars}

Observe que essas variáveis &#x200B;&#x200B;estão listadas apenas para fins de referência. O Activity Map deve ser configurado adequadamente para instalação, mas é possível personalizar a sua implementação usando essas variáveis.

### `s.ActivityMap.regionIDAttribute`

String que identifica o atributo da tag para usar como ID da região de algum elemento ascendente (pai, pai.pai, ...) de `s.linkObject`, ou seja, **o elemento que foi clicado**.

**Exemplo**

Padrões para o parâmetro “id”. Você pode definir para outro parâmetro.

### `s.ActivityMap.link`

Função que recebe o `HTMLElement` clicado e deve retornar um valor de sequência de caracteres que representa o link que foi clicado. Se o valor de retorno for falso (nulo, indefinido, cadeia de caracteres vazia, 0), nenhum link será rastreado.

**Exemplo**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

A função que recebe o HTMLElement clicado e deve retornar um valor de string que representa **a região onde o link foi encontrado quando clicado.** Se o valor de retorno for falso (nulo, indefinido, cadeia de caracteres vazia, 0), nenhum link será rastreado.

**Exemplo**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

Uma sequência de caracteres que recebe uma lista de sequências de caracteres separadas por vírgula para pesquisa no texto do link. Caso encontrado, o link deixará de ser rastreado pelo Activity Map. Caso não esteja definido, nenhuma tentativa foi feita para interromper o rastreamento do link no Activity Map.

**Exemplo**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

Uma sequência de caracteres que recebe uma lista de sequências de caracteres separadas por vírgula para pesquisa no texto da região. Caso encontrado, o link deixará de ser rastreado pelo Activity Map. Caso não esteja definido, nenhuma tentativa foi feita para interromper o rastreamento do link no Activity Map.

**Exemplo**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```
