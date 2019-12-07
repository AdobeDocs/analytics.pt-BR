---
description: É possível rastrear automaticamente os downloads de arquivo e links de saída com base nos parâmetros definidos no arquivo AppMeasurement para JavaScript.
keywords: Analytics Implementation
subtopic: Link tracking
title: A função s.tl() - Rastreamento de link
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# A função s.tl() - Rastreamento de link

Se a empresa preferir ter mais controle sobre os links de rastreamento e seu comportamento, o rastreamento manual de links é recomendado. Use a função s.tl() para enviar manualmente as solicitações de imagem do rastreamento de link com o conteúdo exato desejado. Se o rastreamento básico de link for suficiente, consulte `s.trackDownloadLinks` e `s.trackExternalLinks` em [Variáveis de configuração](c-variables/configuration-variables.md). Os links personalizados não podem ser rastreados automaticamente.

> [!NOTE] O código de rastreamento de link geralmente é muito específico para as necessidades do site e de relatórios. A Adobe recomenda uma experiência de implementação prévia ou um consultor de implementação para entender como usar esse recurso com base nas necessidades comerciais.

## Sintaxe e exemplos

Sintaxe básica:

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

Exemplos básicos:

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true (obrigatório)

O primeiro argumento determina se o navegador aguarda até 500 ms antes de sair da página. Se uma solicitação de imagem for enviada antes de 500 ms, a página navegará imediatamente para o link clicado.

* `this`: aguarde até 500 ms para dar tempo ao AppMeasurement para enviar uma solicitação de imagem. Valor padrão.
* `true`: não espere. Se o link sair da página, é possível que uma solicitação de imagem não seja enviada.

O atraso só é necessário quando um link sai da página.

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType (obrigatório)

O segundo argumento tem três valores válidos, dependendo do tipo de link que você deseja capturar. Ele determina a dimensão que a solicitação de imagem preenche no Adobe Analytics.

* `d`: Downloads de Arquivos
* `e`: Links de saída
* `o`: links personalizados

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName (obrigatório)

Esse argumento pode ser qualquer valor personalizado até 100 caracteres. Ele determina o valor da dimensão no relatório.

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides (opcional)

Permite alterar os valores de variáveis para uma única chamada. Se você usar o argumento doneAction e não tiver substituições de variável, use `null`.

### doneAction (opcional)

Especifica uma ação de navegação a ser executada após a conclusão da chamada de rastreamento de link. Requer o uso de `s.useForcedLinkTracking` e `s.forcedLinkTrackingTimeout`. A variável doneAction pode ser a string `navigate`, o que faz com que o método defina `document.location` como o atributo href de `linkObject`. A variável doneAction também pode ser uma função que permite a personalização avançada.

Se você fornecer um valor para doneAction em um `onClick` evento de âncora, deverá retornar `false` depois da chamada de `s.tl` para impedir a navegação padrão do navegador.
Para refletir o comportamento padrão e seguir o URL especificado pelo atributo href, forneça uma string de `navigate` como o doneAction. Como opção, você pode fornecer sua própria função para lidar com o evento de navegação ao passar essa função como doneAction.

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## Uso das funções JavaScript com rastreamento de link

Você pode consolidar o código de rastreamento de link em uma função JavaScript independente definida na página ou em um arquivo JavaScript vinculado. As chamadas podem ser feitas na função onClick de cada link.

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## Como evitar contagens de link duplicadas {#section_9C3F73DE758F4727943439DED110543C}

É possível que os links dupliquem a contagem nas situações em que o link normalmente é capturado pelo download automático de arquivos ou pelo rastreamento de links de saída. Por exemplo, se você estiver rastreando downloads de PDF automaticamente, uma chamada de `s.tl` resulta em uma contagem de download duplicada:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

Para garantir que a dupla contagem do link não ocorra, use a seguinte função do JavaScript modificada:

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
