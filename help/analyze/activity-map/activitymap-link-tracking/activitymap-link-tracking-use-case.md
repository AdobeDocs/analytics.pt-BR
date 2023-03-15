---
description: É possível diferenciar os links personalizando a ID do link por meio da variável s_objectID, a região e o arquivo de módulo AppMeasurement ActivityMap.
title: Diferenciar links que fazem referência à mesma ID e região do link
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: User, Admin
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 100%

---

# Diferenciar links que fazem referência à mesma ID e Região do link

É possível diferenciar os links com a personalização da ID do link usando a variável s_objectID, a região e o arquivo de módulo AppMeasurement ActivityMap.

Como exemplo, digamos que você tenha vários links “Buy”, que são identificados pelo Activity Map sob a mesma ID de link e Região:

<table id="table_3020E2C0175D455C84E794CF51BE5A93">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Amostra de código </th>
   <th colname="col2" class="entry"> ID do link </th>
   <th colname="col3" class="entry"> Região </th>
  </tr>
 </thead>
  <tbody>
  <tr>
   <td colname="col1">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

Como é possível personalizar a página da Web e usar tags para diferenciar os valores desses links? Existem três opções: você pode personalizar a ID do link ou personalizar a região, ou personalizar o arquivo de módulo AppMeasurement ActivityMap.

## Personalizar a ID do link usando a variável s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Ao criar uma ID de objeto única (`s_objectID`) para um link ou um local de link em uma página, você pode melhorar o rastreamento do Activity Map ou usá-lo para informar sobre um tipo de link ou um local, em vez do URL do link. Clique [aqui](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=pt-BR) para obter mais informações sobre a variável `s_objectID`.

>[!IMPORTANT]
>
>Observe que é necessário um ponto e vírgula (`;`) ao usar o `s_objectID` no Activity Map.

<table id="table_9439A5F320304E439A19842CF3EBA456">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Amostra de código </th>
   <th colname="col2" class="entry"> ID do link </th>
   <th colname="col3" class="entry"> Região </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar a região {#section_6B1EF302573B445DBAF44176D0A12DB9}

Você pode personalizar a região certificando-se de que cada link “Buy” tenha a sua própria região definida. Para fazer isso, adicione um parâmetro `"id"` a um dos principais de cada tag de âncora “Buy”.

>[!NOTE]
>
>Você não está estritamente limitado ao parâmetro `"id"` como um identificador de região. Também é possível definir o seu próprio identificador usando a variável de JavaScript `"s.ActivityMap.regionIDAttribute"`.

<table id="table_250DB52A869C466B942517BABA1C287B">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Amostra de código </th>
   <th colname="col2" class="entry"> ID do link </th>
   <th colname="col3" class="entry"> Região </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    region a<br/>
     <br/>
     <br/>
    region b<br/>
     <br/>
     <br/>
    region c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar o arquivo de módulo AppMeasurement ActivityMap {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Teste o código modificado para garantir seu funcionamento correto. A Adobe não é responsável pela forma como o código modificado se comporta.

Veja alguns exemplos de funções de link/região **genéricas** que podem ser incluídas (em forma modificada) no arquivo AppMeasurement.js.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

O `linkName` é transmitido durante as chamadas para o `s.tl()`.

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
