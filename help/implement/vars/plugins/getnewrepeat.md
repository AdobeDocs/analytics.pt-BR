---
title: getNewRepeat
description: Acompanhar a atividade de visitantes novos e repetidos.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe: getNewRepeat

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getNewRepeat` plug-in permite determinar se um visitante do site é um novo visitante ou um visitante repetido dentro de um número desejado de dias. A Adobe recomenda usar esse plug-in se você quiser identificar os visitantes como &quot;novos&quot; usando um número personalizado de dias. Esse plug-in é desnecessário se as dimensões Novo/Repetir do visitante na Analysis Workspace atenderem às necessidades da sua organização.

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
   * Tipo de ação: Inicializar getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getNewRepeat` método usa os seguintes argumentos:

* **`d`**(número inteiro, opcional): O número mínimo de dias necessários entre visitas que redefine os visitantes para`"New"`. Se esse argumento não for definido, o padrão será 30 dias.

Este método retorna o valor de `"New"` se o cookie definido pelo plug-in não existir ou tiver expirado. Ele retorna o valor de `"Repeat"` se o cookie definido pelo plug-in existe e o tempo desde a ocorrência atual e o tempo definido no cookie é maior que 30 minutos. Este método retorna o mesmo valor para uma visita inteira.

Este plug-in usa um cookie chamado `"s_nr[LENGTH]"` onde `[LENGTH]` é igual ao `d` argumento. O cookie contém um carimbo de data e hora Unix que representa a hora atual e o status atual do visitante (`"New"` ou `"Repeat"`).

## Exemplos de chamadas

### Exemplo #1

O código a seguir definirá s.eVar1 igual ao valor de &quot;Novo&quot; para novos visitantes e continuará a definir s.eVar1 igual ao valor de &quot;Novo&quot; (com cada nova chamada) durante o restante da visita do visitante ao site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemplo #2

Se o visitante voltar ao site a qualquer momento, de 31 minutos a 30 dias desde a última vez que s.getNewRepeat() foi chamado, o código a seguir definirá s.eVar1 igual ao valor de &quot;Repetir&quot; e continuará a definir s.eVar1 igual ao valor de &quot;Repetir&quot; (com cada nova chamada) durante o restante da visita do visitante ao site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemplo 3

Se o visitante não tiver estado no site há pelo menos 30 dias desde a última vez que s.getNewRepeat() foi chamado, o código a seguir definirá s.eVar1 igual ao valor de &quot;New&quot; e continuará a definir s.eVar1 igual ao valor de &quot;New&quot; (com cada nova chamada) durante o restante da visita do visitante ao site.

```js
s.eVar1=s.getNewRepeat();
```

### Exemplo #4

Se o visitante retornar ao site a qualquer momento, 31 minutos a 365 dias (ou seja, 1 ano) desde a última vez que s.getNewRepeat() foi chamado, o código a seguir definirá s.eVar1 igual ao valor de &quot;Repetir&quot; e continuará definindo s.eVar1 igual ao valor de &quot;Repetir&quot; (com cada nova chamada) durante o restante do visita do visitante ao site.

```js
s.eVar1=s.getNewRepeat(365);
```

### Exemplo #5

Se o visitante não tiver estado no site há pelo menos 365 dias (ou seja, 1 ano) desde a última vez que s.getNewRepeat() foi chamado, o código a seguir definirá s.eVar1 igual ao valor de &quot;Novo&quot; e continuará a definir s.eVar1 igual ao valor de &quot;Novo&quot; (com cada nova chamada) durante o restante do visitante visita ao site.

```js
s.eVar1=s.getNewRepeat(365);
```

## Histórico da versão

### 2.1 (30 de setembro de 2019)

* Reorganização da lógica do JavaScript para reduzir o tamanho do plug-in

### 2.0 (16 de abril de 2018)

* Recompilado com tamanho de código menor
* Removida a capacidade de nomear o cookie para armazenar as informações de visita. O plug-in agora nomeia dinamicamente o cookie com base no valor passado para o `d` argumento.
