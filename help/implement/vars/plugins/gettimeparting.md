---
title: getTimeParting
description: Meça o tempo em que uma ação específica ocorre.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Plug-in da Adobe: getTimeParting

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getTimeParting` plug-in permite capturar os detalhes do tempo em que qualquer atividade mensurável ocorre no site. Esse plug-in é importante quando você deseja detalhar métricas por qualquer divisão de tempo repetível em um intervalo de datas específico. Por exemplo, você pode comparar as taxas de conversão entre dois dias diferentes da semana, como todos os domingos e todas as quintas-feiras. Você também pode comparar períodos do dia, como todas as manhãs e todas as noites.

A Analysis Workspace fornece dimensões semelhantes e predefinidas que são formatadas de forma ligeiramente diferente deste plug-in. Consulte [separação de dimensões](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) no guia do usuário Analisar para obter mais informações. Algumas organizações consideram que as dimensões predefinidas da Analysis Workspace são suficientes.

> [A versão 4.0+ IMPORTANTE] desse plug-in é significativamente diferente das versões anteriores. A Adobe recomenda implementar este plug-in &quot;do zero&quot;. O código que faz referência ao plug-in antes da versão 4.0 não é compatível com a versão atual desse plug-in.

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
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getTimeParting` método usa o seguinte argumento:

**`t`**(Opcional, mas recomendado, sequência): O nome do fuso horário para converter a hora local do visitante.  O padrão é UTC/hora GMT. Consulte[Lista de fusos](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)horários do banco de dados TZ na Wikipédia para obter uma lista completa de valores válidos.

Valores válidos comuns incluem:

* `"America/New_York"` para Hora Oriental
* `"America/Chicago"` para Hora Central
* `"America/Denver"` para Hora das Montanhas
* `"America/Los_Angeles"` para Hora do Pacífico

Chamar esse método retorna uma string que contém o seguinte delimitado por um pipe (`|`):

* O ano atual
* O mês atual
* O dia do mês
* O dia da semana
* A hora atual (AM/PM)

## Exemplos de chamadas

### Exemplos para fusos horários específicos

Use o seguinte código de amostra se o cliente estiver em Paris, França:

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Se o cliente estiver em San Jose, Califórnia:

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Se o cliente estiver no país africano do Gana:

```js
s.eVarX = getTimeParting();
```

O Gana está dentro do fuso horário UTC/GMT.  Este exemplo mostra que nenhum argumento de plug-in será necessário nessas circunstâncias.

### Contabilização dos Navegadores Internet Explorer

Use a seguinte amostra se desejar excluir dados de separação de tempo dos Visitantes do Internet Explorer (já que o valor retornado dos navegadores IE pode estar somente no horário local do visitante)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Resultados de chamadas

Se um visitante de Denver, Colorado, visitar um site em 31 de agosto de 2020 às 9h15,

Executando o seguinte código...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...definiria s.eVar10 igual a &quot;year=2020| mês=agosto| data=31| dia=Sexta-feira| hora=18:15&quot;

Enquanto o seguinte código...

```js
s.eVar10 = getTimeParting("America/Nome");
```

...definiria s.eVar10 igual a &quot;year=2020| mês=agosto| data=31| dia=Sexta-feira| time=6:15 AM&quot;

O seguinte código...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...definiria s.eVar10 igual a &quot;year=2020| mês=agosto| data=31| dia=Sexta-feira| hora=8:45&quot;

E o seguinte código...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...definiria s.eVar10 igual a &quot;year=2020| mês=setembro| data=1| dia=Sábado| time=1:15 AM&quot;

## Histórico da versão

### 6.2 (5 de novembro de 2019)

* Correções de pequenos erros
* Tamanho total do código reduzido

### 6.1 (26 de novembro de 2018)

* Correção para navegadores Internet Explorer. Eles podem retornar o horário, mas somente no horário local do visitante.

### 6.0 (14 de agosto de 2018)

* Reescrita completa para acomodar os padrões internacionais. Agora converte as economias diurnas e todos os fusos horários adequadamente.

### 5.0 (17 de abril de 2018)

* Versão do ponto (recompilado, tamanho de código menor)
* Foi removida a necessidade do `tpDST` parâmetro, já que as datas de início/término da economia de dia agora são detectadas automaticamente

### 4.0 (22 de agosto de 2016)

* Fornece uma solução totalmente nova e agora inclui informações de ano, mês e data.
