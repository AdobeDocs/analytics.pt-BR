---
description: Determina se um visitante é um novo visitante ou um visitante repetido, além de capturar essas informações em uma variável do Analytics.
keywords: Implementação do Analytics
seo-description: Determina se um visitante é um novo visitante ou um visitante repetido, além de capturar essas informações em uma variável do Analytics.
seo-title: getNewRepeat
solution: Analytics
subtopic: Plug-ins
title: getNewRepeat
topic: Desenvolvedor e implementação
uuid: e 3 e 9 f 362-e 0 b 1-4 a 2 b-bb 5 b -98 eddaa 0 a 7 f 4
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getNewRepeat

Determina se um visitante é um novo visitante ou um visitante repetido, além de capturar essas informações em uma variável do Analytics.

Use esse plug-in para responder às seguintes dúvidas:

* Qual porcentagem dos meus visitantes é de novos visitantes (diferente dos repetidos)?
* Os visitantes de retorno geram uma conversão maior per capita do que os novos visitantes? Qual é essa proporção?
* As minhas campanhas de marketing geram persistência em visitas? Por exemplo, os usuário que clicam em minhas campanhas retorna depois?

>[!NOTE]
>
>As instruções a seguir exigem que você altere o código de coleta de dados do site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIGURAR SEÇÃO**: nenhuma alteração necessária para esta seção.

**Configuração do plug-in**

Coloque o seguinte código na função *`s_doPlugins()`* , que está localizada na área do *`s_code.js`* arquivo chamada Configuração *de plug-in*. Escolha uma variável de Tráfego personalizado (s.prop) ou uma variável de Conversão personalizada (s.eVar) para uso na captura de dados de valor persistidos. Essa deve ser uma variável que foi ativada usando o Admin Console, mas que não está em uso no momento para qualquer outra finalidade. É possível usar o seguinte exemplo e atualizá-lo com base em seus requisitos.

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* tem dois argumentos opcionais:

1. O primeiro argumento opcional é o número de dias que um cookie deve durar. O valor padrão se esse argumento for omitido é de 30 dias.
1. O segundo argumento opcional é o nome do cookie. O valor padrão é usado se esse argumento for omitido.

**SEÇÃO DE PLUG-INS**: adicione o seguinte código à área do arquivo [!DNL s_code.js] rotulada como SEÇÃO DE PLUG-INS. Não faça alterações nessa parte do código do plug-in.

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

Sempre teste a instalação do plug-in para verificar se a coleta de dados ocorre como esperado antes da implantação no ambiente de produção.
