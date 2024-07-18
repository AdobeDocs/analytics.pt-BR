---
title: getPageName
description: Crie um pageName fácil de ler a partir do caminho do site atual.
feature: Variables
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 75%

---

# Plug-in da Adobe: getPageName

{{plug-in}}

O plug-in `getPageName` cria uma versão formatada amigável e fácil de ler do URL atual. A Adobe recomenda usar esse plug-in se você quiser um valor de [`pageName`](../page-vars/pagename.md) fácil de definir e de entender nos relatórios. Esse plug-in será desnecessário se você já tiver uma estrutura de nomeação para a variável `pageName`, como por meio de uma camada de dados. Ele é melhor usado quando você não tem outra solução para definir a variável `pageName`.

## Instale o plug-in usando a extensão SDK da Web

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o SDK da Web.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Marcas]** à esquerda e clique na propriedade de marca desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda e na guia **[!UICONTROL Catálogo]**
1. Localize e instale a extensão **[!UICONTROL Plug-ins comuns do SDK da Web]**.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda e, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: plug-ins comuns do SDK da Web
   * Elemento de Dados: `getPageName`
1. Defina os parâmetros desejados à direita.
1. Salve e publique as alterações no elemento de dados.

## Instale o plug-in implementando manualmente o SDK da Web

Este plug-in ainda não é compatível com uma implementação manual do SDK da Web.

## Instale o plug-in usando a extensão Adobe Analytics.

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getPageName
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão de plug-in de plug-ins comuns do Analytics, poderá usar o editor de código personalizado.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getPageName` usa os seguintes argumentos:

* **`si`** (opcional, string): uma ID inserida no início da string que representa a ID do site. Esse valor pode ser uma ID numérica ou um nome amigável. Quando não estiver definido, o padrão será o domínio atual.
* **`qv`** (opcional, string): uma lista, delimitada por vírgulas, de parâmetros da string de consulta que, se encontrados no URL, são adicionados à string
* **`hv`** (opcional, string): uma lista de parâmetros delimitada por vírgulas encontrada no hash do URL que, se encontrados no URL, são adicionados à string
* **`de`** (opcional, string): o delimitador usado para dividir partes individuais da string. O padrão é uma barra vertical (`|`).

A função retorna uma string que contém uma versão amigável da URL. Normalmente, essa string é atribuída à variável `pageName`, mas também pode ser usada em outras variáveis.

## Exemplos

```js
// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "mail.example.com|mail|u|0".
s.pageName = getPageName();

// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "example|mail|u|0".
s.pageName = getPageName("example");

// Given the URL https://www.example.com/, sets the page variable to "www.example.com|home".
// When the code runs on a URL that does not contain a path, it always adds the value of "home" to the end of the return value.
s.pageName = getPageName();

// Given the URL https://www.example.com/, sets the page variable to "example|home".
s.pageName = getPageName("example","","","|");

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "www.example.com|en|booking|room-booking.html".
s.pageName = getPageName();

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "example: en: booking: room-booking.html: cid=1235: arrive=05-26: numGuests=2"
s.pageName = getPageName("example","cid","arrive,numGuests",": ");
```

## Melhorias em relação às versões anteriores

A versão 4.0+ do plug-in `getPageName` não depende da existência do objeto AppMeasurement do Adobe Analytics (ou seja, do objeto `s`). Se você atualizar para esta versão, altere o código que chama o plug-in removendo qualquer instância do objeto `s` da chamada. Por exemplo, altere `s.getPageName();` para `getPageName();`.

## Histórico da versão

### 4.2 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 4.1 (17 de setembro de 2019)

* Delimitador padrão alterado para um caractere de barra vertical (era dois pontos + espaço).

### 4.0 (22 de maio de 2018)

* Reanálise/reescrita completa do plug-in
