---
title: getPreviousValue
description: Obtenha o último valor passado para uma variável.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Plug-in da Adobe: getPreviousValue

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getPreviousValue` plug-in permite que você defina uma variável como um valor definido em uma ocorrência anterior. Esse plug-in não é necessário se sua implementação contiver todos os valores desejados na ocorrência atual.

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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getPreviousValue` método usa os seguintes argumentos:

* **`v`**(string, obrigatório): A variável que tem o valor que você deseja passar para a próxima solicitação de imagem. Uma variável comum usada é recuperar`s.pageName`o valor da página anterior.
* **`c`**(string, opcional): O nome do cookie que armazena o valor.  Se esse argumento não estiver definido, ele assumirá`"s_gpv"`como padrão.

Quando você chama esse método, ele retorna o valor da string contido no cookie. Em seguida, o plug-in redefine a expiração do cookie e atribui o valor da variável do `v` argumento. O cookie expira após 30 minutos de inatividade.

## Exemplos de chamadas

### Exemplo nº 1

O seguinte código...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Primeiro define s.prop7 igual ao valor passado para s.pageName na solicitação de imagem anterior (ou seja, o valor armazenado no cookie &quot;gpv_Page&quot;)
* O código redefinirá o cookie &quot;gpv_Page&quot;, tornando-o igual ao valor atual de s.pageName
* Se s.pageName não estiver definido no momento em que esse código é executado, o código redefinirá a expiração do valor atual do cookie

### Exemplo nº 2

O código a seguir define s.prop7 igual ao último valor passado para s.pageName, mas somente se event1 também estiver contido em s.events, conforme determinado pelo plug-in in inList, no momento em que a chamada ocorre.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemplo 3

O código a seguir define s.prop7 igual ao último valor passado para s.pageName, mas somente se s.pageName estiver definido na página ao mesmo tempo.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Exemplo nº 4

O código a seguir define s.eVar10 igual ao valor passado para s.eVar1 na solicitação de imagem anterior.   O valor anterior da eVar1 estaria contido no cookie &quot;s_gpv&quot;.  O código definirá o cookie &quot;s_gpv&quot; igual ao valor atual de s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Improvável Quirks

Se a variável associada ao argumento v estiver definida como um novo valor e o plug-in getPreviousValue for executado MAS uma chamada de servidor do Analytics NÃO for enviada ao mesmo tempo, o novo valor do argumento v ainda será considerado o &quot;valor anterior&quot; na próxima vez que o plug-in for executado.
Por exemplo, suponha que o código a seguir seja executado na primeira página da visita:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Esse código produziria uma chamada de servidor onde o argumento pageName é igual a &quot;home&quot; e o argumento p7 (prop7) não está definido.  No entanto, a chamada para s.getPreviousValue armazenaria o valor de s.pageName (ou seja, &quot;home&quot;) no cookie especificado na chamada (ou seja, o cookie &quot;gpv_Page&quot;).
Agora, suponha que imediatamente depois, na mesma página, o seguinte código seja executado (por qualquer motivo):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Como a função s.t() não é executada neste bloco de código, outra solicitação de imagem não será criada.  No entanto, quando o código da função s.getPreviousValue() for executado desta vez, s.prop7 será definido como igual ao valor anterior de s.pageName (ou seja, &quot;home&quot;) e armazenará o novo valor de s.pageName (ou seja, &quot;valor feliz&quot;) no cookie &quot;gpv_Page&quot;.
Suponha que o visitante navegue para uma página diferente e o seguinte código seja executado nesta página:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Quando a função de chamada s.t() é executada, ela criará uma solicitação de imagem onde s.pageName=&quot;page 2&quot; e s.prop7 é igual a &quot;Happy value&quot;, que era o valor de s.pageName quando a última chamada para getPreviousValue ocorreu.   O valor s.prop7 de &quot;home&quot; nunca foi contido em nenhuma solicitação de imagem real, embora &quot;home&quot; tenha sido o primeiro valor passado para s.pageName.

## Histórico da versão

### v2.0 (7 de outubro de 2019)

* Versão pontual (regravação lógica completa).
