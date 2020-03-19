---
title: t
description: Envie uma chamada de rastreamento de exibição de página para a Adobe.
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# t

O método `t` é um componente principal importante do Adobe Analytics. Ele captura todas as variáveis do Analytics definidas na página, compila em uma solicitação de imagem e envia esses dados para os servidores de coleta de dados da Adobe.

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

A execução do método `t` utiliza todas as variáveis do Analytics definidas e formula um URL com base nessas variáveis. Algumas variáveis do Analytics determinam o URL da imagem, enquanto outras determinam os valores de parâmetro da string de consulta.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

A Adobe recebe a solicitação de imagem e analisa o cabeçalho da solicitação, o URL e os parâmetros da string de consulta. Os servidores de coleta de dados retornam uma imagem transparente com 1x1 pixels, exibida de maneira invisível em seu site.

## Chamada de rastreamento de exibição de página no Adobe Experience Platform Launch

O Launch tem um local dedicado definido para uma chamada de rastreamento de exibição de página.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e Enviar beacon no [!UICONTROL Tipo de ação].
6. Clique no botão de opção `s.t()`.

## Método s.t() no AppMeasurement e no editor de código personalizado do Launch

Chame o método `s.t()` quando quiser enviar uma chamada de rastreamento para a Adobe.

```js
s.t();
```

Como opção, você pode usar um objeto como argumento para substituir valores de variáveis. Consulte [substituições de variáveis](../../js/overrides.md) para obter mais informações.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] As versões anteriores do AppMeasurement usavam várias linhas de código para chamar essa função. O código adicional historicamente acomodava soluções alternativas para navegadores diferentes. A padronização e as práticas recomendadas dos navegadores modernos não exigem mais esse bloco de código. Somente a chamada do método `s.t()` é necessária agora.
