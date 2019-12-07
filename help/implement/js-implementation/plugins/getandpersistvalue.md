---
description: O plug-in getAndPersistValue obtém um valor de sua escolha e o preenche em uma variável do Analytics por determinado período. Um uso comum é ver a quantidade de exibições de página geradas depois de um click-through, que permite a exibição fácil das páginas mais comuns de cada campanha.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getAndPersistValue

O plug-in getAndPersistValue obtém um valor de sua escolha e o preenche em uma variável do Analytics por determinado período. Um uso comum é ver a quantidade de exibições de página geradas depois de um click-through, que permite a exibição fácil das páginas mais comuns de cada campanha.

>[!IMPORTANT]
>
>Este plug-in não foi validado para ser compatível com o [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). [Suporte a Plug-in do AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

Por exemplo, você pode usar esse plug-in para definir um código de rastreamento de campanha da variável *`campaign`* em uma variável de Tráfego personalizado (*`s.prop`*) na exibição de página de cada visitante nos próximos 30 dias. Esse exemplo permite determinar a quantidade de exibições de página o código de rastreamento gerou como resultado do click-through original.

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIGURAR SEÇÃO**: nenhuma alteração necessária para esta seção.

**Configuração do plug-in**

Coloque o seguinte código na função *`s_doPlugins()`*, que está localizada na área do arquivo *`s_code.js`chamada de* Configuração de plug-in *.* Escolha uma variável de Tráfego personalizado (s.prop) ou uma variável de Conversão personalizada (s.eVar) para uso na captura de dados de valor persistidos. Essa deve ser uma variável que foi ativada usando o Admin Console, mas que não está em uso no momento para qualquer outra finalidade. É possível usar o seguinte exemplo e atualizá-lo com base em seus requisitos.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* tem três argumentos:

1. Variável ou valor preenchido no momento para persistir (*`s.campaign`* mostrado acima).
1. Nome do cookie, usado para armazenar o valor (*`s_getval`* mostrado acima).
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
