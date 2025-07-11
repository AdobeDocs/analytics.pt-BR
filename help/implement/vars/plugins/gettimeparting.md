---
title: getTimeParting
description: Meça o tempo em que uma ação específica ocorre.
feature: Appmeasurement Implementation
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 77%

---

# Plug-in da Adobe: getTimeParting

{{plug-in}}

O plug-in `getTimeParting` permite capturar os detalhes do tempo de execução de qualquer atividade mensurável que ocorre no site. Esse plug-in é importante quando você deseja detalhar métricas em qualquer divisão de tempo repetível, dentro de um intervalo de datas específico. Por exemplo, você pode comparar as taxas de conversão de dois dias diferentes da semana, como todos os domingos e todas as quintas-feiras. Você também pode comparar períodos do dia, como todas as manhãs e todas as noites.

O Analysis Workspace fornece dimensões semelhantes e predefinidas formatadas de forma ligeiramente diferente que nesse plug-in. Consulte [dimensões de separação de tempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) no Guia do usuário Analisar para obter mais informações. Algumas organizações consideram que as dimensões predefinidas do Analysis Workspace são suficientes.

>[!IMPORTANT]
>
>A versão 4.0+ desse plug-in é bem diferente das versões anteriores. A Adobe recomenda implementar esse plug-in &quot;do zero&quot;. O código que faz referência ao plug-in antes da versão 4.0 não é compatível com a versão atual desse plug-in.

## Instale o plug-in usando a extensão Web SDK

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Web SDK.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Marcas]** à esquerda e clique na propriedade de marca desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda e na guia **[!UICONTROL Catálogo]**
1. Localize e instale a extensão **[!UICONTROL Plug-ins Comuns do Web SDK]**.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda e, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: Plug-ins comuns do Web SDK
   * Elemento de Dados: `getTimeParting`
1. Defina o parâmetro `Time Zone` à direita.
1. Salve e publique as alterações no elemento de dados.

## Instale o plug-in de implementação manual do Web SDK

Este plug-in ainda não é compatível com uma implementação manual do Web SDK.

## Instale o plug-in usando a extensão Adobe Analytics.

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getTimeParting
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão de plug-in de plug-ins comuns do Analytics, poderá usar o editor de código personalizado.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getTimeParting` usa o seguinte argumento:

**`t`** (opcional, mas recomendado, string): o nome do fuso horário para conversão da hora local do visitante.  O padrão é UTC/GMT. Consulte [List of TZ database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) na Wikipédia para obter uma lista completa de valores válidos.

Valores válidos comuns incluem:

* `"America/New_York"` para Eastern Time (horário do leste)
* `"America/Chicago"` para Central Time (horário central)
* `"America/Denver"` para Mountain Time (horário das montanhas)
* `"America/Los_Angeles"` para Pacific Time (horário do pacífico)

Chamar essa função retorna uma string que contém os itens a seguir delimitados por uma barra vertical (`|`):

* O ano atual
* O mês atual
* O dia do mês
* O dia da semana
* A hora atual (AM/PM)

## Exemplos

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## Histórico da versão

### 6.3 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 6.2 (5 de novembro de 2019)

* Correções de pequenos erros
* Tamanho total do código reduzido

### 6.1 (26 de novembro de 2018)

* Correção para navegadores Internet Explorer. Eles podem retornar o horário, mas somente no horário local do visitante.

### 6.0 (14 de agosto de 2018)

* Reescrita completa para acomodar os padrões internacionais. Agora converte o horário de verão e todos os fusos horários adequadamente.

### 5.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código)
* Foi removida a necessidade do parâmetro `tpDST`, já que as datas de início/término do horário de verão agora são detectadas automaticamente

>[!CAUTION]
>
>As versões anteriores desse plug-in não acomodavam todos os anos no futuro. Se você usar uma versão anterior desse plug-in, a Adobe recomenda que você atualize para a versão mais recente para evitar erros de JavaScript e perda de dados. Se a atualização desse plug-in não for viável, verifique se a variável `s._tpdst` no código do plug-in contém os anos apropriados no futuro.

### 4.0 (22 de agosto de 2016)

* Fornece uma solução totalmente nova e agora inclui informações de ano, mês e data.
