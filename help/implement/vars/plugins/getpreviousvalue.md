---
title: getPreviousValue
description: Obtenha o último valor transmitido a uma variável.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getPreviousValue

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getPreviousValue` permite que você defina uma variável como um valor definido em uma ocorrência anterior. Esse plug-in não é necessário se sua implementação já contiver todos os valores desejados na ocorrência atual.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getPreviousValue
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getPreviousValue` aceita os seguintes argumentos:

* **`v`** (string, obrigatório): a variável que tem o valor que você deseja transmitir para a próxima solicitação de imagem. Uma variável comumente usada para recuperar o valor da página anterior é `s.pageName`.
* **`c`** (string, opcional): o nome do cookie que armazena o valor.  Se esse argumento não estiver definido, ele assumirá `"s_gpv"` como padrão.

Quando você chama esse método, ele retorna o valor em string contido no cookie. Em seguida, o plug-in redefine a validade do cookie e atribui a ele o valor de variável no argumento `v`. O cookie expira após 30 minutos de inatividade.

## Exemplos de chamadas

### Exemplo #1

O código a seguir...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Primeiro define s.prop7 como o valor transmitido para s.pageName na solicitação de imagem anterior (ou seja, o valor armazenado no cookie &quot;gpv_Page&quot;)
* O código redefinirá o cookie &quot;gpv_Page&quot;, tornando-o igual ao valor atual de s.pageName
* Se s.pageName não estiver definido no momento em que esse código for executado, o código redefinirá a expiração do valor atual do cookie

### Exemplo #2

O código a seguir define s.prop7 como o último valor transmitido para s.pageName, mas somente se event1 também estiver contido em s.events, conforme determinado pelo plug-in inList no momento em que a chamada ocorre.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemplo #3

O código a seguir define s.prop7 como o último valor transmitido para s.pageName, mas somente se s.pageName estiver definido na página ao mesmo tempo.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemplo #4

O código a seguir define s.eVar10 como o valor transmitido para s.eVar1 na solicitação de imagem anterior.   O valor anterior da eVar1 estaria contido no cookie &quot;s_gpv&quot;.  O código definirá o cookie &quot;s_gpv&quot; com o valor atual de s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Peculiaridades improváveis

Se a variável associada ao argumento v estiver definida com um novo valor e o plug-in getPreviousValue for executado, MAS uma chamada de servidor do Analytics NÃO for enviada ao mesmo tempo, o novo valor do argumento v ainda será considerado o &quot;valor anterior&quot; na próxima vez que o plug-in for executado.
Por exemplo, suponha que o código a seguir seja executado na primeira página da visita:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Esse código produziria uma chamada de servidor onde o argumento pageName é igual a &quot;inicial&quot; e o argumento p7 (prop7) não está definido.  No entanto, a chamada para s.getPreviousValue armazenaria o valor de s.pageName (ou seja, &quot;inicial&quot;) no cookie especificado na chamada (ou seja, o cookie &quot;gpv_Page&quot;).
Agora, suponha que, imediatamente depois, na mesma página, o seguinte código seja executado (por qualquer motivo):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Como a função s.t() não é executada neste bloco de código, outra solicitação de imagem não será criada.  No entanto, desta vez, quando o código da função s.getPreviousValue() for executado, s.prop7 será definido como igual ao valor anterior de s.pageName (ou seja, &quot;inicial&quot;) e armazenará o novo valor de s.pageName (ou seja, &quot;valor feliz&quot;) no cookie &quot;gpv_Page&quot;.
Suponha que o visitante navegue para uma página diferente e o seguinte código seja executado na página:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Quando a função de chamada s.t() é executada, ela cria uma solicitação de imagem onde s.pageName = &quot;page 2&quot; e s.prop7 é igual a &quot;valor feliz&quot;, que era o valor de s.pageName quando a última chamada para getPreviousValue ocorreu.   O valor &quot;inicial&quot; de s.prop7 nunca esteve contido em uma solicitação de imagem real, embora &quot;inicial&quot; tenha sido o primeiro valor passado para s.pageName.

## Histórico da versão

### v2.0 (7 de outubro de 2019)

* Versão pontual (reescrita completa da lógica).
