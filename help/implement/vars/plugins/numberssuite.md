---
title: ' Conjunto de números'
description: Produza e manipule números para uso em outras variáveis JavaScript.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Plug-in da Adobe: Conjunto de números

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

Os Números Suite incluem uma série de funções JavaScript. Inclui os seguintes plug-ins:

* **`zeroPad`**: Adicione um número específico de zeros ao início de um número. Esse plug-in é útil se uma variável exigir um determinado número de dígitos, como se você trabalhasse com objetos de data JavaScript e quisesse formatar um mês e dia de data com dois dígitos em vez de apenas um dígito. Por exemplo,`01/09/2020`em vez de`1/9/2020`.
* **`randomNumber`**: Gere um número aleatório com um número específico de dígitos. Esse plug-in é útil se você implantar tags de terceiros e quiser um número aleatório de cache busting.
* **`twoDecimals`**: Arredondar um número até o centésimo do armário. Esse plug-in é útil para fins monetários, permitindo arredondar um número para um valor monetário válido.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Para qualquer Regra de inicialização em que você deseja usar o plug-in, adicione uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar addProductEvar
1. Salvar e publicar as alterações na regra

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código] personalizado, que revela o botão [!UICONTROL Abrir editor] .
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando `s_gi`). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

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

O `zeroPad` método usa os seguintes argumentos:

* **num** (obrigatório, inteiro): O número a ser colado. O método arredonda o valor desse argumento para baixo se contiver decimais.
* **nod** (obrigatório, inteiro): O número de dígitos no valor final de retorno. Se o número a ser colado tiver menos dígitos do que o número de dígitos a serem colados, o plug-in adicionará zeros ao início do `num` argumento.

O `randomNumber` método usa os seguintes argumentos:

* **nod** (opcional, número inteiro): O número de dígitos no número aleatório que você deseja gerar. O valor máximo é 17 dígitos. O valor padrão é 10 dígitos.

O `twoDecimals` método usa os seguintes argumentos:

* **val** (obrigatório, número): Um número (representado por uma string ou por um objeto numérico) que você deseja arredondar para o centésimo mais próximo.

## Devoluções

* O método **zeroPad** retorna uma string igual ao `num` argumento, mas com um número específico de zeros adicionados ao início de seu valor, o que garante que o valor de retorno tenha o número correto de dígitos.
* O método **randomNumber** retorna uma string igual a um número aleatório com o número desejado de dígitos.
* O método **twoDecimals** retorna um objeto number arredondado para o centésimo mais próximo.

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

### exemplos de duas casas decimais

```js
s.events = "event10=" + twoDecimals("85.4827128694") //sets s.events="event10=85.48"

var fivehundredthirtytwo = twoDecimals(532.000000001) //sets the variable fivehundredthirtytwo equal to 532

s.eVar65 = twoDecimals("672132.9699736457") //sets s.eVar65 equal to 672132.97
```

## Histórico da versão

### 1.0 (25 de maio de 2019)

* Versão inicial.
