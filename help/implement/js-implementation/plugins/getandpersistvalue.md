---
description: O plug-in getAndPersistValue obtém um valor de sua escolha e o preenche em uma variável do Analytics por determinado período. Um uso comum é ver a quantidade de exibições de página geradas depois de um click-through, que permite a exibição fácil das páginas mais comuns de cada campanha.
keywords: Implementação do Analytics
seo-description: O plug-in getAndPersistValue obtém um valor de sua escolha e o preenche em uma variável do Analytics por determinado período. Um uso comum é ver a quantidade de exibições de página geradas depois de um click-through, que permite a exibição fácil das páginas mais comuns de cada campanha.
seo-title: getAndPersistValue
solution: Analytics
subtopic: Plug-ins
title: getAndPersistValue
topic: Desenvolvedor e implementação
uuid: ddeab 80 c -260 e -44 b 6-8b 83-8 b 8 b 369 ec 19 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getAndPersistValue

O plug-in getAndPersistValue obtém um valor de sua escolha e o preenche em uma variável do Analytics por determinado período. Um uso comum é ver a quantidade de exibições de página geradas depois de um click-through, que permite a exibição fácil das páginas mais comuns de cada campanha.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. Esse exemplo permite determinar a quantidade de exibições de página o código de rastreamento gerou como resultado do click-through original.

>[!NOTE]
>
>As instruções a seguir exigem que você altere o código de coleta de dados do site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIGURAR SEÇÃO**: nenhuma alteração necessária para esta seção.

**Configuração do plug-in**

Coloque o seguinte código na função *`s_doPlugins()`* , que está localizada na área do *`s_code.js`* arquivo chamada Configuração *de plug-in*. Escolha uma variável de Tráfego personalizado (s.prop) ou uma variável de Conversão personalizada (s.eVar) para uso na captura de dados de valor persistidos. Essa deve ser uma variável que foi ativada usando o Admin Console, mas que não está em uso no momento para qualquer outra finalidade. É possível usar o seguinte exemplo e atualizá-lo com base em seus requisitos.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* tem três argumentos:

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
1. Período de persistência, em dias. "30" como mostrado acima resultaria no preenchimento do valor em uma variável selecionada em cada exibição de página pelo usuário nos próximos 30 dias. Se for omitido, o padrão da configuração será *sessão*.

**SEÇÃO DE PLUG-INS**: adicione o seguinte código à área do arquivo [!DNL s_code.js] rotulada como SEÇÃO DE PLUG-INS. Não faça alterações nessa parte do código do plug-in.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Sempre teste a instalação do plug-in para verificar se a coleta de dados ocorre como esperado antes da implantação no ambiente de produção.
