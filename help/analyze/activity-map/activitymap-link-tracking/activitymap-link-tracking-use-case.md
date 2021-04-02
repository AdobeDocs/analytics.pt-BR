---
description: É possível diferenciar os links com a personalização da ID do link usando a variável s_objectID, a região e o arquivo de módulo AppMeasurement Activity Map.
title: Diferenciar links que fazem referência à mesma ID e Região do link
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 61%

---


# Diferenciar links que fazem referência à mesma ID e Região do link

É possível diferenciar os links com a personalização da ID do link usando a variável s_objectID, a região e o arquivo de módulo AppMeasurement Activity Map.

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
    Compre<br/>
     <br/>
     <br/>
    Compre<br/>
     <br/>
     <br/>
    Compre<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    painel de recomendação<br/>
     <br/>
     <br/>
    painel de recomendação<br/>
     <br/>
     <br/>
    painel de recomendação<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

Como é possível personalizar a página da Web e usar tags para diferenciar os valores desses links? Existem três opções: você pode personalizar a ID do link ou personalizar a região, ou personalizar o arquivo de módulo AppMeasurement Activity Map.

## Personalizar a ID do link usando a variável s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Ao criar uma ID de objeto exclusiva, `s_objectID`, para um link ou um local de link em uma página, é possível melhorar o rastreamento de Activity Map ou usar o Activity Map para relatar sobre um tipo de link ou um local, em vez do URL do link. Clique [aqui](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/page-variables.html) para obter mais informações sobre a variável `s_objectID`

>[!IMPORTANT]
>
>Observe que é necessário um ponto e vírgula (`;`) ao usar `s_objectID` no Activity Map.
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
    Produto3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    painel de recomendação<br/>
     <br/>
     <br/>
    painel de recomendação<br/>
     <br/>
     <br/>
    painel de recomendação<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar a região  {#section_6B1EF302573B445DBAF44176D0A12DB9}

Você pode personalizar a região, garantindo que cada link &quot;Comprar&quot; tenha sua própria Região definida. Para fazer isso, adicione um parâmetro `"id"` a um dos pais de cada tag de âncora &quot;Comprar&quot;.

>[!NOTE]
>Você não está estritamente limitado ao parâmetro `"id"` como um identificador de região. Também é possível definir seu próprio identificador usando a variável JavaScript `"s.ActivityMap.regionIDAttribute"`.
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
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
    Compre<br/>
     <br/>
     <br/>
    Compre<br/>
     <br/>
     <br/>
    Compre<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    região a<br/>
     <br/>
     <br/>
    região b<br/>
     <br/>
     <br/>
    região c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizar o arquivo de módulo AppMeasurement Activity Map  {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
Certifique-se de testar o código modificado para garantir seu funcionamento. A Adobe não é responsável pela forma como o código modificado se comporta.

Veja alguns exemplos de funções de link/região **genéricas** que podem ser incluídas (em forma modificada) no arquivo AppMeasurement.js.

```
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

O `linkName` é transmitido durante as chamadas para `s.tl()`.

```
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
