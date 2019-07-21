---
title: Tráfego interno
description: O plug-plugin de Tráfego interno identifica dinamicamente os visitantes provenientes de uma rede interna.
seo-description: Plug-plugin de tráfego interno
seo-title: Plug-plugin de tráfego interno
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Tráfego interno

O plug-plugin de Tráfego interno identifica dinamicamente os visitantes provenientes de uma rede interna.

Identificar o tráfego interno e externo promove maior precisão em todos os tipos de relatórios, fornecendo um mecanismo que filtra e segmenta os dados de segmentos. Implementado corretamente, também elimina a necessidade de uma regra VISTA ou de uma Regra de processamento que são abordagens típicas para identificar tal tráfego.

## Como funciona o plug-plugin de Tráfego interno?

O plug-in tenta carregar um arquivo que só estaria disponível em sua rede interna/intranet, ou seja, um pixel transparente de 1 x 1. Se ele for carregado com sucesso, o tráfego daquele visitante será identificado como interno. Qualquer outro item seria tráfego externo.

## Considerações

* O único lado negativo para essa abordagem é que um erro 404 é exibido no console do navegador para visitantes externos na primeira página de sua visita. Isso não afetará a experiência do usuário.
* Recomendamos que você obtenha aprovação da sua equipe de rede ou infosec antes de tentar carregar um pixel hospedado internamente.
* Embora o plug-plugin não mova tráfego para outro conjunto de relatórios ou o exclua do relatório (como pode ser feito com uma regra VISTA), a lógica personalizada pode ser incluída com sua implementação, para que essa funcionalidade possa ocorrer no cliente.

## Implementação

1. Adicionar seu Pixel de intranet: Você pode adicionar qualquer tipo de arquivo na intranet que o plug-in tentaria acessar. Recomenda-se um pixel transparente de 1 x 1. Ela deve ser colocada em um local na intranet amplamente acessível em suas redes internas.
1. Configurar uma evar: Uma evar precisará ser adicionada dentro do conjunto de relatórios de destino. Deve ter uma expiração de «Visita» e alocação de «Valor original (primeiro)».
1. Defina o URL interno: Nas variáveis de configuração do appmeasurement e antes de doplugins ser instanciado, defina a variável interna de URL (s. inturl) para o pixel ou outro arquivo para a verificação de tráfego. Por exemplo: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to “internal” or “external”.
1. Adicione o Código Fonte do plug-in: Inclua o código de plug-plugin abaixo da seção doplugins do arquivo appmeasurement.

## Código fonte do plug-in

Adicione este código abaixo da seção doplugins da biblioteca do appmeasurement.

```s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");```

## Other Notes

* Always test plug-in installations to ensure that data collection happens as expected before deploying them in a production environment.
* Your implementation might be using a different object name than the default Adobe Analytics "s" object. If so, please update the object name accordingly.
* If you employ a Tag Management System, please follow its steps to update doPlugins and the other custom plugins.

