---
title: getResponsiveLayout
description: Determine qual layout de um site está sendo exibido no momento.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe:getResponsiveLayout

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getResponsiveLayout` plug-in permite que você rastreie a versão do site responsivo baseado em design que um visitante está visualizando no momento. A Adobe recomenda usar esse plug-in se o seu site usar um design responsivo e você quiser rastrear a versão do site exibida por um visitante. Esse plug-in é desnecessário se o site não usar o design responsivo.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar getResponsiveLayout
1. Salve e publique as alterações na regra.

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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getResponsiveLayout` método usa os seguintes argumentos:

* **`ppw`**(obrigatório, número inteiro): A largura máxima de pixels que uma janela do navegador pode ter antes que a página alterne de um layout de retrato de telefone para um layout com base no modo paisagem de telefone
* **`plw`**(obrigatório, número inteiro): A largura máxima de pixels que uma janela do navegador pode ter antes que a página alterne de um layout paisagem para um layout baseado em tablet
* **`tw`**(obrigatório, booleano): A largura máxima de pixels que uma janela do navegador pode ter antes que a página alterne de um layout de tablet para um layout baseado em desktop

Chamar esse método retorna uma string contendo duas partes. A primeira parte usa um dos seguintes valores, dependendo da largura do navegador e dos argumentos acima:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (para sites que não têm layouts retrato e paisagem)
* `"tablet layout"`
* `"desktop layout"`

A segunda parte da string retornada é a largura e a altura do navegador. Por exemplo, `"desktop layout:1243x700"`.

## Exemplos de chamadas

### Exemplo nº 1

Se o status...

* Seu site muda do modo retrato do telefone para o modo paisagem do telefone quando a largura do navegador é superior a 500 pixels
* Seu site muda do modo paisagem telefônica para o modo tablet quando a largura do navegador é superior a 700 pixels
* Seu site muda do modo tablet para o modo desktop quando a largura do navegador é maior que 1000 pixels

...o código a seguir definirá a eVar10 igual ao layout de design responsivo atual como experiência do visitante, bem como a largura e as dimensões do navegador

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Exemplo nº 2

Se o status...

* Seu site tem apenas um modo de telefone, um modo tablet e um modo desktop
* Seu site muda do modo de telefone para o modo tablet quando a largura do navegador é superior a 500 pixels
* Seu site muda do modo tablet para o modo desktop quando a largura do navegador é superior a 1.100 pixels

...o código a seguir definirá a eVar10 igual ao layout de design responsivo atual como experiência do visitante, bem como a largura e as dimensões do navegador

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Histórico da versão

### 1.0 (2 de maio de 2018)

* Versão inicial.
