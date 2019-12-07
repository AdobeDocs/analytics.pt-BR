---
description: O plug-in getVisitNum determina o número de visitas que um usuário fez ao site e captura esse número em uma variável do Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getVisitNum
topic: Developer and implementation
uuid: 27d57f92-fffb-44d0-b9ca-9da93323f64c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getVisitNum

O plug-in getVisitNum determina o número de visitas que um usuário fez ao site e captura esse número em uma variável do Analytics.

## Código e implementação do plug-in {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIGURAR SEÇÃO**: nenhuma alteração necessária para esta seção.

**Configuração do plug-in**

Coloque o seguinte código na função *`s_doPlugins()`*, que está localizada na área do arquivo *`s_code.js`chamada de* Configuração de plug-in *.* Escolha uma variável de Tráfego personalizado (s.prop) ou uma variável de Conversão personalizada (s.eVar) para usar na captura dos dados do número de visitas. Essa deve ser uma variável que tenha sido ativada usando o Admin Console, mas que não está em uso no momento para qualquer outra finalidade. É possível usar o seguinte exemplo e atualizá-lo com base em seus requisitos.

`s.prop1=s.getVisitNum();`

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

**SEÇÃO DE PLUG-INS**: adicione o seguinte código à área do arquivo [!DNL s_code.js] rotulada como SEÇÃO DE PLUG-INS. Não faça alterações nessa parte do código do plug-in.

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**Parâmetros**

* tp = (sequência, opcional) Período de rastreamento. use "d" para dia, "w" para semana, "m" para mês ou um número específico para o número de dias.

   * Se dia, mês ou semana for selecionado, o número de visitantes será redefinido ao final do dia/mês/semana.
   * Se um número específico de dias for selecionado, então o número de visitantes será redefinido após esse número de dias.
   * Se nenhum valor for definido, então "m" será usado.

* c = (sequência, opcional) Especifique o nome do cookie persistente. O padrão é "s_vnum".
* c2 = (sequência, opcional) Especifique o nome do cookie de sessão. O padrão é "s_invisit".

**Devoluções**

* devolve o número de visita (1, 2, 3 etc) da visitação. O número será aumentado apenas na primeira página das visitas.
* devolve "número de visita desconhecido" caso o plug-in não consiga identificar o número de visita (os cookies estão bloqueados).

**Exemplos**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**Notas**

* Sempre teste a instalação do plug-in para verificar se a coleta de dados ocorre como esperado antes da implantação no ambiente de produção.
* Esse plug-in depende da capacidade de definir cookies no navegador da Web do usuário. Se o usuário não aceitar cookies, todas as visitas aparecerão como primeiras visitas.

