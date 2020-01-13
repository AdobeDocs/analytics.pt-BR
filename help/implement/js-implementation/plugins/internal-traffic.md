---
title: Tráfego interno
description: O plug-in de Tráfego interno identifica dinamicamente os visitantes provenientes de uma rede interna.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tráfego interno

O plug-in de Tráfego interno identifica dinamicamente os visitantes provenientes de uma rede interna.

A identificação do tráfego interno e externo promove maior precisão em todos os tipos de relatórios, fornecendo um mecanismo que filtra e segmenta os dados que estão sendo coletados. Implementado corretamente, isso também eliminaria a necessidade de uma regra VISTA ou Regra de processamento que são abordagens típicas para identificar esse tráfego.

## Como o plug-in de Tráfego interno funciona?

O plug-in tenta carregar um arquivo que só estaria disponível na rede interna/intranet, ou seja, um pixel transparente de 1x1. Se for carregado com êxito, o tráfego desse visitante será identificado como interno. Qualquer outra coisa seria o tráfego externo.

## Considerações

* A única desvantagem dessa abordagem é que um erro 404 é exibido no console do navegador para visitantes externos na primeira página da visita. Isso não afetará a experiência do usuário.
* Sugerimos que você obtenha aprovação da sua equipe de Rede ou InfoSec, antes de tentar carregar um pixel hospedado internamente.
* Embora o plug-in não mova o tráfego para outro conjunto de relatórios ou o exclua do relatório (como pode ser feito com uma regra VISTA), a lógica personalizada pode ser incluída na implementação, para que essa funcionalidade possa ocorrer no lado do cliente.

## Implementação

1. Adicionar o pixel da intranet: você pode adicionar qualquer tipo de arquivo na intranet que o plug-in tentaria acessar. Recomenda-se um pixel transparente 1x1. Ele deve ser colocado em um local na intranet que seja amplamente acessível na rede interna.
1. Configurar uma eVar: é necessário adicionar uma eVar ao conjunto de relatórios de destino. Ela deve ter uma expiração de "Visita" e alocação do "Valor original (primeiro)".
1. Definir o URL interno: nas variáveis de configuração do AppMeasurement e antes da instanciação de doPlugins, defina a variável de URL interna (s.intURL) para o pixel ou outro arquivo que possa ser usado para a verificação de tráfego. Por exemplo: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modificar doPlugins e definir a eVar: o plug-in pode ser inicializado ao incluir essa linha de código na seção doPlugins do código da biblioteca do AppMeasurement, usando a eVar definida na etapa um: `s.eVarXX = s.intCheck();`
o valor da variável será definido como "interno" ou "externo".
1. Adicionar o código fonte do plug-in: inclua o código do plug-in abaixo da seção doPlugins do arquivo AppMeasurement.

## Código fonte do plug-in

Adicione esse código abaixo da seção doPlugins da biblioteca do AppMeasurement.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Outras observações

* Sempre teste as instalações de plug-ins para garantir que a coleta de dados ocorra como esperado, antes de implantar em um ambiente de produção.
* A implementação pode usar um nome de objeto diferente do objeto "s" padrão do Adobe Analytics. Em caso afirmativo, atualize o nome do objeto de acordo.
* Se você usar um sistema de Tag Management, siga as etapas para atualizar doPlugins e outros plug-ins personalizados.
