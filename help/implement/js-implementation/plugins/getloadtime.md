---
description: Obtém o tempo de carregamento da página em décimos de segundos e permite o armazenamento do valor em prop, eVar, e/ou outro evento numérico.
keywords: Implementação do Analytics
seo-description: Obtém o tempo de carregamento da página em décimos de segundos e permite o armazenamento do valor em prop, eVar, e/ou outro evento numérico.
seo-title: getLoadTime
solution: Analytics
title: getLoadTime
topic: Desenvolvedor e implementação
uuid: 5 d 26 a 69 b-cbde -4 be 1-bac 1-5 ee 8 a 4 e 55 ca 3
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getLoadTime

Obtém o tempo de carregamento da página em décimos de segundos e permite o armazenamento do valor em prop, eVar, e/ou outro evento numérico.

Para usar este plugin, você insere o código da função, em seguida, chama a função duas vezes no arquivo [!DNL s_code.js]. Uma vez no início do arquivo e novamente na seção `doPlugins`. Este plugin não é definido intencionalmente como um método do objeto s. Isso apenas aumentaria o tempo de carga de página calculado.

>[!NOTE]
>
>As instruções a seguir exigem que você altere o código de coleta de dados do site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_968AC379C3004C359A85AFED5A48D5AE}

**Adicionar a função**

Adicione a seguinte definição da função `s_getLoadTime` em [!DNL s_code.js], em qualquer ponto antes da seção "NÃO ALTERE QUALQUER ITEM ABAIXO DESTA LINHA":

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Efetuar a chamada de função inicial**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**Efetuar a chamada de função final**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

Exemplo de utilização 1 - Salve o tempo de carregamento de página em prop10 e eVar20:

```js
s.eVar20=s.prop10=s_getLoadTime();
```

Exemplo de utilização 2 - Salve o tempo de carregamento de página no valor numérico event99:

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(Opcional) Adicionar suporte a navegadores antigos**

Para suportar navegadores antigos que não oferecem a propriedade [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/), inclua a seguinte linha na seção CABEÇALHO do HTML da página próximo ao início e antes de invocar .js, .css ou outros arquivos:

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

