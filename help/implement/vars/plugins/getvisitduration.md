---
title: getVisitDuration
description: Rastrear quanto tempo um visitante esteve no site até agora.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Plug-in da Adobe:getVisitDuration

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudar a obter mais valor com o uso do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `getVisitDuration` in rastreia a quantidade de tempo em minutos que o visitante esteve no site até esse ponto. A Adobe recomenda usar esse plug-in se você deseja rastrear o tempo cumulativo do site até esse ponto ou rastrear o tempo necessário para executar uma atividade. Este plug-in não rastreia o tempo entre eventos; se essa funcionalidade for desejada, use o `getTimeBetweenEvents` plug-in.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Para qualquer Regra de inicialização em que você deseja usar o plug-in, adicione uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar addProductEvar
1. Salvar e publicar as alterações na regra

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código] personalizado, que revela o botão [!UICONTROL Abrir editor] .
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando `s_gi`). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getVisitDuration` método não usa nenhum argumento. Retorna um dos seguintes valores:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (onde `[x]` é o número de minutos passados desde que o visitante chegou ao site)

Este plug-in cria um cookie primário chamado `"s_dur"`, que é o número de milissegundos decorridos desde que o visitante chegou ao site. O cookie expira após 30 minutos de inatividade.

## Exemplos de chamadas

### Exemplo nº 1

O seguinte código...

```js
s.eVar10 = s.getVisitDuration();
```

...sempre definirá a eVar10 igual ao número de minutos passados desde que o visitante chegou ao site

### Exemplo nº 2

O seguinte código...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...usa o plug-in in inList para verificar se a variável events contém o evento purchase.  Em caso positivo, a eVar10 será definida como o número de minutos entre o início da visita do visitante e o momento da compra.

### Exemplo 3

O seguinte código...

```js
s.prop10 = s.getVisitDuration();
```

...sempre definirá prop10 igual ao número de minutos passados desde que o visitante chegou ao site.  Isso será útil se prop10 tiver definição de caminho ativada.  Adicionar a métrica &quot;saídas&quot; ao relatório prop10 mostrará um relatório granular e de &quot;dispersão&quot; do tempo que uma visita levou em minutos antes de um visitante sair do site.

## Histórico da versão

### 2.0 (2 de maio de 2018)

* Lançamento pontual (reanálise/regravação completa do plug-in).
