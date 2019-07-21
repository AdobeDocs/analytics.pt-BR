---
description: Captura o valor de uma variável do Analytics na próxima exibição de página. Por exemplo, é possível usar o plug-in para capturar o valor s.pageName da exibição de página anterior em uma variável de Tráfego personalizado. Também há a opção de capturar um valor anterior somente quando eventos bem-sucedidos atribuídos estão definidos.
keywords: Implementação do Analytics
seo-description: Captura o valor de uma variável do Analytics na próxima exibição de página. Por exemplo, é possível usar o plug-in para capturar o valor s.pageName da exibição de página anterior em uma variável de Tráfego personalizado. Também há a opção de capturar um valor anterior somente quando eventos bem-sucedidos atribuídos estão definidos.
seo-title: getPreviousValue
solution: Analytics
subtopic: Plug-ins
title: getPreviousValue
topic: Desenvolvedor e implementação
uuid: 20 da 7 b 4 a -9820-4690-a 1 cc-d 10 b 6 dd 627 a 7
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPreviousValue

Captura o valor de uma variável do Analytics na próxima exibição de página. Por exemplo, é possível usar o plug-in para capturar o valor s.pageName da exibição de página anterior em uma variável de Tráfego personalizado. Também há a opção de capturar um valor anterior somente quando eventos bem-sucedidos atribuídos estão definidos.

>[!NOTE]
>
>As instruções a seguir exigem que você altere o código de coleta de dados do site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIGURAR SEÇÃO**: nenhuma alteração necessária para esta seção.

**Configuração do plug-in**

Coloque o seguinte código na função *`s_doPlugins()`* , que está localizada na área do *`s_code.js`* arquivo chamada Configuração *de plug-in*. Escolha uma variável de Tráfego personalizado (s.prop) ou uma variável de Conversão personalizada (s.eVar) para uso na captura de dados de valor persistidos. Essa deve ser uma variável que foi ativada usando o Admin Console, mas que não está em uso no momento para qualquer outra finalidade. É possível usar o seguinte exemplo e atualizá-lo com base em seus requisitos.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* tem três argumentos:

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). Quando deixado em branco ou omitido, o plug-in captura o valor anterior em todas as exibições de página.

**SEÇÃO DE PLUG-INS**: adicione o seguinte código à área do arquivo [!DNL s_code.js] rotulada como SEÇÃO DE PLUG-INS. Não faça alterações nessa parte do código do plug-in.

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**Observações**

* Sempre teste a instalação do plug-in para verificar se a coleta de dados ocorre como esperado antes da implantação no ambiente de produção.
* Se nenhum valor estiver presente para a variável selecionada em qualquer página, o texto *sem valor* será definido no cookie.
* A expiração fixa de 30 minutos está definida para cada cookie e é atualizada com cada carregamento de página. O plug-in funcionar pela duração de uma visita.
* Como essa função deve ser chamada como parte da seção de plug-ins do código, este funciona cada vez *`s.t()`* ou *`s.tl()`* é chamada.

* A variável escolhida deve ser preenchida com um valor antes da chamada para *`s.getPreviousValue`*. Because the *`s_doPlugins()`* function is executed after the variables on the page are populated, this issue rarely occurs. It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.

