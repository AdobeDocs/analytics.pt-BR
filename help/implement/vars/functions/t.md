---
title: t
description: Envie uma chamada de rastreamento de exibição de página para a Adobe.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# t

O `t` método é um componente principal importante do Adobe Analytics. Ele pega todas as variáveis do Analytics definidas na página, as compila em uma solicitação de imagem e envia esses dados para os servidores de coleta de dados da Adobe.

Por exemplo, considere o seguinte código JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

A execução do `t` método utiliza todas as variáveis do Analytics definidas e formula um URL com base nessas variáveis. Algumas variáveis do Analytics determinam o URL da imagem, enquanto outras determinam os valores de parâmetro da string de consulta.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

A Adobe recebe a solicitação de imagem e analisa o cabeçalho da solicitação, o URL e os parâmetros da string de consulta. Os servidores de coleta de dados retornam uma imagem transparente de 1x1 pixels, invisível exibida em seu site.

## Chamada de rastreamento de exibição de página no Adobe Experience Platform Launch

A inicialização tem um local dedicado definido uma chamada de rastreamento de exibição de página.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone &#39;+&#39;
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como Enviar beacon.
6. Click the `s.t()` radio button.

## método s.t() no AppMeasurement e Iniciar editor de código personalizado

Chame o `s.t()` método quando quiser enviar uma chamada de rastreamento para a Adobe.

```js
s.t();
```

Como opção, você pode usar um objeto como argumento para substituir valores de variável. Consulte substituições [de](../../js/overrides.md) variáveis para obter mais informações.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] As versões anteriores do AppMeasurement usavam várias linhas de código para chamar essa função. O código adicional historicamente acomoda soluções alternativas para navegadores diferentes. A padronização e as práticas recomendadas nos navegadores modernos não exigem mais esse bloco de código. Somente a chamada de método `s.t()` é necessária agora.
