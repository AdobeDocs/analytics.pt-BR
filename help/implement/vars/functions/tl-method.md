---
title: tl
description: Envie uma chamada de rastreamento de link para a Adobe.
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
source-git-commit: 8ff414efff302adfee42f192e781a8dec5c42902
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 80%

---

# tl

O método `tl()` é um componente principal importante do Adobe Analytics. Ele captura todas as variáveis do Analytics definidas na página, compila em uma solicitação de imagem e envia esses dados para os servidores de coleta de dados da Adobe. Funciona de forma semelhante ao método [`t()`](t-method.md), no entanto, esse método não aumenta as exibições de página. É útil para rastrear links e outros elementos que não seriam considerados um carregamento de página completo.

Se [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) ou [`trackExternalLinks`](../config-vars/trackexternallinks.md) estiverem ativados, o AppMeasurement chama o método `tl()` automaticamente para enviar dados de rastreamento de links de download e de saída. Se sua organização preferir ter mais controle sobre os links a serem rastreados e o comportamento deles, você pode chamar o método `tl()` manualmente. Os links personalizados só podem ser acompanhados manualmente.

## Rastreamento de link usando o SDK da Web

O SDK da Web não diferencia entre chamadas de exibição de página e chamadas de rastreamento de link; ambos usam o `sendEvent` comando. Se quiser que o Adobe Analytics contabilize um determinado evento XDM como uma chamada de rastreamento de link, verifique se os dados XDM incluem ou estão mapeados para `web.webInteraction.name`, `web.webInteraction.URL`, e `web.webInteraction.type`.

* O nome do link mapeia para `web.webInteraction.name`.
* Vincular URL mapeia para `web.webInteraction.URL`.
* O tipo de link mapeia para `web.webInteraction.type`. Os valores válidos incluem `other` (Links personalizados), `download` (Links de download) e `exit` (Links de saída).

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

## Rastreamento de link usando a extensão do Adobe Analytics

A extensão do Adobe Analytics tem um local dedicado para definir uma chamada de rastreamento de link.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
1. Em [!UICONTROL Ações], clique na ação desejada ou clique no link **&#39;+&#39;** ícone para adicionar uma ação.
1. Defina o [!UICONTROL Extensão] lista suspensa para **[!UICONTROL Adobe Analytics]**, e o [!UICONTROL Tipo de ação] para **[!UICONTROL Enviar sinal]**.
1. Clique no botão de opção `s.tl()`.

Não é possível definir argumentos opcionais na extensão do Analytics.

## Método s.tl() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `s.tl()` quando quiser enviar uma chamada de rastreamento para a Adobe.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### Objeto Link (obrigatório)

O argumento do objeto Link determina se o navegador aguarda até 500 ms antes de sair da página. Se uma solicitação de imagem for enviada antes de 500 ms, a página navegará imediatamente para o link clicado.

>[!NOTE]
>
>O AppMeasurement ativa automaticamente a variável [`useBeacon`](../config-vars/usebeacon.md) para links de saída, tornando esse argumento desnecessário nos navegadores modernos. Esse argumento era usado com mais frequência em versões anteriores do AppMeasurement.

* `this`: aguarde até 500 ms para dar tempo ao AppMeasurement para enviar uma solicitação de imagem. Valor padrão.
* `true`: não espere.

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### Tipo de link (obrigatório)

O argumento tipo de link é uma sequência com apenas um caractere que determina o tipo de chamada de rastreamento de link. Há três valores válidos.

* `o`: o link é um [Link personalizado](/help/components/dimensions/custom-link.md).
* `d`: o link é um [Link de download](/help/components/dimensions/download-link.md).
* `e`: o link é um [Link de saída](/help/components/dimensions/exit-link.md).

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### Nome do link (recomendado)

O argumento do nome do link é uma string que determina o item de dimensão do rastreamento do link. Ao usar as dimensões [Link personalizado](/help/components/dimensions/custom-link.md), [Link de download](/help/components/dimensions/download-link.md) ou [Link de saída](/help/components/dimensions/exit-link.md) nos relatórios, esta cadeia de caracteres contém o item de dimensão. Se esse argumento não for definido, a variável [linkURL](../config-vars/linkurl.md) será usada.

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### Substituições de variáveis (opcional)

Permite alterar os valores de variáveis para uma única chamada. Consulte [substituições de variáveis](../../js/overrides.md) para obter mais informações.

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

### Evite rastrear links duplicados

Se `trackDownloadLinks` ou `trackExternalLinks` estiverem ativados, o AppMeasurement faz uma chamada de rastreamento de link automaticamente se os filtros corretos coincidirem. Se você também chamar `s.tl()` manualmente para esses cliques em links, pode ser que envie dados duplicados à Adobe. Dados duplicados aumentam os números nos relatórios e os tornam menos precisos.

Por exemplo, a função a seguir enviaria duas chamadas de rastreamento de link para o mesmo clique de link (links de download manuais e automáticos):

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

Você pode ajudar a impedir chamadas de rastreamento de link duplicadas usando a função modificada a seguir. Verifica primeiro se um objeto de link existe e envia apenas uma chamada de rastreamento de link manual se o objeto do link for uma string vazia.

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
