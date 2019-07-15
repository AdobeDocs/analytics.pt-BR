---
description: É possível rastrear automaticamente os downloads de arquivo e links de saída com base nos parâmetros definidos no arquivo AppMeasurement para JavaScript.
keywords: Implementação do Analytics
seo-description: É possível rastrear automaticamente os downloads de arquivo e links de saída com base nos parâmetros definidos no arquivo AppMeasurement para JavaScript.
seo-title: A função s.tl() - Rastreamento de link
solution: Analytics
subtopic: Rastreamento de link
title: A função s.tl() - Rastreamento de link
topic: Desenvolvedor e implementação
uuid: f 28 f 071 a -8820-4 f 74-89 cd-fd 2333 a 21 f 22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# A função s.tl() - Rastreamento de link

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## A função s.tl() - Rastreamento de link {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

Se necessário, esses tipos de links podem ser acompanhados manualmente usando código de link personalizado, como explicado abaixo. Além disso, o código de link personalizado pode ser usado para monitorar links personalizados genéricos que podem ser usados para diversas necessidades de rastreamento e relatórios.

## s.tl() Referência de parâmetro {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

O primeiro argumento deve ser sempre definido como this (padrão) ou true. O argumento se refere ao objeto que está sendo clicado. Quando definido como &quot;this&quot;, ele se refere à propriedade HREF do link.

Se você estiver implementando o rastreamento de links em um objeto sem propriedade HREF, você deve sempre definir este argumento como &quot;this&quot;.

Como clicar em um link muitas vezes leva um visitante para fora da página atual, um atraso de 500 ms é usado para assegurar que uma solicitação de imagem seja enviada para a Adobe antes de o usuário deixar a página. Esse atraso só será necessário na saída da página, mas geralmente ocorre quando a função s.t() é chamada. Se você desejar desativar o atraso, passe a palavra-chave &quot;true&quot; como o primeiro parâmetro ao chamar a função s.t().

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

linkType tem três valores positivos, dependendo do tipo de link que você queira capturar. Se o link não for de download ou saída, você deverá escolher a opção de links Personalizados.

| Tipo | valor linkType |
|--- |--- |
| Downloads de arquivos | &#39;d&#39; |
| Links de saída | &#39;e&#39; |
| Links personalizados | &#39;o&#39; |

**linkName**

Pode ser qualquer valor personalizado, até 100 caracteres. Determina como o link é exibido no relatório apropriado.

**variableOverrides**

(Opcional, transmitido como nulo se não for usado) Permite alterar os valores de variável para esta única chamada. É semelhante a outras bibliotecas [!DNL AppMeasurement].

**useForcedLinkTracking**

Esse sinalizador é usado para desativar o rastreamento forçado de link para alguns navegadores. O rastreamento forçado de links é ativado por padrão para os navegadores FireFox 20 e posteriores, e WebKit.

Valor padrão = verdadeiro

Exemplo: `s.useForcedLinkTracking& = false`

**forcedLinkTrackingTimeout**

O número máximo de milissegundos a fim de aguardar a conclusão do rastreamento antes de executar doneAction que foi passado para `s.tl`. Esse valor especifica o tempo máximo de espera. Se a chamada de link de rastreamento for concluída antes do tempo limite, doneAction será executado imediatamente. Se você perceber que as chamadas de link de rastreamento não estão sendo concluídas, talvez precise aumentar esse tempo limite.

Valor padrão = 250

Exemplo: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**doneAction**

Um parâmetro opcional para especificar uma ação de navegação para executar depois que a chamada de rastreamento de link for concluída quando useForcedLinkTracking estiver ativada.

Sintaxe:

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

doneAction: (opcional) Especifica a ação que deve ser tomada depois que a chamada de rastreamento de link é enviada ou atinge o tempo limite com base no valor especificado por:

`s.forcedLinkTrackingTimeout`

A variável doneAction pode ser a navegação da string, o que resulta na definição do método `document.location` como atributo href de linkObject . A variável doneAction também pode ser uma função que permite a personalização avançada.

Se você fornecer um valor para doneAction em um evento onClick de âncora, deverá retornar false depois da chamada de `s.tl` para impedir a navegação padrão do navegador.

Para refletir o comportamento padrão e seguir a URL especificada pelo atributo href, forneça uma string de &quot;navegação&quot; como doneAction.

Como opção, você pode fornecer sua própria função para lidar com o evento de navegação ao passar essa função como doneAction .

Exemplos:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**Exemplo**

O exemplo a seguir de uma função [!UICONTROL s.tl()] usa o atraso padrão de 500 ms para garantir a coleta dos dados antes de sair da página.

```js
s.tl(this,'o','link name');
```

O exemplo a seguir desativa o atraso de 500 ms, se o usuário não for sair da página ou sempre que o objeto clicado não tiver HREF.

```js
s.tl(true,'o','link name');
```

O atraso de 500 ms é o tempo máximo de atraso. Se a imagem solicitada for retornada em menos de 500 ms, o atraso será interrompido imediatamente. Isso permite ao visitante passar para a próxima página ou próxima ação na página.

Os exemplos a seguir se destinam à manipulação de links personalizados nos navegadores WebKit:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>Os usos do código de link personalizado são geralmente muito específicos para suas necessidades de site e relatórios. Você pode entrar em contato com o Consultor da Adobe ou Atendimento ao cliente antes de implementar o código de link personalizado para entender as possibilidades disponíveis e como aproveitar esse recurso com base em suas necessidades de negócios.

O código básico para monitorar um link usando o código de link personalizado é mostrado no exemplo a seguir:

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>The [!UICONTROL s_gi] function must contain your report suite ID as a function parameter. Certifique-se de trocar o [!DNL rsid] para sua ID exclusiva do conjunto de relatórios.

>[!NOTE]
>
>Se o parâmetro do nome do link não estiver definido, a URL do link (determinada pelo objeto &quot;this&quot;) será usada como o nome do link.

As variáveis do [!DNL Analytics] podem ser definidas como parte de um código de link personalizado.

## Acompanhamento automático de links de saída e downloads de arquivos {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

O arquivo JavaScript pode ser configurado para monitorar automaticamente os downloads de arquivos e links de saída com base nos parâmetros que definem os tipos de arquivo de download de arquivos e links de saída.

<!-- 

link_automatic.xml

 -->

Os parâmetros que controlam o rastreamento automático são desta forma:

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Os parâmetros *`trackDownloadLinks`* e *`trackExternalLinks`* determinar se o rastreamento automático de download de arquivo e link de saída está ativado. When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Exemplo 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. When *`linkLeaveQueryString`*=false, exit links are determined using only the domain, path, and file portion of the link URL. When *`linkLeaveQueryString`*=true, the query string portion of the link URL is also used to determine an exit link.

## Exemplo 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

Com as configurações a seguir, o exemplo abaixo será computado como um link de saída:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## Exemplo 3 {#section_2A78D05162D640169844A7D1E9799BAA}

Com as configurações a seguir, o link abaixo não será computado como um link de saída:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>Um único link pode ser rastreado somente como um download de arquivo ou link de saída, com prioridade para o download de arquivo. If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. A tabela a seguir resume o rastreamento automático de downloads de arquivos e links de saída.

## Acompanhamento manual de link usando código de link personalizado {#concept_7113B5D037BE4622B6934554C6D18F96}

O código de link personalizado permite que downloads de arquivos, links de saída e links personalizados sejam controlados em situações em que o rastreamento automático não é suficiente ou aplicável.

<!-- 

link_manual.xml

 -->

O código do link personalizado geralmente é implementado com a adição de um manipulador de eventos [!UICONTROL onClick] a um link ou com a adição do código a uma rotina existente. Ele pode ser implementado essencialmente de qualquer função ou manipulador de eventos JavaScript.

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. Esta função, [!UICONTROL s.tl()], é chamada diretamente em um manipulador de eventos, como [!UICONTROL onClick] ou [!UICONTROL onChange], ou de uma função separada. Esta função [!UICONTROL s.tl()] tem cinco argumentos. Os três primeiros são obrigatórios:

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## Acompanhamento de link personalizado nos navegadores Firefox e WebKit {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

O JavaScript H.25 inclui uma atualização para garantir que o rastreamento de links seja concluído com sucesso em navegadores WebKit (Safari e Chrome). O JavaScript H.26 inclui uma atualização para garantir que o rastreamento de links seja concluído com sucesso no FireFox 20 e posteriores.

Após essa atualização, os links de download e de saída que são acompanhados automaticamente (determinados por [!DNL s.trackDownloadLinks] e [!DNL s.trackExternalLinks]) serão acompanhados com sucesso. Se você estiver acompanhando links personalizados usando chamadas manuais ao JavaScript, precisará modificar o modo como essas chamadas são feitas. Por exemplo, links de saída e de download com frequência são acompanhados com código semelhante ao seguinte:

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

O Internet Explorer executa a chamada de rastreamento de link e abre a nova página. Outros navegadores podem cancelar a execução da chamada de rastreamento do link quando a nova página é aberta. Com frequência, isso impede a conclusão das chamadas de rastreamento de link.

Para contornar esse comportamento, o H.25 (lançado em julho de 2012) inclui um método sobrecarregado de rastreamento de link ([!DNL s.tl]) que força os navegadores a aguardarem a conclusão da chamada de rastreamento de link. Esse novo método executa a chamada de rastreamento de link e, em seguida, lida com o evento de navegação em vez de usar a ação padrão do navegador. Este método sobrecarregado requer um parâmetro adicional, chamado [!UICONTROL doneAction], para especificar a ação a ser executada quando a chamada de rastreamento de link é concluída.

Para usar esse novo método, atualize as chamadas para [!DNL s.tl] com um parâmetro [!UICONTROL doneAction] adicional, semelhante ao seguinte:

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

A transmissão de &#39;navigate&#39; como [!UICONTROL doneAction] reflete o comportamento padrão do navegador e abre a URL especificada pelo atributo href quando a chamada de rastreamento é concluída.

No JavaScript H.25.4 (lançado em fevereiro de 2013), as limitações de escopo a seguir foram adicionadas aos links acompanhados quando `useForcedLinkTracking` estava ativada. O rastreamento de link forçado automático se aplica apenas a:

* `<A>` e `<AREA>` tags.
* A tag deve ter um atributo `HREF`
* The `HREF` can&#39;t start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

## Acompanhamento de link com o uso de uma solicitação de imagem {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

Os links podem ser rastreados sem chamar a função s.tl() ao construir uma solicitação de imagem.

<!-- 

link_img.xml

 -->

As solicitações de imagem são codificadas com a adição do parâmetro &quot;pe&quot; ao seu parâmetro src de solicitação de imagem, como a seguir:

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = download
* lnk_e = saída
* lnk_o = personalizado

Além disso, é possível especificar uma URL do link transmitindo a URL no parâmetro pev1:

```
pev1=mylink.com
```

É possível especificar uma URL do link transmitindo a URL no parâmetro pev2:

```
pev2=My%20Link
```

Por exemplo:

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## Configuração de variáveis adicionais para downloads de arquivos, links de saída e links personalizados {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

Por padrão, eles são definidos dentro do arquivo JS, como a seguir:

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

A variável *`linkTrackVars`* deve incluir todas as variáveis que você quer rastrear com cada download de arquivo, link de saída e link personalizado. The *`linkTrackEvents`* parameter should include each event you want to track with every file download, exit link, and custom link. Quando um desses tipos de link ocorrer, o valor atual de cada variável identificado será acompanhado.

Por exemplo, para monitorar prop1, eVar1 e event1 com todos os downloads de arquivo, links de saída e links personalizados, use as seguintes configurações no arquivo JS global:

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. Provavelmente, esse procedimento inflará instâncias de cada variável inadvertidamente e deve ser evitado.

## Práticas recomendadas {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. É possível aumentar instâncias de cada variável e evento em situações em que a variável (ou evento) se aplica à página atual, mas não ao download de arquivo específico, link de saída, ou link personalizado.

Para garantir que as variáveis adequadas estejam definidas com o código de link personalizado, a Adobe recomenda definir *`linkTrackVars`* e *`linkTrackEvents`* no código de link personalizado, da seguinte forma:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>No exemplo acima, o valor de prop 1 é definido dentro do próprio código do link personalizado. O valor de prop2 vem do valor atual da variável, como definido na página.

## Utilização de chamadas de função com código de link personalizado {#concept_DB662C93B3ED415DB72C80270502BE5D}

Devido à natureza complexa do código de link personalizado, é possível consolidar o código em uma função JavaScript autocontida (definida na página ou em um arquivo JavaScript vinculado) e fazer chamadas para a função no manipulador do [!UICONTROL onClick].

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>Se necessário, você pode passar o tipo de link e o nome do link como parâmetros adicionais para a função javascript.

Você pode utilizar um código semelhante ao seguinte para chamar essas funções:

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## Como evitar contagens de link duplicadas {#section_9C3F73DE758F4727943439DED110543C}

É possível que o link seja contabilizado duas vezes em situações nas quais o link normalmente seria capturado pelo rastreamento automático de download de arquivo ou link de saída.

Por exemplo, se você rastreia automaticamente downloads de PDF, o código a seguir resulta em uma contagem de download duplicada:

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

Para garantir que a dupla contagem do link não ocorra, use a seguinte função do JavaScript modificada:

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

As duas últimas linhas do código acima modificam o comportamento do código de link personalizado para que somente o comportamento de rastreamento automático ocorra, eliminando qualquer possibilidade de dupla contagem.

## Janelas de popup com useForcedLinkTracking {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement]O executa a chamada de rastreamento de link e, em seguida, trata o evento de navegação em vez de usar a ação padrão do navegador.

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

Isso permite que o link seja rastreado e o popup carregue da maneira esperada.

## Links de redutores de URL {#concept_CD792362A8E04448B452BE9A18772024}

Links provenientes de serviços de redutores de URL (como o bit.ly) normalmente não são rastreados como visualizações de página ou referenciadores. Estes serviços devolvem 301/302 redirecionamentos com o URL completo para o navegador da Web. O navegador, então, envia uma nova solicitação isolada para o URL completo. O referenciador original é preservado, uma vez que o redutor possui o mesmo tamanho no loop; também não há nenhuma indicação de que o serviço de redirecionamento foi utilizado para obter o URL.

<!-- 

link_shortener.xml

 -->

Devido à variedade de serviços disponíveis, recomendamos que você teste os cenários específicos que são usados em seu site para determinar o mecanismo de redirecionamento usado pelo serviço.

## Variáveis de rastreamento de link em doPlugins {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

Para ajudar a gerenciar o controle de links, as variáveis a seguir são preenchidas antes da execução da função `doPlugins`.

<!-- 

util_linkhandler.xml

 -->

No `doPlugins`, você pode usar os seguintes valores para modificar o comportamento de rastreamento de link. Por exemplo, é possível anular o rastreamento ou adicionar variáveis às solicitações de rastreamento.

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variável </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Impacto </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>Contém o tipo de link determinado automaticamente, se houver. Pode ser definido como um dos seguintes: </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d (download) </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e (sair) </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o (personalizado/outro) </li> 
    </ul> <p>Este é o parâmetro <code>pe</code> na solicitação de imagem. </p> </td> 
   <td colname="col3"> <p>Se definido com <code>linkURL</code> ou <code>linkName</code>, uma chamada de servidor é enviada como um link de download, personalizado ou de saída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>O nome que será exibido no relatório personalizado, de download ou de saída. Truncado em 100 caracteres. Pode ser definido como qualquer string. </p> <p>Este é o parâmetro <code>pev2</code> na solicitação de imagem. </p> </td> 
   <td colname="col3"> <p> Se definido como <code>linkType</code>, uma solicitação de imagem será enviada como link de download, personalizado ou de saída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>O URL do link, que atua como o nome se um linkName não existir. Pode ser definido como qualquer string de URL. </p> <p>Este é o parâmetro <code>pev1</code> na solicitação de imagem. </p> </td> 
   <td colname="col3"> <p>Se definido como <code>linkType</code>, uma solicitação de imagem será enviada como link de download, personalizado ou de saída. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>O objeto clicado para referência. É apenas leitura </p> </td> 
   <td colname="col3"> <p>Nenhum impacto direto na medição. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemplo**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## Validação de downloads de arquivos, links de saída e links personalizados {#concept_0B43AD582D3E470899FCCB58E44D3D49}

Para validar completamente os links de download, saída e personalizados, a Adobe recomenda usar um analisador de pacotes para examinar os links em tempo real.

<!-- 

downloads_validate.xml

 -->

Downloads de arquivos, links de saída e links personalizados não são exibições de página, portanto a ferramenta [!UICONTROL DigitalPulse Debugger] não pode ser usada para verificar os parâmetros e as configurações das variáveis. Você deverá usar [Analisador de pacote](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) para exibir os dados do link de rastreamento.
