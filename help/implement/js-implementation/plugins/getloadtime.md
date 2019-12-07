---
description: Obtém o tempo de carregamento da página em décimos de segundos e permite o armazenamento do valor em prop, eVar, e/ou outro evento numérico.
keywords: Analytics Implementation
title: getLoadTime
topic: Developer and implementation
uuid: 5d26a69b-cbde-4be1-bac1-5ee8a4e55ca3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getLoadTime

Obtém o tempo de carregamento da página em décimos de segundos e permite o armazenamento do valor em prop, eVar, e/ou outro evento numérico.

Para usar este plugin, você insere o código da função, em seguida, chama a função duas vezes no arquivo [!DNL s_code.js]. Uma vez no início do arquivo e novamente na seção `doPlugins`. Este plugin não é definido intencionalmente como um método do objeto s. Isso apenas aumentaria o tempo de carga de página calculado.

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_968AC379C3004C359A85AFED5A48D5AE}

**Adicionar a função**

Adicione a seguinte definição da função `s_getLoadTime` em [!DNL s_code.js], em qualquer ponto antes da seção "NÃO ALTERE QUALQUER ITEM ABAIXO DESTA LINHA":

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Efetuar a chamada de função inicial**

Adicione uma chamada a `s_getLoadTime()` próximo do início de [!DNL s_code.js], fora de qualquer função.

**Efetuar a chamada de função final**

Adicione outra chamada a `s_getLoadTime()` na função `s_doPlugins()`, salvando o valor retornado em uma prop, eVar e/ou um evento numérico.

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

