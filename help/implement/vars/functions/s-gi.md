---
title: s_gi()
description: Crie e rastreie instâncias do AppMeasurement.
feature: Appmeasurement Implementation
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# s_gi

A função `s_gi()` instancia ou encontra uma instância do AppMeasurement pelo ID de conjunto de relatórios. O AppMeasurement acompanha cada instância criada e `s_gi()` retorna a instância existente para um conjunto de relatórios, se existir. Se uma instância não existe, uma nova instância é criada.

## Instanciar um objeto de rastreamento usando a extensão do SDK da Web

A extensão do SDK da Web instancia e gerencia o objeto de rastreamento para você. No entanto, é possível personalizar o nome do objeto de rastreamento nas configurações da extensão:

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no SDK da Web da Adobe Experience Platform.
1. Altere o campo [!UICONTROL Nome] para o valor desejado. Seu valor padrão é `alloy`.

## Instanciar um objeto de rastreamento manualmente implementando o SDK da Web

O código a seguir carrega o SDK da Web e instancia um objeto de rastreamento. É possível personalizar o nome do objeto de rastreamento alterando a string `"alloy"` no final do script integrado para o valor desejado.

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

Consulte [Instalação do SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR) na documentação do SDK da Web para obter mais informações.

## Instanciar um objeto de rastreamento usando a extensão do Adobe Analytics

A extensão do Analytics instancia e gerencia o objeto de rastreamento para você. No entanto, também é possível definir um objeto de rastreamento global na opção [!UICONTROL Gerenciamento de biblioteca] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Gerenciamento de biblioteca] e selecione qualquer botão de opção diferente de [!UICONTROL Gerenciar a biblioteca para mim].

O campo de texto da variável global permite definir um objeto de rastreamento personalizado. O valor padrão é `s`.

## s_gi() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame a função `s_gi()` para instanciar um objeto de rastreamento. Seu único argumento contém uma string delimitada por vírgulas com IDs de conjuntos de relatórios. O argumento ID de conjunto de relatórios é obrigatório.

>[!TIP]
>
>A Adobe recomenda usar a variável `s` como um objeto de rastreamento. A Adobe usa `s` em sua documentação, em exemplos de implementação e em plug-ins. No entanto, você pode usar qualquer variável desde que seja consistente em todo o site.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
>As seções e exemplos a seguir contêm tópicos complexos sobre implementação. Teste sua implementação minuciosamente e rastreie personalizações importantes no [documento de design da solução](../../prepare/solution-design.md) de sua organização.

## Gerenciar várias implementações usando diferentes objetos de rastreamento

Você pode enviar dados diferentes para conjuntos de relatórios diferentes se instanciar vários objetos de rastreamento. Esses dois objetos de rastreamento operam independentemente um do outro.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Restaurar variáveis do AppMeasurement após substituir o objeto s

Algumas ferramentas de terceiros também podem usar o objeto `s` do JavaScript. Se você substituir acidentalmente o objeto `s` no site, será possível chamar `s_gi` com o mesmo argumento de string RSID para restaurar todas as variáveis e métodos substituídos.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Referencie o mesmo objeto de rastreamento com várias variáveis

Se duas variáveis referenciarem a mesma função `s_gi()` com o mesmo conjunto de relatórios, você poderá usar as variáveis alternadamente.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
