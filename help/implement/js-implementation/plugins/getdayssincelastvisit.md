---
description: Determina o número de dias desde que um usuário visitou site pela última vez e captura essas informações em uma variável do Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getDaysSinceLastVisit
topic: Developer and implementation
uuid: cad95882-3bd0-4f94-a0c3-4e7b6058d246
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getDaysSinceLastVisit

Determina o número de dias desde que um usuário visitou site pela última vez e captura essas informações em uma variável do Analytics.

>[!IMPORTANT]
>
>[A Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) agora inclui uma dimensão de **[!UICONTROL Dias desde a última visita]** pronta para uso, anulando a necessidade deste plug-in.

Esses dados de frequência de retorno podem ser usados para responder às seguintes dúvidas:

* Qual é a frequência de retorno de visita em meu site?
* Como a frequência de retorno se relaciona à conversão? Os compradores repetidos visitam frequentemente ou infrequentemente?
* Os usuários que clicam em minhas campanhas retornam frequentemente?

O plug-in também pode gerar valores usados para segmentação. Por exemplo, é possível criar um segmento para exibir todos os dados para apenas essas visitas precedidas por 30 ou mais dias sem visitas do usuário.

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

## Código e implementação do plug-in {#section_5600DBB819F143D59527A73BD94418DE}

**SEÇÃO CONFIGURAÇÃO**

Não é necessário alterar.

**Configuração do plug-in**

Coloque o seguinte código na função `s_doPlugins()`, que está localizada na área do arquivo [!DNL s_code.js] chamada de *Configuração de plug-in*. Escolha uma variável de Tráfego personalizado (s.prop) e/ou uma variável de Conversão personalizada (s.eVar) para usar na captura dos dados de frequência de retorno. Essa seleção deve ser uma variável que foi ativada usando o Admin Console, mas que não está em uso no momento para qualquer outra finalidade. A seguir, é fornecido um exemplo, que deve ser atualizado apropriadamente com base em suas necessidades.

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**SEÇÃO DE PLUG-INS**
Adicione o seguinte código à área do arquivo [!DNL s_code.js] rotulada como *SEÇÃO DE PLUG-INS*. Não faça alterações nessa parte do código do plug-in.

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**Notas**

* Sempre teste a instalação do plug-in para verificar se a coleta de dados ocorre como esperado antes da implantação no ambiente de produção.
* O plug-in categoria os usuário por frequência de retorno nos seguintes grupos:

   * Primeira visita
   * Menos de 1 dia
   * Menos de 7 dias
   * Mais de 7 dias
   * Mais de 30 dias

* Esse plug-in depende dos cookies para marcar um usuário como já tendo visitado anteriormente. Se o navegador não aceita cookies, o plug-in retorna um valor *Cookies não suportados*.

