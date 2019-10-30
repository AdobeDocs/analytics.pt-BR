---
description: O plug-in apl (ou appendList) permite anexar um valor a qualquer lista delimitada, com a opção de verificação de maiúsculas e minúsculas para garantir que o valor não exista na lista. O plug-in APL é mencionado por vários plug-ins padrão, mas pode ser usado diretamente em várias situações.
keywords: Implementação do Analytics
seo-description: O plug-in apl (ou appendList) permite anexar um valor a qualquer lista delimitada, com a opção de verificação de maiúsculas e minúsculas para garantir que o valor não exista na lista. O plug-in APL é mencionado por vários plug-ins padrão, mas pode ser usado diretamente em várias situações.
seo-title: appendList
solution: Analytics
subtopic: Plug-ins
title: appendList
topic: Desenvolvedor e implementação
uuid: e923c86c-eaa6-4e17-a3a4-0e08af886674
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# appendList

O plug-in apl (ou appendList) permite anexar um valor a qualquer lista delimitada, com a opção de verificação de maiúsculas e minúsculas para garantir que o valor não exista na lista. O plug-in APL é mencionado por vários plug-ins padrão, mas pode ser usado diretamente em várias situações.

Esse plug-in é útil para:

* Adicionar um evento à variável de eventos atual
* Adicionar um valor a uma variável de lista sem duplicar um valor na lista
* Adicionar um produto à variável products atual com base na lógica da página
* Adicionar valores aos parâmetros *`linkTrackVars`* e *`linkTrackEvents`*

**Caso de uso 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cenário </p> </td> 
   <td colname="col2"> <p>Adicionar <span class="term"> event1 </span> à variável de eventos atual, garantindo que o evento não seja duplicado. </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resultados </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Caso de uso 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cenário </p> </td> 
   <td colname="col2"> <p>Adicione o valor O <span class="term"> histórico </span> para a variável de lista <span class="varname"> prop1 </span>, onde o <span class="term"> histórico </span> e <span class="term"> Histórico </span> são considerados o mesmo valor. </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resultados </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> O <span class="term"> histórico </span> não é adicionado porque o <span class="term"> Histórico </span> já está na lista. </p> </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Implementação {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

Siga estas etapas para implementar o plug-in APL.

1. Solicite o código do plug-in no Atendimento ao cliente ou com o consultor da Adobe atribuído.
1. Adicione chamadas à função API, conforme a necessidade, na função *`s_doPlugins`*

O código deverá ter esta aparência no site:

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**Navegadores suportados**

O plug-in exige que o navegador dê suporte ao JavaScript versão 1.0.

**Informações de plug-in**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Informações de plug-in </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Parâmetros </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L= lista de origem, lista vazia é aceita </p> <p> v = valor para anexar </p> <p> d = delimitador de lista </p> <p> u (opcional, o padrão é 0) Verificação de valor exclusiva. 0=sem verificação exclusiva, o valor é sempre anexado. 1=verificação que não diferencia maiúsculas de minúsculas, anexa somente se o valor não está na lista. 2=verificação que diferencia maiúsculas de minúsculas, anexa somente se o valor não está na lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valor de retorno </p> </td> 
   <td colname="col2"> <p>lista original, com valor anexado se for adicionado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemplos de uso </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

A lista de origem L pode ser uma lista vazia, como *`L=""`*. O valor retornado será uma lista vazia ou uma lista com um valor.

**Código do plug-in**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split
```

