---
title: getTimeParting
description: Meça o tempo em que uma ação específica ocorre.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getTimeParting

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getTimeParting` permite capturar os detalhes do tempo de execução de qualquer atividade mensurável que ocorre no site. Esse plug-in é importante quando você deseja detalhar métricas em qualquer divisão de tempo repetível, dentro de um intervalo de datas específico. Por exemplo, você pode comparar as taxas de conversão de dois dias diferentes da semana, como todos os domingos e todas as quintas-feiras. Você também pode comparar períodos do dia, como todas as manhãs e todas as noites.

O Analysis Workspace fornece dimensões semelhantes e predefinidas formatadas de forma ligeiramente diferente que nesse plug-in. Consulte [dimensões de separação de tempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) no Guia do usuário Analisar para obter mais informações. Algumas organizações consideram que as dimensões predefinidas do Analysis Workspace são suficientes.

>[IMPORTANTE] A versão 4.0+ desse plug-in é significativamente diferente das versões anteriores. A Adobe recomenda implementar esse plug-in &quot;do zero&quot;. O código que faz referência ao plug-in antes da versão 4.0 não é compatível com a versão atual desse plug-in.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getTimeParting
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getTimeParting` aceita o seguinte argumento:

**`t`** (opcional, mas recomendado, string): o nome do fuso horário para conversão da hora local do visitante.  O padrão é UTC/GMT. Consulte [List of TZ database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) na Wikipédia para obter uma lista completa de valores válidos.

Valores válidos comuns incluem:

* `"America/New_York"` para Eastern Time (horário do leste)
* `"America/Chicago"` para Central Time (horário central)
* `"America/Denver"` para Mountain Time (horário das montanhas)
* `"America/Los_Angeles"` para Pacific Time (horário do pacífico)

Chamar esse método retorna uma string que contém os itens a seguir delimitados por uma barra vertical (`|`):

* O ano atual
* O mês atual
* O dia do mês
* O dia da semana
* A hora atual (AM/PM)

## Exemplos de chamadas

### Exemplos para fusos horários específicos

Use o código de amostra a seguir se o cliente estiver em Paris, França:

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Se o cliente estiver em San Jose, Califórnia:

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Se o cliente estiver no país africano de Gana:

```js
s.eVarX = getTimeParting();
```

Gana está no fuso horário UTC/GMT.  Este exemplo mostra que, nessas circunstâncias, nenhum argumento do plug-in será necessário.

### Contabilização para navegadores Internet Explorer

Use a seguinte amostra se desejar excluir dados de separação de tempo dos visitantes que usam Internet Explorer (já que o valor retornado pelos navegadores IE pode estar somente no horário local do visitante)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Resultados de chamadas

Se um visitante de Denver, Colorado, visitar um site em 31 de agosto de 2020 às 9:15,

Executar o código a seguir...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

... definiria s.eVar10 como &quot;year=2020 | month=agosto | date=31 | day=sexta-feira | time=18:15&quot;

Enquanto o código a seguir...

```js
s.eVar10 = getTimeParting("America/Nome");
```

... definiria s.eVar10 como &quot;year=2020 | month=agosto | date=31 | day=sexta-feira | time=06:15&quot;

O código a seguir...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

... definiria s.eVar10 como &quot;year=2020 | month=agosto | date=31 | day=sexta-feira | time=20:45&quot;

E o código a seguir...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

... definiria s.eVar10 como &quot;year=2020 | month=setembro | date=1 | day=sexta-feira | time=01:15&quot;

## Histórico da versão

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

### 4.0 (22 de agosto de 2016)

* Fornece uma solução totalmente nova e agora inclui informações de ano, mês e data.
