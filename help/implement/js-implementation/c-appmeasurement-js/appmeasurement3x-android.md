---
description: AppMeasurement 3.x para Android
seo-description: Documentação antiga do AppMeasurement 3.x para Android
seo-title: AppMeasurement 3.x para Android
solution: Analytics
subtopic: Marcadores
title: AppMeasurement 3.x para Android
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 595efd52fe3b8edae32d8b3c2216ea066ec642be

---


# AppMeasurement 3.x para Android

*Observação: Este documento contém informações herdadas para versões anteriores do AppMeasurement, especificamente para as versões 3.x para Android.
Para obter informações sobre a implementação atual do AppMeasurement, consulte[Sobre o AppMeasurement para Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).*

*Última atualização do AppMeasurement 3.x para Android em 15/03/2018*

O Adobe AppMeasurement para Android permite avaliar aplicativos Android nativos na Adobe Experience Cloud.

Este guia está dividido em duas seções. uma seção para o analista que tem experiência com o Adobe Analytics e uma seção para o desenvolvedor do Android com experiência em desenvolvimento de aplicativo móvel.

**Versões** suportadas: Android 2.0 ou posterior.

**Baixe as instruções e os links de Download da biblioteca** para todas as plataformas móveis do AppMeasurement que estão disponíveis na página Medição e otimização de aplicativos móveis no Developer Connection. É necessário ter uma conta gratuita do Developer Connection ou um logon do SiteCatalyst para fazer o download das bibliotecas. Os links de download não são exibidos até que você se conecte.

## Início rápido de analista

Esta seção aborda a implementação da biblioteca Android e adiciona o código necessário para uma implementação padrão. As etapas são incluídas para mostrar como enviar eventos personalizados e outros dados.

Como analista, você precisará habilitar os Relatórios de aplicativo móvel para seu conjunto de relatórios. Você deve fornecer para seu desenvolvedor uma descrição das variáveis de dados de contexto que devem ser enviadas pelo aplicativo, caso tenha métricas adicionar para capturar. Por exemplo, para coletar o nome de usuário após o login, seu desenvolvedor pode colocar o nome de usuário em uma variável de dados de contexto chamada `myco.username`.

### Habilitar Relatórios de aplicativo móvel no SiteCatalyst

O SiteCatalyst fornece uma interface para habilitar o Rastreamento do ciclo de vida do aplicativo móvel. O mapa permite que o SiteCatalyst gere automaticamente os Relatórios de aplicativo móvel.

1. Abra Console de administração &gt; Conjuntos de relatórios &gt; Editar configurações &gt; Gerenciamento móvel &gt; Relatório de aplicativo móvel.
1. Clique em Habilitar rastreamento do ciclo de vida do aplicativo móvel.

As medições de ciclo de vida foram capturadas e os Relatórios de aplicativo móvel aparecem no menu Relatórios do SiteCatalyst.

### Capturar métricas adicionais usando Regras de processamento

Se sua implementação envia eventos ou dimensões adicionais utilizando variáveis de dados de contexto, você deve configurar regras de processamento para capturar os dados.

Antes de criar Regras de processamento, um indivíduo em sua organização deve ser certificado. Para obter mais informações, consulte a Ajuda para Regras de processamento.

Após a ativação das regras de processamento, o exemplo de Copiar uma variável de dados de contexto demonstrará o processo necessário para mapear os dados de contexto.

### (Opcional) Ativar o rastreamento offline

Se você planeja armazenar ocorrências quando o dispositivo está offline, é necessário ativar o carimbo de data/hora do conjunto de relatórios.

Depois de ativar o rastreamento offline, todas as ocorrências devem ter um carimbo de data/hora ou não serão coletadas. Se você está relatando sobre dados do AppMeasurement para um conjunto de relatórios que também coleta dados do JavaScript, pode ser necessário configurar um conjunto de relatórios separado para dados móveis a fim de evitar perda de dados ou incluir um carimbo de data e hora personalizado nas ocorrências de JavaScript utilizando a variável s.timestamp.

Se não tiver certeza se o conjunto de relatórios tem carimbo de data e hora, entre em contato com o Client Care.

## Início rápido para desenvolvedores

Esta seção aborda a seleção e configuração de eventos, eVars e props que você usará para coletar dados do Android. As etapas também são incluídas para criar Regras de processamento para copiar os dados de contexto enviados pela biblioteca Android para estas variáveis.

As etapas para implementar a biblioteca do Android e iniciar o envio de dados de medição são as seguintes:

* Obtenha a Biblioteca
* Adicionar a biblioteca ao seu projeto
* Adicionar permissões do aplicativo
* Um resumo sobre o TrackingHelper
* Implementação

### Obtenha a Biblioteca

Visite Medição e otimização de aplicativos móveis no Developer Connection para fazer o download da biblioteca do Android. Após descompactar o arquivo, você terá os seguintes componentes de software:

* admsAppLibrary.jar: a biblioteca projetada para o uso com dispositivos e simuladores Android. Requer Android 2.0 ou posterior.
* Examples\TrackingHelper.java: classe opcional que é designada para manter o código de rastreamento separado do seu aplicativo lógico.

### Adicionar a biblioteca ao seu projeto

1. No Eclipse IDE, clique com o botão direito do mouse no nome do projeto.
1. Selecione Caminho de criação &gt; Adicionar arquivos externos.
1. Selecionar `admsAppLibrary.jar`.
1. Clique em Abrir.
1. Clique novamente no projeto com o botão direito do mouse e selecione Build Path (Caminho de criação) &gt; Configure Build Path (Configurar caminho de criação).
1. Clique na guia Order and Export (Solicitar e exportar).
1. Certifique-se de que `admsAppLibrary.jar` está selecionado.

Seu aplicativo pode importar classes/interfaces da biblioteca admsAppLibrary.jar usando importar com.adobe.ADMS.*;

### Adicionar permissões do aplicativo

A biblioteca do AppMeasurement pede as seguintes permissões para enviar dados e gravar chamadas de rastreamento offline:

* INTERNET
* ACCESS_NETWORK_STATE

Para adicionar essas permissões, adicione as seguintes linhas para o seu arquivo AndroidManifest.xml (no diretório do projeto do aplicativo):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### Um resumo sobre o TrackingHelper

O SDK inclui uma classe adicional e optativa, chamada de TrackingHelper. TrackingHelper fornece uma maneira de separar seu código de medição da lógica do aplicativo.

Considere o seguinte exemplo: em seu aplicativo, você deseja enviar um evento que rastreia cada logon. Você pode adicionar o seguinte código diretamente depois do seu código de logon para enviar este evento (não se preocupe com os detalhes do código, chegaremos lá):

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

Essa abordagem direta está correta, mas não seria melhor colocar esse código em outro lugar para que não atrapalhe o desenvolvimento de seu aplicativo? O TrackingHelper é este "outro lugar". No TrackingHelper, você pode colocar este código em um método chamado trackLogonEvent:

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

Agora, no código do seu aplicativo, você pode rastrear um evento de logon com uma simples chamada para trackLogonEvent:

TrackingHelper.trackLogonEvent("nome de usuário");

A chamada de medição no código de seu aplicativo se resume a uma única linha. Além disso, se a lógica de medição subjacente precisar se alterada, será necessário atualizar apenas o TrackingHelper. Se outro desenvolvedor fizer uma adição ao seu código ele poderá utilizar os métodos simplificados que você tenha definido, sem precisar fazer um curso rápido sobre a biblioteca do AppMeasurement.

Talvez você prefira usar o TrackingHelper para fazer novas implementações, mesmo que a configuração exija um ou dois minutos a mais. As etapas restantes neste guia abordam as etapas para definir o TrackingHelper e iniciar o envio de dados de medição.

Certifique-se de copiar TrackingHelper.java para um diretório que contém arquivos de classe para seu aplicativo e substitua o nome do pacote na parte superior deste arquivo para corresponder a sua estrutura de pacote (com.company.application). Se preferir implementar o TrackingHelper, você pode encontrar várias mostras no TrackingHelper que você pode copiar para seu aplicativo.

### Implementação

1. Abra TrackingHelper.java e atualize TRACKING_RSID e TRACKING_SERVER com sua ID do conjunto de relatórios e o servidor do rastreamento. Por exemplo:

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   Estes valores são necessários e devem estar corretos ou a medição não funcionará. Se estiver inseguro quanto esses valores pergunte ao especialista do SiteCatalyst.

2. Encontre o método configureAppMeasurement. Aqui é onde você ativa o SSL, o rastreamento offline e faz outras alterações globais em suas configurações. Por enquanto, exclua o comentário da linha para ativar o debugLogging até que tudo esteja funcionando da forma desejada.

3. Adicione uma chamada a configureAppMeasurement da atividade raiz do seu aplicativo.

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

Este é todo o código que você precisa para iniciar o rastreamento de métricas personalizadas. No entanto, com mais algumas linhas de código você poderá ativar o rastreamento do ciclo de vida para enviar medições do ciclo de vida automaticamente, incluindo inicializações, atualizações, paralisações e usuários diários e mensais.

A biblioteca do AppMeasurement faz todo o trabalho pesado, então tudo o que você precisa fazer é adicionar duas chamadas de método para cada classe de Atividade do seu aplicativo.

### (Recomendado) Rastrear eventos de ciclo de vida

Quando o rastreamento de ciclo de vida estiver ativado, cada vez que o aplicativo for iniciado, uma única ocorrência será enviada para rastrear instalações, atualizações, dias envolvidos e outras Medições de ciclo de vida.

Para começar a rastrear eventos de ciclo de vida em seu aplicativo, adicione chamadas aos métodos onResume() e onPause() em cada atividade no aplicativo, como mostrado no seguinte exemplo. Recomendamos transferir a Atividade ou o Serviço como o objeto de contexto em vez do contexto de Aplicativo global.

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

Pronto! Você implementou o rastreamento básico ciclo de vida em seus aplicativo Android. Depois que seu Analista da Web configurar o SiteCatalyst para processar as métricas do AppMeasurement que você está enviando, o conjunto de relatórios do SiteCatalyst conterá as medições de ciclo de vida padrão.

O que fazer agora?

* (Opcional) Rastrear eventos personalizados. Adicione métodos personalizados a TrackingHelper para rastrear todos os eventos que você deseja medir em seu aplicativo. Você pode adicionar métodos para rastrear logon, comprar de aplicativos, entre outros.
* (Opcional) Rastrear aplicativos personalizados. O estado de um aplicativo é parecido com uma visualização da página. Esta seção mostra como adicionar um método personalizado ao TrackingHelper para rastrear um estado de um aplicativo.
* Início rápido para a avaliação de vídeo. Adicionar um código para rastrear automaticamente métricas de vídeo incluindo a exibição de vídeos, o tempo total de reprodução e os vídeos mais populares.

### (Opcional) Rastrear eventos personalizados

Os eventos personalizados são métricas de sucesso e únicas para o seu aplicativo. Você deve enviar um evento personalizado quando um usuário faz o logon, inicia uma compra no aplicativo ou clica em um link para sua página do Facebook. A classe tracking helper contém um exemplo que mostra como rastrear um evento personalizado. Você pode utilizar este método como um modelo para adicionar métodos de rastreamento de eventos adicional.

Em TrackingHelper.java, defina um método de rastreamento de evento personalizado:

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

Em todo o seu código, você pode chamar este método para rastrear um evento personalizado:

`TrackingHelper.trackCustomEvents();`

Use este processo para adicionar a quantidade de métodos de rastreamento de evento que for necessária. Uma palavra rápida sobre o TrackingHelper contém um método de exemplo para rastrear um evento de logon.

### (Opcional) Rastrear aplicativos personalizados

A classe tracking helper também contém um exemplo que mostra como rastrear um estado de aplicativo. Rastrear um estado personalizado é muito parecido com rastrear um evento. A única diferença é que você usar o método trackAppState em vez de trackEvents.

```
measure.trackAppState("name", contextData);
```

De um ponto de vista de relatórios, o trackAppState aumenta as exibições de página, diferente do trackEvents.

## Início rápido para a avaliação de vídeo

A medição de vídeo está descrita no guia Medição de vídeo em SiteCatalyst. O processo geral para medição de vídeo é muito parecido em todas as plataformas AppMeasurement. Esta seção de início rápido fornece uma visão geral básica das tarefas do desenvolvedor junto com exemplos de código.

A mesma biblioteca, admsAppLibrary.jar, é usada para o rastreamento do aplicativo e do vídeo. A documentação se refere a esses métodos assim como ao módulo de mídia para fins de consistência em todas as plataformas.

Você precisa ter uma instância de medição configurada antes de poder usar um módulo de mídia.

Complete as seguintes tarefas para implementar o rastreamento de vídeo no Android:

* Variáveis de mapeamento de eventos do Player para o SiteCatalyst
* Configurar fases, segmentos e frequência de chamada
* Rastrear eventos de vídeo

### Variáveis de mapeamento de eventos do Player para o SiteCatalyst

Você precisa mapear as eVars e os eventos SiteCatalyst selecionados para rastreamento de vídeo para variáveis de dados de contexto para configurar a medição de vídeo. Para obter mais informações, consulte Configuração de vídeo no SiteCatalyst.

O seu Analista de Web deve fornecer a você uma Planilha de implementação de vídeo que contenha uma lista das variáveis do SiteCatalyst que ele configurou para receber os dados de vídeo:

* Nome do vídeo (eVar): eVar2
* Nome do vídeo (Prop): prop2
* Segmentos (eVar): eVar3
* Tipo de conteúdo (eVar): eVar1
* Tempo do vídeo (Evento): event3
* Exibições de vídeo (Evento): event1
* Término do vídeo (Evento): event7
* Exibições de segmentos de vídeo (Evento): event2

1. Adicione o código a seguir após o código adicionado em Implementação, substituindo a variável do SiteCatalyst selecionada com o exemplo no código:

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. Configurar fases, segmentos e frequência de chamada.

3. Rastrear eventos de vídeo.


### Configurar fases, segmentos e frequência de chamada

As fases permitem que você envie um evento quando atingir um ponto específico do vídeo. Os segmentos permitem que você divida o vídeo em seções para um rastreamento mais granular. As frequências de chamada permitem que você envie chamadas de medição com a visualização do tempo em intervalos específicos. Para obter mais informações, consulte Métricas de vídeo.

### Mapear etapas

É possível definir etapas com base em um percentual da duração total ou nos segundos decorridos. Este exemplo define as etapas como uma porcentagem da duração total. Em um vídeo de dois minutos, o código a seguir envia eventos de fases em 30, 60 e 90 segundos.

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### Mapear etapas de compensação

Este exemplo define as etapas por cada segundo decorrido a partir do início do vídeo. Em um vídeo de dois minutos, código a seguir envia eventos de fases em 20, 40 e 60 segundos.

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### Exemplos

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### Rastrear eventos de vídeo

Para medir o vídeo, você precisa adicionar o código que informa ao módulo de mídia quando os eventos ocorrem em seu player. Utilizando os métodos open, play, stop e close. Quando um usuário iniciar um vídeo, você deve chamar o método reproduzir para que o módulo de mídia inicie a contagem de segundos visualizados.

Caso o usuário pare o vídeo, você precisará chamar uma ação de parada para que a contagem seja pausada. Essa ação costuma ser realizada com eventos de manuseio expostos pelo player. 

Por exemplo:

Carregar: chama open e play

Pausar: chama stop. Por exemplo, se um usuário pausar um vídeo depois de 15 segundos, chama stop("Video1",15)

Buffer: chama stop enquanto é feito o buffer do vídeo. Chama play quando a reprodução é retomada.

Retomar: chama play. Por exemplo, quando um usuário retoma um vídeo após 15 segundos, chama s.play("Video1",15).

Scrub (controle deslizante): quando o usuário arrasta o controle deslizante do vídeo, chama stop. Quando o usuário solta o controle deslizante do vídeo, chama play.

Encerrar: chame stop, em seguida close. Por exemplo, ao fim de um vídeo de 100 segundos, chame stop("Video1",100), em seguida close("Video1").

Para chegar a este resultado é possível definir quatro funções personalizadas que você pode chamar pelos manipuladores de evento do reprodutor de mídia. Os vários parâmetros passados para open, play, stop e close vêm do player. Os pseudo códigos demonstram como isto deve ser feito:

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## Medições de ciclo de vida

Esta planilha lista métricas e dimensões medidas quando o rastreamento de ciclo de vida automático está ativado.

### Medições de ciclo de vida e dimensões

Quando configuradas, as medições de ciclo de vida são enviadas nos parâmetros de dados de contexto ao Analytics, nos parâmetros ao Destino com cada chamada mbox e como um sinal ao gerenciamento de público-alvo. Analytics e Destino usam o mesmo formato, enquanto que o gerenciamento de público-alvo usa um prefixo diferente para cada métrica.

Para o Analytics, os dados de contexto enviados com cada chamada de rastreamento de ciclo de vida são capturados automaticamente e relatados usando a métrica ou dimensão listada na primeira coluna, com as exceções observadas na coluna de descrição.

| Métrica | Contexto do Analytics | Descrição do sinal do Audience Manager no contexto do Analytics | Parâmetro de dados/destino |
|--- |--- |--- |--- |
| Primeiras inicializações | a.InstallEvent | c_a_InstallEvent | Disparado na primeira execução após a instalação (ou reinstalação). |
| Atualizações | a.UpgradeEvent | c_a_UpgradeEvent | Disparado na primeira execução após as atualizações (sempre que o número da versão mudar). |
| Usuários envolvidos diariamente | a.DailyEngUserEvent | c_a_DailyEngUserEvent | Disparado quando o aplicativo é utilizado em um dia específico. |
| Usuários envolvidos mensalmente | Usuários envolvidos mensalmente | a.MonthlyEngUserEvent | Disparado quando o aplicativo é utilizado durante um mês em particular. |
| Inicializa | a.LaunchEvent | c_a_LaunchEvent | Desencadeado a cada execução, incluindo falhas e instalações. | Inicializações Também acionadas em um resumo do plano de fundo quando o tempo limite da sessão do ciclo de vida for excedido. |
| Falhas | a.CrashEvent | c_a_CrashEvent | Dispara quando o aplicativo não se fecha levemente. O evento é enviado no momento da inicialização do aplicativo após o travamento (o aplicativo é considerado travado se não for fechado). |
| Duração da sessão anterior | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Extensão da sessão anterior total agregada em segundos. |

*Observação: Usuários **envolvidos**diariamente e Usuários **envolvidos**mensalmente não são armazenados automaticamente em uma métrica do Analytics. Você deve criar uma regra de processamento que defina um evento personalizado para capturar essa métrica.*

### Dimensões

| Métrica | Parâmetro do Target/Dados de contexto do Analytics | Sinal do Audience Manager de contexto do Analytics | Descrição |
|--- |--- |--- |--- |
| Data de instalação | a.InstallDate | c_a_InstallDate | Data do início após instalação. DD/MM/AAAA |
| Atualizações | a.UpgradeEvent | c_a_UpgradeEvent | Disparado na primeira execução após as atualizações (sempre que o número da versão mudar). |
| ID do aplicativo | a.AppID | c_a_AppID | Armazena o nome e a versão do aplicativo no seguinte formato:`[AppName] [BundleVersion]`. Por exemplo, myapp 1.1. |
| Dias desde a primeira visita | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | Número de dias desde a primeira execução. |
| Usuários envolvidos mensalmente | Usuários envolvidos mensalmente | a.MonthlyEngUserEvent | Disparado quando o aplicativo é utilizado durante um mês em particular. |
| Inicializa | a.LaunchEvent | c_a_LaunchEvent | Desencadeado a cada execução, incluindo falhas e instalações. | Inicializações Também acionadas em um resumo do plano de fundo quando o tempo limite da sessão do ciclo de vida for excedido. |
| Falhas | a.CrashEvent | c_a_CrashEvent | Dispara quando o aplicativo não se fecha levemente. O evento é enviado no momento da inicialização do aplicativo após o travamento (o aplicativo é considerado travado se não for fechado). |
| Duração da sessão anterior | a.PreviousSessionLength | Cc_a_PreviousSessionLength | Extensão da sessão anterior total agregada em segundos. |
| Dias desde a última visita | a.DaysSinceLastUse | c_a_DaysSinceLastUse | Número de dias desde a última utilização. |
| Dias da semana | a.DayOfWeek | c_a_DayOfWeek | Número do dia da semana no qual o aplicativo foi iniciado. |
| Hora do dia | a.HourOfDay | c_a_HourOfDay | Medie a hora que o aplicativo foi iniciado. Formato numérico 24 horas. Utilizado para hora do visitante para determinar os tempos de pico de uso. |
| Versão do sistema operacional | a.OSVersion | c_a_OSVersion | Versão do sistema operacional. |
| Dias desde a última atualização | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | Número de dias desde que o número de versão do aplicativo foi alterado. |
| Inicializações desde a última atualização | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | Número de inicializações desde que o número de versão do aplicativo foi alterado. |
| Nome do dispositivo | a.DeviceName | c_a_DeviceName | Armazena o nome do dispositivo. | iOS: sequência de 2 dígitos separadas por vírgulas que identifica o dispositivo iOS. O primeiro número tipicamente representa a geração do dispositivo e o segundo, versões dos diferentes membros da família do dispositivo. Consulte Versões do dispositivo iOS para obter uma lista de nomes comuns de dispositivo. |
| Nome da operadora | a.CarrierName | c_a_CarrierName | Armazena o nome do servidor de serviços para dispositivos móveis, conforme fornecido pelo dispositivo. |
| Resolução | a.Resolution | c_a_Resolution | Largura x altura em pixels |

*Observação:**Dias desde a última atualização**,**Inicializações desde a última atualização**e o nome **da**operadora não são armazenados automaticamente em uma variável do Analytics. You must create a processing rule to copy these values to an Analytics variable for reporting.*

## Dados de contexto

Os dados de contexto são o método preferencial para enviar dados de aplicativos para os servidores de coleta.

Em vez atribuir explicitamente os valores aos props e eVars, você pode utilizar as variáveis de dados de contexto para enviar pares de nome/valor que são mapeados no SiteCatalyst. Com base nesses pares de valores chave, é possível definir eventos, copiar valores para eVars e props e executar declarações condicionais adicionais. Isso ajuda a impedir que você faça atualizações de código para oferecer suporte a diferentes configurações do conjunto de relatórios.

Há duas maneiras de enviar dados de contexto com os métodos de rastreamento. Quaisquer dados de contexto definidos diretamente no objeto PersistentContextData são enviados em cada chamada. Você também pode enviar os dados de contexto como parâmetro para uma chamada de rastreamento única, que é enviada apenas com a chamada.

### Dados de contexto persistentes

Os valores colocados em Dados de contexto persistentes são enviados com cada chamada de servidor. No exemplo a seguir, "key" e "value" são enviados com todas as chamadas trackAppState:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### Dados de contexto de chamada única

Para enviar dados de contexto para uma chamada única, envie Dados de contexto como parâmetro para a chamada de rastreamento (trackAppState, trackEvents e assim por diante).

No seguinte exemplo, "key" e "value" são enviados com todas as três chamadas trackAppState. No entanto, "key2" e "value2" são enviados somente com a segunda chamada trackAppState:

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## Variáveis de configuração

As variáveis a seguir são definidas quando os aplicativos são iniciados:

*Observação: Todas as variáveis de configuração são opcionais, exceto ReportSuiteID e trackingServer.*

**Instância compartilhada**

Antes de realizar chamadas de medição, você deve recuperar uma instância da biblioteca para cada método que você chamar na biblioteca de medição:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Observação: as variáveis de configuração são privadas. Utilize os métodos de obter e definir para mudar estes valores.*

### Variáveis de configuração

**reportSuiteIDs**: (Obrigatório) O conjunto de relatórios ou os conjuntos de relatórios (marcação de vários relatórios) que você deseja rastrear. Para rastrear vários conjuntos de relatórios, passe uma lista delimitada por vírgula dos nomes de cada conjunto de relatórios.

Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

Exemplos:

`measure.setReportSuiteIDs("rsid");`

Marcação de vários relatórios:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**: (Obrigatório) Identifica o servidor de coleta.

Essa variável deve ser preenchida com o domínio do seu servidor de monitoramento, sem um prefixo de protocolo "http://" ou https://". O prefixo de protocolo é manipulado automaticamente pela biblioteca com base na variável ssl.

Se ssl for true, é realizada uma conexão segura com o servidor. Se ssl for false, é realizada uma conexão insegura com o servidor.

Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

Exemplos:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**: Padrão: identificador uuidExclusivo para cada visitante. Se você não definir uma visitorID personalizada uma visitorID única será gerada.

Nós recomendamos a utilização do padrão a não ser que você tenha um caso de utilização específico para definir a visitorID. A definição de uma visitorID personalizada tem o potencial de causar visitas duplicadas ao utilizar o rastreamento de ciclo de vida. Para evitar isso, defina a ID do visitante antes de configurar a medição do aplicativo.

**characterSet**: O padrão é UTF-8

Sintaxe:

```
String getCharSet()
void setCharSet(String charSet)
```

Exemplos:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**:o padrão é nenhum (o valor definido para o conjunto de relatórios é usado)

O código de moeda utilizado para eventos de compra ou moeda que são rastreados no aplicativo para Android.

Sintaxe:

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

Exemplos:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**: O padrão é 5 minutos

Especifica a duração, em segundos, entre as inicializações do aplicativo antes que a inicialização seja considerada uma nova sessão. Esse tempo de espera também se aplica quando seu aplicativo é enviado para segundo plano e reativado. O tempo que seu aplicativo gasta em segundo plano não está incluído na duração da sessão.

Sintaxe:

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

Exemplos:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**: O padrão é falso

Habilita (true) ou desabilita (false) o envio de dados de medição via SSL (HTTPS). Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:

`void setSSL(boolean ssl)`

Exemplos:

`measure.setSSL(true);`

**debugLogging** Default é falso

Ativa (verdadeiro) ou desativa (falso) a visualização de informações e a versão da biblioteca no console de saída. O padrão desta variável é false. Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:

`void setDebugLogging(boolean debugLogging)`

Exemplos:

`measure.setDebugLogging(true);`

## Rastreamento de variáveis

**Instância compartilhada**

Antes de realizar chamadas de medição, você deve recuperar uma instância da biblioteca para cada método que você chamar na biblioteca de medição:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*Observação: as variáveis de configuração são privadas. Utilize os métodos de obter e definir para mudar estes valores.*

### Variáveis de rastreamento persistente

**Evar**: Define a eVar especificada para o valor fornecido. O eVar é enviado com todas as chamadas de rastreamento até que seja esvaziado ao ser enviado a uma sequência de caracteres vazia ou chamando a limpeza de vars.

Sintaxe:

`void setEvar(int evarNum, String evarValue)`

Exemplo:
`measure.setEvar(1, "value");`

**Prop**: Define a prop especificada para o valor fornecido. O prop é enviado com todas as chamadas de rastreamento até que seja apagado ao configurá-lo como uma sequência de caracteres vazia ou chamando clearVars.

Sintaxe:

`void setProp(int propNum, String propValue)`

Exemplo:

`measure.setProp(1, "value");`

**Hier**: Define a variável herdada especificada para o valor fornecido. A variável hier é enviada com todas as chamadas de rastreamento até que seja esvaziado ao ser enviado a uma sequência de caracteres vazia ou chamando clearVars.

Sintaxe:

`void setHier(int hierNum, String hierValue)`

Exemplo:

`measure.setHier(1, "value");`


**ListVar**: Define a listVar especificada para o valor fornecido. A listVar é enviada com todas as chamadas de rastreamento até que seja apagada ao defini-la como uma sequência de caracteres vazia ou chamando clearVars.

Sintaxe:

`void setListVar(int listNum, String listValue)`

Exemplo:

`measure.setListVar(1, "value");`

**purchaseID**: A purchaseID é usada para impedir que um pedido seja contado várias vezes pelo SiteCatalyst.

Sempre que o evento de compra foi usado no seu site, você deve atribuir uma id exclusiva a essa compra usando a variável purchaseID.

`measure.setPurchaseID("unique_id");`

**transactionID**: As Fontes de Dados de Integração usam uma ID de transação para vincular dados offline a uma transação online (como um cliente potencial ou compra gerada online).

Cada transactionID única enviada para a Adobe é registrada em preparação para um carregamento de Fontes de dados de informações offline sobre essa transação.

`measure.setTransactionID("unique_id");`

**appState**: (nome da página) O valor fornecido para o estado do aplicativo é armazenado na variável de nome da página.

`measure.setAppState("state");`

**canal**: measurement.setChannel("mobile");

**appSection**: O valor fornecido para a seção do aplicativo é armazenado na variável do servidor.

Sintaxe:

`void setAppSection(String Section)`

Exemplo:
`measure.setAppSection("news");`

**campaign**

Sintaxe:

`void setCampaign(String Campaign)`

Exemplo:

`measure.setCampaign("112233");`

**products**

Sintaxe:

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

Exemplo:

`measure.setProducts("Running;Shoe");`

**events**

Sintaxe:

`void setEvents(String Event) //comma-delimited list`

Exemplo:

`measure.setEvents("event1, event2");`

**geoState**

Sintaxe:

`void setGeoState(String GeoState)`

Exemplo:

`measure.setGeoState("UT");`

**geoZip**

Sintaxe:

`void setGeoZip(String GeoZip)`

Exemplo:

`measure.setGeoZip("12345");`

**Dados** de contexto persistentes: Os valores inseridos em Dados de contexto persistentes são enviados com cada chamada de servidor. Para enviar dados de contexto para uma única chamada, envie uma tabela hash contextData como parâmetro para a chamada de rastreamento (trackAppState, trackEvents e assim por diante).

Exemplo:

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Consulte Dados de contexto.

**linkTrackVars**: Uma lista de nomes de variáveis delimitada por vírgulas que restringe o conjunto atual de variáveis para o rastreamento de links. Se linkTrackVars não estiver definido, o AppMeasurement para Android envia todas as variáveis definidas com uma chamada trackLink.

Sintaxe:

`void setLinkTrackVars(String Vars) //comma-delimited list`

Exemplo:

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**: Uma lista de eventos delimitada por vírgulas que restringe o conjunto atual de eventos para rastreamento de links. Se linkTrackEvents não estiver definida, o AppMeasurement para Android envia todos os eventos com uma chamada trackLink.

Sintaxe:

`void setLinkTrackEvents(String Events) //comma-delimited list`

Exemplo:

`measure.setLinkTrackEvents("event1, event2");`

## Métodos

Esta seção contém uma lista de métodos fornecidos pela biblioteca Android.

**Instância compartilhada**

Antes de realizar chamadas de medição, você deve recuperar uma instância da biblioteca para cada método que você chamar na biblioteca de medição:

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### Configuração inicial

Este método configura as variáveis necessárias e deve ser chamado antes de outros métodos.

**configureMeasurement**: Este método é usado para configurar os dois parâmetros necessários para iniciar a medição do aplicativo. Você deve definir os valores de reportSuiteIDs e trackingServer no objeto de medição usando este método antes de enviar qualquer chamada de servidor.

Sintaxe:

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

Exemplos:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### Rastreamento de evento e estado

Estes são os principais métodos usados para rastrear eventos personalizados e estados de aplicativo.

**trackAppState**: Essa é a maneira recomendada de rastrear os estados do aplicativo no aplicativo. O valor fornecido em appState aparece como a variável do nome da página da chamada do servidor. A sequência de caracteres appState deve ser fornecida para cada chamada desde que não seja transportada para a próxima chamada.

Os dados de contexto enviados com esta chamada são anexados a qualquer valor em persistentContextData e enviados com a chamada. Apenas os valores definidos em persistentContextData permanecem para a próxima chamada.

Sintaxe:

`void trackAppState(string AppStateName)`

Exemplos:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**: Essa é a maneira recomendada para rastrear eventos em seu aplicativo. trackEvents é semelhante a trackAppState, mas envia eventos em vez de nomes de páginas. Os eventos são fornecidos como uma sequência de caracteres delimitada por vírgulas. A sequência de caracteres de events deve ser fornecida para cada chamada, pois não é transportada para a próxima chamada.

Este método efetua uma chamada subjacente para trackLinkURL, onde linkURL está definido como nil, linkType está definido como "o" e linkName é preenchido com a ID do aplicativo.

Isso significa que linkTrackVars e linkTrackEvents se aplicam a chamadas para trackEvents.

Os dados de contexto enviados com esta chamada são anexados a qualquer valor em persistentContextData e enviados com a chamada. Apenas os valores definidos em persistentContextData permanecem para a próxima chamada.

Sintaxe:

`void trackEvents(string Events)`

Exemplos:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**Importe a nota se estiver usando o método trackLink**

O trackEvents efetua uma chamada subjacente para trackLink, onde linkURL está definido como null, linkType está definido como "o" e linkName é preenchido com a ID do aplicativo. Isso é realizado para impedir que a contagem de visualização de página (visualização de estado) seja aumentada sempre que você enviar um evento.

Se estiver chamando trackLink diretamente e definindo valores para linkTrackVars e linkTrackEvents, essas restrições de variável e evento se aplicam a TrackEvents. Isso significa que apenas as variáveis e os eventos definidos nessas listas serão enviados com o TrackEvents. É necessário definir linkTrackVars e linkTrackEvents como nulo a não ser que você deseja que as restrições sejam aplicadas a trackEvents.

### Rastreamento avançado (rastreamento e trackLink)

Esses métodos fornecem opções adicionais de rastreamento e permitem que você preencha diretamente props, eVars e outras variáveis do SiteCatalyst. Eles devem ser usados por clientes com uma implementação existente ou com clientes familiarizados com outras implementações do SiteCatalyst.

`track` e `trackLink` são os métodos principais de medição que são implementados em todas as versões das bibliotecas de medição da Adobe em várias plataformas. Em sua maioria, ao rastrear aplicativos móveis, é mais fácil usar os métodos trackAppState e trackEvents do que chamar o rastreamento e trackLink diretamente.

O rastreamento de visualização de página (track) e de link (trackLink) envia todas as variáveis persistentes que têm valores que não sejam nulos, vazios ou zero. Você deve reiniciar ou esvaziar todas as variáveis, conforme necessário, antes de chamar track ou trackLink.

*Observação: Devido a natureza de vários segmentos dos aplicativos modernos, não é recomendado configurar valores de variável persistente para enviar com uma chamada de rastreamento futura (usando setEvar, setProp, setHier, SetListVar e setPersistentContextData). Por exemplo, se um valor de variável for definido em vários threads, o valor pode estar em um estado inconsistente quando a chamada de rastreamento é feita. Para evitar isso, nós recomendamos passar os dados de contexto com cada chamada de rastreamento e definir o valor de variável em Regras de processamento.

**Descrições de métodos**

**faixa**: Envia uma exibição de página padrão, juntamente com quaisquer variáveis adicionais definidas no objeto de medição, para o servidor de coleção.

Cada chamada para rastrear envia todos os dados persistentes definidos no objeto de medição (listados na descrição para clearVars), além de qualquer contextData ou variáveis fornecidas apenas para esta chamada. Se você enviar uma variável definida, qualquer valor correspondente à variável persistente será substituído.

Sintaxe:

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

Exemplos:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**: Envia dados de link personalizados, de download ou de saída para os servidores de coleta de dados da Adobe, juntamente com quaisquer variáveis trackconfig com valores.

Use trackLink para rastrear todas as atividades que não devem capturar uma visualização da página.

Sintaxe:

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**: identifica o URL clicado. Se não houver URL especificado, o nome será utilizado. Use apenas ao vincular a uma página da Web pelo seu aplicativo Android. Caso contrário, coloque null neste parâmetro.

**linkType**: identifica o relatórios do link que mostrará o URL ou o nome. Os valores compatíveis incluem:
* “o” (links personalizados)
* “d” (downloads de arquivos)
* “e” (links de saída)

**linkName**: o nome que aparece no relatório de link. Se não houver um nome especificado, o relatório usará o URL.

Para coletar dados, você deve especificar o parâmetro linkURL ou linkName. Quando não estiver usando um desses parâmetros, contexto de dados ou variáveis adicionais, coloque null como valor.

Exemplos:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**: Define a eVar especificada para o valor fornecido. O eVar é enviado com todas as chamadas de rastreamento até que seja esvaziado ao ser enviado a uma sequência de caracteres vazia ou chamando a limpeza de vars.

Sintaxe:

`void setEvar(int evarNum, String evarValue)`

**setProp**: Define a prop especificada para o valor fornecido. O prop é enviado com todas as chamadas de rastreamento até que seja limpo ao ser enviado a uma sequência de caracteres vazia ou chamando a limpeza de vars.

Sintaxe:

`void setProp(int propNum, String propValue)`

**setHier**: Define a variável herdada especificada para o valor fornecido. A variável hier é enviada com todas as chamadas de rastreamento até que seja esvaziado ao ser enviado a uma sequência de caracteres vazia ou chamando a limpeza vars.

Sintaxe:

`void setHier(int hierNum, String hierValue)`

**setListVar**: Define a listVar especificada para o valor fornecido. A listVar com todas as chamadas de rastreamento até que seja esvaziado ao ser enviado a uma cadeia de caracteres vazia ou chamando a limpeza vars.

Sintaxe:

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**: Os valores inseridos em Dados de contexto persistentes são enviados com cada chamada de servidor. Para enviar dados de contexto para uma única chamada, envie uma tabela hash contextData como parâmetro para a chamada de rastreamento (trackAppState, trackEvents e assim por diante).

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

Consulte Dados de contexto.

**clearVars**: Remove valores das seguintes variáveis no objeto:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Sintaxe:

`void clearVars()`

Exemplos:
`measure.clearVars();`

**Rastreamento offline**

*Observação: para ativar o AppMeasurement offline, seu conjunto de relatórios deve estar com o registro de data e hora ativado.*

As variáveis a seguir permitem que você armazene chamadas de medição quando o aplicativo está offline. Para ativar o AppMeasurement offline, seu conjunto de relatórios deve estar com o registro de data e hora ativado. Depois dessa alteração, todas as ocorrências deverão ter o registro de data e hora ou serão descartadas. Caso esteja enviando atualmente um relatório de dados AppMeasurement para um conjunto de relatórios que também colete dados de JavaScript, poderá ser necessário definir um conjunto de relatórios separadamente para o AppMeasurement offline a fim de evitar perda de dados.

Quando ativado, o AppMeasurement offline se comporta da seguinte maneira:
* O aplicativo envia uma chamada de servidor, mas a transmissão de dados falha.
* O AppMeasurement gera um registro de data e hora para o hit atual.
* O AppMeasurement armazena os dados do hit em buffer e faz o backup dos dados de hits em buffer no armazenamento persistente para evitar a perda de dados.

Em cada hit subsequente ou no intervalo definido por offlineThrottleDelay, o AppMeasurement tenta enviar os dados de hits em buffer, mantendo a ordem de hits original. Caso a transmissão de dados falhe, a armazenagem de dados em buffer continuará (Enquanto o dispositivo estiver offline).

### Configuração de métodos

**setOfflineTrackingEnabled**: O padrão é falso. Ativa ou desativa o rastreamento offline para a biblioteca de medição.

Sintaxe:

`void setOfflineTrackingEnabled(boolean Enabled);`

Exemplos:
"measurement.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**: O padrão é 1000. O número máximo de ocorrências offline armazenada na fila. Se o limite de hits estiver definido acima de 5000, o desempenho poderá ser prejudicado.

Sintaxe:

`void setOfflineHitLimit(int offlineHitLimit)`

Exemplos:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**: Retorna o número de chamadas de rastreamento armazenadas na fila offline.

Sintaxe:

`int getTrackingQueueSize()`

Exemplos:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**: Remove todas as chamadas de rastreamento armazenadas da fila offline.

Sintaxe:

`void clearTrackingQueue()`

Exemplos:

`measure.clearTrackingQueue();`

**Aviso: tenha cuidado ao limpar a fila manualmente, pois o resultado não pode ser revertido.**


**setOnline e setOffline**: Defina manualmente o estado online ou offline do objeto de medição. A biblioteca detecta automaticamente quando um dispositivo está online ou offline. Estes métodos serão necessários apenas quando você quiser forçar a medição offline. SetOnline é usado apenas para voltar ao estado online após ter sido alterado manualmente para offline.

Quando a medição está offline:

* Se offlineTrackingEnabled for verdadeiro: as ocorrências são armazenadas até a medição estar online.
* Se offlineTrackingEnabled for falso: as ocorrências são descartadas.

Sintaxe:

```
void setOnline()
void setOffline()
```

Exemplos:

```
measure.setOffline();
measure.setOnline();
```

## Rastreamento offline

O AppMeasurement lhe permite medir o uso do aplicativo mesmo que o dispositivo Android esteja offline.

*Observação: para ativar o AppMeasurement offline, seu conjunto de relatórios deve estar com o registro de data e hora ativado.*

Consulte Rastreamento offline.

## Target

A Adobe proporciona a capacidade de fornecer conteúdo direcionado dentro de aplicativos Android.

O conteúdo retornado do Test&amp;Target pode ser qualquer conteúdo com base em texto, como HTML, XML ou texto sem formatação. Após o conteúdo ser carregado, passa a ser uma decisão do desenvolvedor de aplicativos Android como ele será acessado no aplicativo. O conteúdo pode ser exibido como HTML ou utilizado para modificar o comportamento do aplicativo. Este guia fornece um exemplo de simples utilização da classe Test&amp;Target.

Requisitos

* JDK 5/6/7
* SDK do Android para a Plataforma 1.5 ou posterior.

O exemplo desta seção é baseado no Eclipse.

**Obtenha a Biblioteca**

Visite Medição e otimização de aplicativos móveis no Developer Connection para fazer o download da biblioteca do Android.

Após descompactar o arquivo, você terá os seguintes componentes de software:

* admsAppLibrary.jar: a biblioteca projetada para o uso com dispositivos e simuladores Android. Requer Android 2.0 ou posterior.
* Examples\TrackingHelper.java: classe opcional que é designada para manter o código de rastreamento separado do seu aplicativo lógico.

**Adicionar a biblioteca ao seu projeto**

1. No Eclipse IDE, clique com o botão direito do mouse no nome do projeto.
1. Selecione Caminho de criação &gt; Adicionar arquivos externos.
1. Selecione admsAppLibrary.jar.
1. Clique em Abrir.
1. Clique novamente no projeto com o botão direito do mouse e selecione Build Path (Caminho de criação) &gt; Configure Build Path (Configurar caminho de criação).
1. Clique na guia Order and Export (Solicitar e exportar).
1. Certifique-se de que admsAppLibrary.jar está selecionado.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using `importcom.adobe.ADMS.*;`

**Adicionar permissões do aplicativo**

A biblioteca do AppMeasurement pede as seguintes permissões para enviar dados e gravar chamadas de rastreamento offline:

* INTERNET
* ACCESS_NETWORK_STATE

Para adicionar essas permissões, adicione as seguintes linhas para o seu arquivo AndroidManifest.xml (no diretório do projeto do aplicativo):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Exemplo

Após adicionar a biblioteca ao seu projeto e incluir as permissões de aplicativo, você pode usar as duas classes Test&amp;Target, MboxFactory e Mbox.

O seguinte exemplo mostra como carregar conteúdo HTML do Test&amp;Target em um WebView em um único aplicativo do Android. Este exemplo supõe que a oferta e a campanha do HTML associado já tenha sido criada na Ferramenta de administração Test&amp;Target e que a campanha foi aprovada.

1. Complete as etapas em Implementação, em seguida, importe o pacote testandtarget no tipo da subclasse do Aplicativo ou da Atividade:

   `com.adobe.adms.testandtarget.*;`

2. Siga o código numerado abaixo para criar um mbox (confira os comentários para obter mais explicações a respeito de cada linha de código). Para completar esta etapa você precisará conhecer o código de seu cliente e o nome do mbox usado na configuração da campanha na Ferramenta de Administração Test&amp;Target.

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. Define a classe personalizada que implementa a interface MboxContentConsumer. Essa interface abstrata exige apenas que você defina um método chamado de “consume” para passar o conteúdo. A classe CustomConsumer definida abaixo exibe apenas o conteúdo em um WebView.

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. Clique com o botão direito em seu projeto e selecione Run As (Abrir como) &gt; Android Application (Aplicativo Android) para criar e testar seu aplicativo. Se tiver estruturado e aprovado sua campanha Test&amp;Target corretamente, você verá sua oferta exibida no emulador de dispositivo Android.

**Medições de ciclo de vida**

Se as medições de ciclo de vida estiverem ativadas, elas serão enviadas como parâmetros para cada mbox carregado.

* (Recomendado) Rastrear eventos de ciclo de vida
* Medições de ciclo de vida

## Gerenciamento de público-alvo

A Adobe proporciona a capacidade de enviar sinais e recuperar segmentos de visitantes a partir do gerenciamento de público-alvo.

### Requisitos

* JDK 5/6/7
* SDK do Android para a Plataforma 1.5 ou posterior.

O exemplo desta seção é baseado no Eclipse.

### Obtenha a Biblioteca

Visite Medição e otimização de aplicativos móveis no Developer Connection para fazer o download da biblioteca do Android.

Após descompactar o arquivo, você terá os seguintes componentes de software:

* admsAppLibrary.jar: a biblioteca projetada para o uso com dispositivos e simuladores Android. Requer Android 2.0 ou posterior.
* Examples\TrackingHelper.java: classe opcional que é designada para manter o código de rastreamento separado do seu aplicativo lógico.

### Adicionar a biblioteca ao seu projeto

1. No Eclipse IDE, clique com o botão direito do mouse no nome do projeto.
1. Selecione Caminho de criação &gt; Adicionar arquivos externos.
1. Selecione admsAppLibrary.jar.
1. Clique em Abrir.
1. Clique novamente no projeto com o botão direito do mouse e selecione Build Path (Caminho de criação) &gt; Configure Build Path (Configurar caminho de criação).
1. Clique na guia Order and Export (Solicitar e exportar).
1. Certifique-se de que admsAppLibrary.jar está selecionado.

Your application can import the classes/interfaces from the admsAppLibrary.jar library by using `importcom.adobe.ADMS.*;`

### Adicionar permissões do aplicativo

A biblioteca do AppMeasurement pede as seguintes permissões para enviar dados e gravar chamadas de rastreamento offline:
* INTERNET
* ACCESS_NETWORK_STATE

Para adicionar essas permissões, adicione as seguintes linhas para o seu arquivo AndroidManifest.xml (no diretório do projeto do aplicativo):

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Amostra de código

Depois de adicionar a biblioteca ao seu projeto, será possível usar a classe ADMS_AudienceManager. To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. Configure o gerenciamento de público-alvo:

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   Substitua mycompany.demdex.net pelo seu endpoint. O gerenciamento de público-alvo pode ser configurado em qualquer ponto no seu aplicativo.


2. Opcionalmente, defina dpid e dpuuid.

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. Crie um dicionário de características e o envie em um sinal.

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

O dicionário do perfil do visitante é retornado como o parâmetro content.

### Medições de ciclo de vida

Se as medições de ciclo de vida estiverem ativadas e o gerenciamento de público-alvo estiver configurado em application:didFinishLaunchingWithOptions:, um sinal contendo as medições de ciclo de vida será enviado após a conclusão da configuração.

* (Recomendado) Rastrear eventos de ciclo de vida
* Medições de ciclo de vida

### Referência ADMS_AudienceManager

**Métodos**

**ConfigureAudienceManager**: Define o terminal de gerenciamento de público-alvo.

Sintaxe:

`public static void ConfigureAudienceManager(String server, Context context);`

Exemplo:

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**: Retorna um booliano que indica se os métodos do Audience Manager fornecerão log de depuração no seu console.

Sintaxe:

`public static boolean GetDebugLogging();`

**GetDpid**: Retorna a dpid.

Sintaxe:

`public static String GetDpid();`

**GetDpuuid**: Retorna dpuuid.

Sintaxe:

`public static String GetDpuuid();`

**GetVisitorProfile**: Esse método pode ser chamado a qualquer momento depois de enviar um sinal para recuperar o perfil de visitante mais recente.

O perfil do visitante contém todos os pares de valores chave que foram retornados no objeto stuff.

Sintaxe:

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**: Ativa ou desativa o registro de depuração no console.

Sintaxe:

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**: Se newDpid e newDpuuid estiverem definidas, elas serão enviadas com cada sinal.

Sintaxe:

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**: Envia um dicionário de características e recebe o perfil de visitante atualizado no retorno de chamada.

O uuid da resposta JSON é armazenado internamente e é usado com todos os sinais subsequentes. Uma solicitação de pixel também é enviada para cada URL encontrado no objeto dests.

Sintaxe:

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### Interfaces

**Métodos**


**AudienceManagerCallback**

Sintaxe:

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

Interface para o objeto usado no retorno da chamada SubmitSignal.


## Plug-in PhoneGap

Este plug-in permite que você envie chamadas do Android AppMeasurement do seu projeto PhoneGap.

Para ajudar a criar um projeto PhoneGap, consulte Introdução do PhoneGap ao Android.

Para fazer o download do plug-in, consulte Plug-ins PhoneGap de iOS e Android para o SiteCatalyst.

### Incluir o plug-in

1. Copie ADMS_plugin.java para o pacote na sua pasta src.
2. Copie ADMS_Helper.js para a pasta assets/www/js no seu projeto do PhoneGap.
3. Na pasta res/xml, abra o arquivo config.xml e registre um novo plug-in ao criar um novo nó pai em plug-ins: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

Por exemplo, se o seu pacote for chamado de com.example.phonegaptest, então o nó de plug-in seria: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### Inclua a biblioteca do AppMeasurement

Para fazer o download da biblioteca do AppMeasurement, consulte Obtenha a biblioteca.

1. Copie admsAppLibrary.jar para a pasta libs no seu projeto do PhoneGap.
2. Verifique se admsAppLibrary.jar está no caminho de compilação ao clicar com o botão direito do mouse em libs &gt; Caminho de compilação &gt; Configurar caminho de compilação.
3. Na guia Bibliotecas, se ainda não estiver na lista, clique em Adicionar JARs e selecione admsAppLibrary.jar na pasta libs.


### Rastreamento automático de medições de ciclo de vida

O rastreamento das Medições de ciclo de vida requer configuração fora do PhoneGap. Para ativar o rastreamento automático do ciclo de vida, complete as etapas de Implementação no Início rápido do desenvolvedor.

### Usar o Plug-in

Nos arquivos html onde você deseja usar rastreamento, inclua:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

Pronto. Agora você pode fazer chamadas de medição. Consulte Métodos de plug-in do PhoneGap.

### Solução de problemas

**Minha sintaxe está correta. Por que o código no plug-in não está sendo alcançado?**

Verifique se este erro aparece no console de saída: `java.lang.ClassNotFoundException: ADMS_plugin`

Se esse erro ocorrer, verifique se você executou a etapa 3 na seção Incluir o plug-in.

## Métodos do plug-in PhoneGap

Nos arquivos html onde você deseja usar esses métodos, inclua:

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**Configuração de métodos**


**configureMeasurementWithReportSuiteIDsTrackingServer**: Este método é usado para configurar os dois parâmetros necessários para iniciar a medição do aplicativo. Você deve definir os valores de reportSuiteIDs e trackingServer no objeto de medição usando este método antes de enviar qualquer chamada de servidor.

Sintaxe:

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

Exemplo:

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnline e setOffline**: Defina manualmente o estado online ou offline do objeto de medição. A biblioteca detecta automaticamente quando um dispositivo está online ou offline. Estes métodos serão necessários apenas quando você quiser forçar a medição offline. SetOnline é usado apenas para voltar ao estado online após ter sido alterado manualmente para offline.

Quando a medição está offline:

* Se offlineTrackingEnabled for verdadeiro: as ocorrências são armazenadas até a medição estar online.
* Se offlineTrackingEnabled for falso: as ocorrências são descartadas.

Sintaxe:

```
void setOnline();
void setOffline();
```

Exemplo:

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**: Ativa (true) ou desativa (false) a exibição de informações de depuração. O padrão desta variável é false.

Você não pode substituir esta variável usando substituições de variável.

Sintaxe:

`void setDebugLogging(bool debugLogging);`

Exemplo:

`ADMS.setDebugLogging(true);`

### Métodos de rastreamento de evento e estado


**trackAppState**: Essa é a maneira recomendada de rastrear os estados do aplicativo (por exemplo, páginas) no aplicativo. O valor fornecido em appState aparece como a variável do nome da página da chamada do servidor. A sequência de caracteres appState deve ser fornecida para cada chamada desde que não seja transportada para a próxima chamada.

Sintaxe:

`void trackAppState(string stateName);`

Exemplo:

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**: Essa é a maneira recomendada de rastrear os estados do aplicativo (por exemplo, páginas) no aplicativo. O valor fornecido em appState aparece como a variável do nome da página da chamada do servidor. A sequência de caracteres appState deve ser fornecida para cada chamada desde que não seja transportada para a próxima chamada.

Os dados de contexto enviados com esta chamada são anexados a qualquer valor em persistentContextData e enviados com a chamada. Apenas os valores definidos em persistentContextData permanecem para a próxima chamada.

Sintaxe:

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData: objeto JSON com pares de valor chave para enviar dados de contexto.

Exemplo:

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**: Essa é a maneira recomendada para rastrear eventos em seu aplicativo. trackEvents é semelhante a trackAppState, mas envia eventos em vez de nomes de páginas. Os eventos são fornecidos como uma string delimitada por trackEvents por vírgulas. A sequência de caracteres de events deve ser fornecida para cada chamada, pois não é transportada para a próxima chamada.

Este método efetua uma chamada subjacente para trackLinkURL, onde linkURL está definido como nulo, linkType está definido como "o" e linkName é preenchido com a ID do aplicativo.

Isso significa que linkTrackVars e linkTrackEvents se aplicam a chamadas para `trackEvents`.

Sintaxe:

`void trackEvents(string eventNames);`

Exemplo:

`ADMS.trackEvents("login,event2");`

**Importe a nota se estiver usando o método trackLink**

`trackEvents` efetua uma chamada subjacente para trackLinkURL, onde linkURL está definido como null, linkType está definido como "o" e linkName é preenchido com a ID do aplicativo. Isso é realizado para impedir que a contagem de visualização de página (visualização de estado) seja aumentada sempre que você rastrear eventos.

Se estiver chamando trackLinkURL diretamente e definindo valores para linkTrackVars e linkTrackEvents, essas restrições de variável e evento se aplicam a TrackEvents. Isso significa que apenas as variáveis e os eventos definidos nessas listas serão enviados com o TrackEvents. É necessário definir linkTrackVars e linkTrackEvents como nulo a não ser que você deseja que as restrições sejam aplicadas a trackEvents.

**trackEventsWithContextData**: Essa é a maneira recomendada para rastrear eventos em seu aplicativo. trackEvents é semelhante a trackAppState, mas envia eventos em vez de nomes de páginas. Os eventos são fornecidos como uma sequência de caracteres delimitada por vírgulas. A sequência de caracteres de events deve ser fornecida para cada chamada, pois não é transportada para a próxima chamada.

Este método efetua uma chamada subjacente para trackLinkURL, onde linkURL está definido como null, linkType está definido como "o" e linkName é preenchido com a ID do aplicativo.

Isso significa que linkTrackVars e linkTrackEvents se aplicam a chamadas para trackEvents.

Os dados de contexto enviados com esta chamada são anexados a qualquer valor em persistentContextData e enviados com a chamada. Apenas os valores definidos em persistentContextData permanecem para a próxima chamada.

Sintaxe:

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData: objeto JSON com pares de valor chave para enviar dados de contexto.

Exemplo:

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**Importe a nota se estiver usando o método trackLink**

trackEvents efetua uma chamada subjacente para trackLinkURL, onde linkURL está definido como null, linkType está definido como "o" e linkName é preenchido com a ID do aplicativo. Isso é realizado para impedir que a contagem de visualização de página (visualização de estado) seja aumentada sempre que você rastrear eventos.

Se estiver chamando trackLinkURL diretamente e definindo valores para linkTrackVars e linkTrackEvents, essas restrições de variável e evento se aplicam a TrackEvents. Isso significa que apenas as variáveis e os eventos definidos nessas listas serão enviados com o TrackEvents. É necessário definir linkTrackVars e linkTrackEvents como nulo a não ser que você deseja que as restrições sejam aplicadas a trackEvents.

**Métodos de rastreamento avançados (track e trackLink)**

Esses métodos fornecem opções adicionais de rastreamento e permitem que você preencha diretamente props, eVars e outras variáveis do SiteCatalyst. Eles devem ser usados por clientes com uma implementação existente ou com clientes familiarizados com outras implementações do SiteCatalyst.

`track` e `trackLink` são os métodos principais de medição que são implementados em todas as versões das bibliotecas de medição da Adobe em várias plataformas. Em sua maioria, ao rastrear aplicativos móveis, é mais fácil usar os métodos trackAppState e trackEvents do que chamar o rastreamento e trackLink diretamente.

O rastreamento de visualização de página (track) e de link (trackLink) envia todas as variáveis persistentes que têm valores que não sejam nulos, vazios ou zero. Você deve reiniciar ou esvaziar todas as variáveis, conforme necessário, antes de chamar track ou trackLink.

**Métodos**

**faixa**: Envia uma exibição de página padrão, juntamente com quaisquer variáveis adicionais definidas no objeto de medição, para o servidor de coleção.

Sintaxe:

`void track();`

Exemplo:

`ADMS.track();`

**trackWithContextData**: Envia uma exibição de página padrão, juntamente com quaisquer variáveis adicionais definidas no objeto de medição, para o servidor de coleção.

Cada chamada para trackWithContextData envia todos os dados persistentes definidos no objeto de medição (listados na descrição para clearVars), além de qualquer contextData fornecido apenas para essa chamada.

Sintaxe:

`void trackWithContextData(JSON cData);`

cData: objeto JSON com pares de valor chave para enviar dados de contexto.

Exemplo:

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**: Envia uma exibição de página padrão, juntamente com quaisquer variáveis adicionais definidas no objeto de medição, para o servidor de coleção.

Cada chamada para trackWithContextDataAndVariables envia todos os dados persistentes definidos no objeto de medição (listados na descrição para clearVars), além de qualquer contextData e variáveis fornecidas apenas para essa chamada. Se você enviar uma variável definida, qualquer valor correspondente à variável persistente será substituído.

Sintaxe:

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData: objeto JSON com pares de valor chave para enviar dados de contexto.

Exemplo:

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**: Envia dados de link personalizados, de download ou de saída para os servidores de coleta de dados da Adobe, juntamente com qualquer variável de configuração de rastreamento que tenha valores.

Use trackLink para rastrear todas as atividades que não devem capturar uma visualização da página.

Cada chamada para trackLinkURLWithLinkTypeNameContextDataVariables envia todos os dados persistentes definidos no objeto de medição (listados na descrição para clearVars), além de qualquer contextData fornecido apenas para essa chamada.

Sintaxe:

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData: objeto JSON com pares de valor chave para enviar dados de contexto.

Exemplo:

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### Definir e obter variáveis de AppMeasurement

**Métodos**

**setEvarToValue**: Define a eVar especificada para o valor fornecido. O eVar é enviado junto com a próxima chamada de rastreamento.

Sintaxe:

`void setEvarToValue(int evar, string value);`

Exemplo:

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**: Define a prop especificada para o valor fornecido. O prop é enviado junto com a próxima chamada de rastreamento.

Sintaxe:

void setPropToValue(int prop, valor de string);

Exemplo:

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**: Define a variável hier especificada para o valor fornecido. A variável é enviada junto com a próxima chamada de rastreamento.

Sintaxe:

`void setHierToValue(int hier, string value);`

Exemplo:

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**: Define a listvar especificada para o valor fornecido. A listvar é enviada junto com a próxima chamada de rastreamento.

Sintaxe:

`void setListVarToValue(int list, string value);`

Exemplo:

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**: Obtém a variável especificada.

Sintaxe:

`void getEvar(int evar, function success, function fail);`

Exemplo:

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**: Obtém a variável especificada.

Sintaxe:

`void getProp(int prop, function success, function fail);`

Exemplo:

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**: Obtém a variável especificada.

Sintaxe:

`void getHier(int hier, function success, function fail);`

Exemplo:

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**: Obtém a variável especificada.

Sintaxe:

`void getListVar(int list, function success, function fail);`

Exemplo:

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**: Remove valores das seguintes variáveis no objeto:

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

Sintaxe:

`void clearVars();`

Exemplo:

`ADMS.clearVars();`

**trackingQueueSize**: Obtém ou define o número de chamadas de rastreamento armazenadas na fila offline.

Sintaxe:

`void trackingQueueSize(function success, function fail);`

Exemplo:

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**: Remove todas as chamadas de rastreamento armazenadas da fila offline. Aviso: cuidado ao limpar a fila manualmente, pois o resultado não pode ser revertido.

Sintaxe:

`void clearTrackingQueue();`

Exemplo:

`ADMS.clearTrackingQueue();`

### Definir e obter variáveis de configuração

**Métodos**

**getVersion**: Obtém a versão da biblioteca.

Sintaxe:

`void getVersion(function success, function fail);`

Exemplo:

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**: (Obrigatório) O conjunto de relatórios ou os conjuntos de relatórios (marcação de vários relatórios) que você deseja rastrear. Para rastrear vários conjuntos de relatórios, passe uma lista delimitada por vírgula dos nomes de cada conjunto de relatórios.

Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:
`void setReportSuiteIDs(string reportSuiteIDs);`

Exemplo:

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**: (Obrigatório) Identifica o servidor de coleta.

Essa variável deve ser preenchida com o valor gerado para você no Code Manager.

O mesmo valor é usado para garantir o rastreamento seguro, caso ssl esteja ativo.

Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:

`void setTrackingServer(string trackingServer);`

Exemplo:

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

Sintaxe:

`void setDataCenter(string dataCenter);`

Exemplo:

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**: O padrão é CFUUID.

Identificador único para cada visitante. Se você não definir um visitorID personalizado, um visitorID único será gerado (usando o CFUUID da Apple) na primeira inicialização e armazenado em uma chave de padrões do usuário. Essa chave será usada pelo AppMeasurement e PhoneGap desse ponto em diante. Essa tecla também é salva e restaurada durante o processo de backup padrão do aplicativo.

Sintaxe:

`void setVisitorID(string visitorId);`

Exemplo:

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**: O padrão é UTF-8.

Sintaxe:

`void setCharSet(string charSet);`

Exemplo:

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**: O padrão é nenhum (o valor definido para o conjunto de relatórios é usado).

O código da moeda utilizado para eventos de compras ou moeda que são rastreados no aplicativo iOS.

Sintaxe:

`void setCurrencyCode(string currencyCode);`

Exemplo:

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**: O padrão é falso.

Habilita (true) ou desabilita (false) o envio de dados de medição via SSL (HTTPS). Você não pode substituir essa variável por uma chamada única, é preciso alterar o valor persistente.

Sintaxe:

`void setSSLEnabled(bool sslEnabled);`

Exemplo:

`ADMS.setSSLEnabled(false);`

### Definir e obter variáveis de rastreamento persistente

**Métodos**

**setPurchaseID**:

Sintaxe:

`void setPurchaseID(string purchaseId);`

Exemplo:

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

Sintaxe:

`void setTransactionID(string transactionId);`

Exemplo:

`ADMS.setTransactionID("transaction1");`

**setAppState**:

Sintaxe:

`void setAppState(string stateName);`

Exemplo:

`ADMS.setAppState("myAppState");`

**setChannel**:

Sintaxe:

`void setChannel(string channel);`

Exemplo:

`ADMS.setChannel("myChannel");`

**setAppSection**:

Sintaxe:

`void setAppSection(string appSection);`

Exemplo:

`DMS.setAppSection("myAppSection");`

**setCampaign**:

Sintaxe:

`void setCampaign(string campaign);`

Exemplo:

`ADMS.setCampaign("myCampaign");`

**setProducts**:

Sintaxe:

`void setProducts(string products);`

Exemplo:

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

Sintaxe:

`void setEvents(string events);`

Exemplo:

`ADMS.setEvents("event1, event2");`

**setGeoState**

Sintaxe:

`void setGeoState(string state);`

Exemplo:

`ADMS.setGeoState("FL");`

**setGeoZip**:

Sintaxe:

`void setGeoZip(string zip);`

Exemplo:

`ADMS.setGeoZip("39984");`

**setPersistentContextData**: Dados de contexto são a maneira recomendada para coletar dados. Para enviar dados de contexto crie um objeto JSON e atribua pares de valores chave aos valores que você deseja enviar.

Sintaxe:

`void setPersistentContextData(JSON cData);`

Exemplo:

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

Sintaxe:

`void persistentContextData(function success, function fail);`

Exemplo:

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**: Uma lista de nomes de variáveis delimitada por vírgulas que restringe o conjunto atual de variáveis para o rastreamento de links.

Se linkTrackVars não estiver definido, o plug-in PhoneGap envia todas as variáveis com uma chamada trackLink.

Sintaxe:

`void setLinkTrackVars(string linkTrackVars);`

Exemplo:

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**: Uma lista de eventos delimitada por vírgulas que restringe o conjunto atual de eventos para rastreamento de links. Se linkTrackEvents não estiver definido, o plug-in PhoneGap envia todos os eventos com uma chamada trackLink.

Sintaxe:

`void setLinkTrackEvents(string linkTrackEvents);`

Exemplo:

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**: Uma lista de variáveis delimitada por vírgulas que restringe o conjunto atual de variáveis para chamadas de rastreamento leve. Essas variáveis que você enviou com uma chamada de servidor leve são configuradas pelo ClientCare.

Sintaxe:

`void setLightTrackVars(string lightTrackVars);`

Exemplo:

`ADMS.setLightTrackVars("prop1,hier3");`

### Rastreamento offline

**Métodos**

**setOfflineTrackingEnabled**:

Sintaxe:

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

Exemplo:

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

Sintaxe:

`void setOfflineHitLimit(int offlineHitLimit);`

Exemplo:

`ADMS.setOfflineHitLimit(3000);`

## Guia de migração do Android versão 2.x a 3.x

* AppMeasurement agora é ADMS_Measurement. Encontre locais onde você faz referência a essa classe e atualize o nome para ADMS_Measurement.
* getInstance agora é sharedInstance. Procure locais onde você chama getInstance e substitua por sharedInstance.
* Remoa todas as chamadas para medição de taxa (getChurnInstance). Estas chamadas são feitas por rastreamento automático e as variáveis agora são inseridas utilizando os dados de contexto.
* Timestamp é removido. A biblioteca trata automaticamente os registros de hora e data.

A sintaxe para os métodos seguintes foram alteradas. Exemplos atualizados para todas as propriedades e métodos estão disponíveis em Variáveis e métodos de configuração.


### Conjunto de relatórios

**Versão anterior (2.1.x)**

`account`

**Nova versão (3.x)**

`reportSuiteIDs`

### Track

**Versão anterior (2.1.x)**


`String track()`

`String track(Hashtable variableOverrides)`

**Nova versão (3.x)**

Enviar null para valores não usados.

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### Track Link

**Versão anterior (2.1.x)**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**Nova versão (3.x)**

Estas duas chamadas foram substituídas com uma chamada única. Enviar null para valores não usados.

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### Métodos de rastreamento offline

**Versão anterior (2.1.x)**

`void forceOffline();`


`void forceOnline();`

**Nova versão (3.x)**

`void setOnline();`

`void setOffline();`


### Variáveis renomeadas

A seguinte lista mostra as variáveis da versão 2.x com seus valores correspondentes na versão 3.x. Várias variáveis foram removidas da versão 3.x para aumentar o foco móvel da biblioteca e para simplificar a implementação.


*Observação: a versão 3.x usa getters e setters em vez de variáveis públicas. Você precisará atualizar locais no seu código onde você define variáveis diretamente para usar os métodos get e set.*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## Usar o Bloodhound para testar aplicativos móveis

A ferramenta Bloodhound permite que você envie chamas de servidor para um computador local a fim de testar aplicativos móveis.

*Importante: a partir de 30 de abril de 2017, o Adobe Bloodhound foi interrompido. A partir de 1º de maio de 2017, não serão fornecidos aprimoramentos e suporte adicionais pela engenharia ou pelo Adobe Expert Care.*

Durante o desenvolvimento do aplicativo, o Bloodhound permite exibir localmente chamadas de servidor e, como opção, encaminhar os dados para os servidores de coleta da Adobe.

O Bloodhound está disponível para Mac e Windows.

### Requisitos

* Um computador Mac com base Intel executando o Snow Leopard (10.6) ou posterior ou um PC com Windows.
* Conexão de rede aos seus dispositivos móveis ou simuladores.

### Baixar

Consulte Bloodhound - Ferramenta de QA de medição de aplicativo no Developer Connection.

### Instalação

* Mac: abra o dmg baixado e arraste o Bloodhound até a pasta Aplicativos.
* Windows: execute o arquivo de instalação baixado .

### Usar o Bloodhound

Depois de iniciar a ferramenta, o servidor é desativado até você clicar no botão Iniciar. Clique no botão Iniciar quando estiver pronto para capturar chamadas de servidor de seu aplicativo.

Como opção, você pode especificar um número de porta personalizado (deve ser acima de 1024) antes de iniciar o servidor. Se você não fornecer um número de porta, o servidor seleciona automaticamente uma porta aberta.

Depois que o servidor estiver funcionando, você precisará configurar seus aplicativos ou dispositivos para enviar dados para a ferramenta, como discutido na próxima seção.

### Configurar dispositivos para enviarem ocorrências ao Bloodhound

Você pode alterar configurações de proxy no dispositivo para que enviem solicitações de http para a ferramenta. Como opção, as solicitações enviada para a ferramenta podem ser encaminhadas para os servidores de coleta de dados da Adobe.

Se o seu dispositivo não suporta um proxy, é possível enviar as ocorrências diretamente para o bloodhound para testes.

*Observação: o Bloodhound não suporta o rastreamento por SSL. Você deve desativar SSL na biblioteca do AppMeasurement ao testar a utilização do Bloodhound.*

#### Dispositivos iOS

O dispositivo iOS deve estar na mesma rede que o computador hospedando o Bloodhound.

1. Navegue até Configurações &gt; Wi-Fi.
1. Clique na seta azul à direita da rede Wi-Fi atual.
1. Role até configuração de Proxy HTTP.
1. Selecione Automático.
1. Insira o URL e a porta do proxy (na interface do usuário do Bloodhound) no campo URL.

#### Outros dispositivos

Se o dispositivo suporta a configuração automática de proxy, use o URL de proxy (na interface do usuário do Bloodhound) como o URL de configuração automática de proxy (PAC). O suporte de proxy varia na versões do Android e há ferramentas de configuração de proxy disponíveis para que o Android simplifique a configuração.

### Enviar ocorrências diretamente

Para dispositivos que não suportam proxy (Simulador de iOS, versões anteriores do Android etc.) é possível usar o Bloodhound como servidor de rastreamento para capturar as ocorrências geradas. Para fazer isso, configure seu servidor de rastreamento como "<Bloodhound IP>:<BloodhoundPort>".

Por exemplo:

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### Soluções de problemas/problemas comuns

* O Bloodhound funciona apenas com rastreamento não-ssl. Quaisquer ocorrências de rastreamento enviadas por SSL não são capturadas, independentemente do método usado acima.

## Widgets do Android

Os widgets do Android podem ser monitorados usando os mesmos métodos do seu aplicativo. Os widgets compartilham o contexto do aplicativo com o app, de forma que o pedido de hit e a identificação de visitantes são preservados.

As diretrizes a seguir ajudarão você a monitorar os widgets do Android:

* Não implante chamadas de medições de ciclo de vida (startActivity/stopActivity) no próprio widget.
* Para monitorar quando um widget é adicionado à página inicial, adicione uma chamada trackState ou trackEvent ao método onEnabled do widget.
* Para monitorar quando o aplicativo é iniciado a partir de um widget, adicione uma chamada trackState ou trackEvent antes de iniciar o seu aplicativo.
* Se estiver interessado em monitorar o contexto de uma ação, você pode definir uma variável ContextData que fornece a opção de segmentar cada um separadamente (por exemplo, AppExperienceType="widget" vs. "app").
