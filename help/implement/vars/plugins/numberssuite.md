---
title: Conjunto de números
description: Produza e manipule números para uso em outras variáveis JavaScript.
feature: Appmeasurement Implementation
exl-id: 7af88dce-baf3-4581-b5b6-0d6e41922266
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 89%

---

# Plug-in da Adobe: Conjunto de números

{{plug-in}}

O Numbers Suite inclui uma série de funções JavaScript. Inclui os seguintes plug-ins:

* **`zeroPad`**: adicione um número específico de zeros ao início de um número. Esse plug-in é útil se uma variável exigir um determinado número de dígitos, como se você trabalhasse com objetos de data JavaScript e quisesse formatar o mês e o dia de uma data com dois dígitos em vez de apenas um dígito. Por exemplo, `01/09/2020` em vez de `1/9/2020`.
* **`randomNumber`**: gere um número aleatório com um número específico de dígitos. Esse plug-in é útil se você implantar tags de terceiros e quiser um número aleatório para substituição de cache.
* **`twoDecimals`**: arredonde um número até a centena que estiver mais próxima. Esse plug-in é útil para fins monetários e permite arredondar um número para um valor monetário válido.

## Instale o plug-in usando a extensão Web SDK ou Web SDK

Este plug-in ainda não é compatível com o Web SDK.

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
   * Tipo de ação: inicializar Numbers Suite
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
/* Adobe Consulting Plugin: zeroPad v1.0 */
function zeroPad(num,nod){num=parseInt(num);nod=parseInt(nod);if(isNaN(num)||isNaN(nod))return"";var c=nod-num.toString().length+ 1;return Array(+(0<c&&c)).join("0")+num};

/* Adobe Consulting Plugin: randomNumber v2.0 (zeroPad plug-in optional)*/
function randomNumber(nod){nod="number"===typeof nod?17>Math.abs(nod)?Math.round(Math.abs(nod)):17:10;for(var a="1",c=0;c<nod;c++) a+="0";a=Number(a);a=Math.floor(Math.random().toFixed(nod)*a)+"";a.length!==nod&&"undefined"!==typeof zeroPad&&(a=zeroPad(a,nod)); return a};

/* Adobe Consulting Plugin: twoDecimals v1.0 */
function twoDecimals(v){return"undefined"===typeof v||void 0===v||isNaN(v)?0:Number(Number(v).toFixed(2))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar os plug-ins

A função `zeroPad` usa os seguintes argumentos:

* **num** (obrigatório, inteiro): o número a ser arredondado. A função arredondará para baixo o valor desse argumento se este contiver decimais.
* **nod** (obrigatório, inteiro): o número de dígitos no valor final de retorno. Se o número a ser arredondado tiver menos dígitos do que o número limite de dígitos, o plug-in adicionará zeros no início do argumento `num`.

A função `randomNumber` usa os seguintes argumentos:

* **nod** (opcional, inteiro): o número de dígitos no número aleatório que você deseja gerar. O valor máximo é 17 dígitos. O valor padrão é 10 dígitos.

A função `twoDecimals` usa os seguintes argumentos:

* **val** (obrigatório, número): um número (representado por uma string ou por um objeto numérico) que você deseja arredondar para a centena mais próxima.

## Devoluções

* A função **zeroPad** retorna uma string igual ao argumento `num`, mas com um número específico de zeros adicionados ao início de seu valor, o que garante que o valor de retorno tenha o número correto de dígitos.
* A função **randomNumber** retorna uma string igual a um número aleatório com o número desejado de dígitos.
* A função **twoDecimals** retorna um objeto numérico arredondado para a centena mais próxima.

## Exemplos de chamadas

### exemplos de zeroPad

```js
s.eVar25 = zeroPad(25.5562, 5) //sets eVar25 equal to "00025"

s.prop1 = zeroPad(25, 1) //sets prop1 equal to "25"

s.prop1 = zeroPad(232425235,23) //sets prop1 equal to "00000000000000232425235"
```

### exemplos de randomNumber

```js
s.eVar65 = randomNumber(15) //sets eVar65 equal to "721759731750342" or some other random 15-digit number

randomNumber() //returns a random 10-digit number but is useless since this isn't used in an expression

var j = randomNumber(35) //sets a variable named j equal to "15476068651810060" or another random 17-digit number
```

### exemplos de twoDecimals

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Histórico da versão

### 1.0 (25 de maio de 2019)

* Versão inicial.
