---
title: getGeoCoordenates
description: Rastrear a geoLocation de um visitante.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Plug-in da Adobe: getGeoCoordenates

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getGeoCoordinates` plug-in permite capturar a latitude e a longitude dos dispositivos dos visitantes. A Adobe recomenda usar esse plug-in se desejar capturar dados de localização geográfica nas variáveis do Analytics.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Catalog] botão
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar getGeoCoordination
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão na extensão do Adobe Analytics.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getGeoCoordinates v1.0 */
s.getGeoCoordinates=function(){var d=this,b="",a=d.c_r("s_ggc").split("|"),e={timeout:5E3,maximumAge:0},f=function(c){c=c.coords;var a=new Date;a.setTime(a.getTime()+18E5);d.c_w("s_ggc",parseFloat(c.latitude.toFixed(4))+"|"+parseFloat(c.longitude.toFixed(4)),a); b="latitude="+parseFloat(c.latitude.toFixed(4))+" | longitude="+parseFloat(c.longitude.toFixed(4))},g=function(a){b="error retrieving geo coordinates"};1<a.length&&(b="latitude="+a[0]+" | longitude="+a[1]);navigator.geolocation&& navigator.geolocation.getCurrentPosition(f,g,e);""===b&&(b="geo coordinates not available");return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getGeoCoordinates` método não usa nenhum argumento. Retorna um dos seguintes valores:

* `"geo coordinates not available"`: Para dispositivos que não têm dados de localização geográfica disponíveis no momento em que o plug-in é executado. Esse valor é comum na primeira ocorrência da visita, especialmente quando os visitantes precisam primeiro fornecer consentimento sobre o rastreamento de sua localização.
* `"error retrieving geo coordinates"`: Quando o plug-in encontra erros ao tentar recuperar o local do dispositivo
* `"latitude=[LATITUDE] | longtitude=[LONGITUDE]"`: Onde [LATITUDE]/[LONGITUDE] são a latitude e a longitude, respectivamente

> [!NOTE] Os valores de coordenadas são arredondados para a quarta decimal mais próxima. Por exemplo, o valor de `"40.438635333"` é arredondado para `"40.4386"` limitar o número de valores únicos a serem capturados. Os valores estão próximos o suficiente para apontar o local exato do dispositivo em cerca de 3 metros.

Esse plug-in usa um cookie chamado `"s_ggc"` para armazenar coordenadas entre ocorrências, se necessário.

## Exemplos de chamadas

### Exemplo nº 1

O seguinte código...

```js
s.eVar1 = s.getGeoCoordinates();
```

...define eVar1 igual a um dos valores de retorno acima, dependendo do status do dispositivo do visitante

### Exemplo nº 2

O código a seguir extrai latitude e longitude em suas próprias variáveis chamadas finalLatitude e finalLongitude para uso em outros códigos/aplicativos

```js
var coordinates = s.getGeoCoordinates();
if(coordinates.indexOf("latitude") > -1)
{
  var finalLatitude = Number(coordinates.split("|")[0].trim().split("=")[1]),
  finalLongitude = Number(coordinates.split("|")[1].trim().split("=")[1]);
}
```

Daí, você pode determinar se um visitante está, por exemplo, na Estátua da Liberdade:

```js
if(finalLatitude >= 40.6891 && finalLatitude <= 40.6893 && finalLongtude >= -74.0446 && finalLongitude <= -74.0444)
  var visitorAtStatueOfLiberty = true;
else
  var visitorAtStatueOfLiberty = false;
```

## Histórico da versão

### 1.0 (25 de maio de 2015)

* Versão inicial.
