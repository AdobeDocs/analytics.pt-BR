---
title: tl
description: Envie uma chamada de rastreamento de link para a Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# tl

O `tl()` método é um componente principal importante do Adobe Analytics. Ele pega todas as variáveis do Analytics definidas na página, as compila em uma solicitação de imagem e envia esses dados para os servidores de coleta de dados da Adobe. Funciona de forma semelhante ao [`t()`](t-method.md) método, no entanto, esse método não aumenta as exibições de página. É útil para rastrear links e outros elementos que não seriam considerados um carregamento de página completo.

Se [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) ou [`trackExternalLinks`](../config-vars/trackexternallinks.md) estiver ativado, o AppMeasurement chama automaticamente o `tl()` método para enviar dados de rastreamento de link de download e saída. Se sua organização preferir ter mais controle sobre os links para rastrear e seu comportamento, você pode chamar o `tl()` método manualmente. Os links personalizados só podem ser acompanhados manualmente.

## Chamada de rastreamento de link no Adobe Experience Platform Launch

O Launch tem um local dedicado definido uma chamada de rastreamento de link.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
1. Em [!UICONTROL Actions], clique no ícone &#39;+&#39;
1. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e a opção [!UICONTROL Action Type] Enviar beacon.
1. Click the `s.tl()` radio button.

Não é possível definir argumentos opcionais no Launch.

## método s.tl() no AppMeasurement e Iniciar editor de código personalizado

Chame o `s.tl()` método quando quiser enviar uma chamada de rastreamento para a Adobe.

```js
s.tl();
```

Como opção, esse método aceita vários argumentos:

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objeto Link

O argumento do objeto link determina se o navegador aguarda até 500 ms antes de sair da página. Se uma solicitação de imagem for enviada antes de 500 ms, a página navegará imediatamente para o link clicado.

> [!NOTE] O AppMeasurement ativa automaticamente a [`useBeacon`](../config-vars/usebeacon.md) variável para links de saída, tornando esse argumento desnecessário nos navegadores modernos. Esse argumento era usado com mais frequência em versões anteriores do AppMeasurement.

* `this`: aguarde até 500 ms para dar tempo ao AppMeasurement para enviar uma solicitação de imagem. Valor padrão.
* `true`: não espere.

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### Tipo de link

O argumento de tipo de link é uma sequência de caracteres de letra única que determina o tipo de chamada de rastreamento de link. É o mesmo que definir a [`linkType`](../config-vars/linktype.md) variável.

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### Nome do link

O argumento do nome do link é uma string que determina o valor da dimensão de rastreamento do link. É o mesmo que definir a [`linkName`](../config-vars/linkname.md) variável.

```js
s.tl(true,"d","Example download link");
```

### Substituições de variável

Permite alterar os valores de variáveis para uma única chamada. Consulte substituições [de](../../js/overrides.md) variáveis para obter mais informações.

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## Exemplos e casos de uso

Envie uma chamada básica de rastreamento de link diretamente dentro de um link HTML:

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

Use o JavaScript para fazer uma chamada básica de rastreamento de link usando argumentos de método:

```JavaScript
s.tl(true,"o","Example link");
```

Use o JavaScript para fazer a mesma chamada básica de rastreamento de link usando variáveis separadas:

```js
s.linkType = "o";
s.linkName = "Example link";
s.tl();
```

### Efetuar chamadas de rastreamento de link em uma função personalizada

Você pode consolidar o código de rastreamento de link em uma função JavaScript independente definida na página ou em um arquivo JavaScript vinculado. As chamadas podem ser feitas na função onClick de cada link. Defina o seguinte em um arquivo JavaScript:

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

Em seguida, você pode chamar a função sempre que quiser rastrear um determinado link:

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### Evitar rastrear links duplicados

Se `trackDownloadLinks` ou `trackExternalLinks` estiverem ativados, o AppMeasurement faz automaticamente uma chamada de rastreamento de link se os filtros corretos coincidirem. Se você também chamar manualmente `s.tl()` esses cliques em links, poderá enviar dados duplicados para a Adobe. Dados duplicados aumentam os números de relatórios e os tornam menos precisos.

Por exemplo, a função a seguir enviaria duas chamadas de rastreamento de link para o mesmo clique de link (links de download manuais e automáticos):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Você pode ajudar a impedir chamadas de rastreamento de link duplicadas usando a seguinte função modificada. Primeiro, verifica se um objeto de link existe e envia apenas uma chamada de rastreamento de link manual se o objeto de link for uma string vazia.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
