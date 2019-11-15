---
description: Implemente o projeto Accelerated Mobile Pages (AMP) no Adobe Analytics.
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
solution: Analytics
title: Accelerated Mobile Pages
topic: Developer and implementation
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Accelerated Mobile Pages

Implemente o projeto Accelerated Mobile Pages (AMP) no Adobe Analytics.

O AMP é um [projeto de código aberto](https://www.ampproject.org/) que permite a criação de páginas da Web para conteúdo estático, capaz de ser renderizado rapidamente. Esse recurso é ideal para editores que desejam criar conteúdo otimizado para dispositivo móveis e carregá-lo instantaneamente em qualquer lugar. O tópico inclui:

* [Como funciona](/help/implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [Uso da tag amp-analytics com o modelo "adobeanalytics"](/help/implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [Uso da tag amp-analytics tag com o modelo "adobeanalytics_nativeConfig"](/help/implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [Resumo](/help/implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [Perguntas frequentes](/help/implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Documentação adicional e exemplos**

* [Documentação](https://www.ampproject.org/docs/get_started/about-amp.html) externa do projeto de código aberto AMP
* [Exemplos](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) de instalação

## Como funciona {#section_21C2836D63104794BCEBEECB6593AFBF}

As AMPs apresentam páginas HTML com tags especiais armazenadas em cache na Web em diferentes redes de fornecimento de conteúdo (CDNs) dos parceiros e editores de tecnologia participantes. Ao fazê-lo, o conteúdo AMP é entregue da fonte mais próxima com a latência mais baixa. Isso causa uma complicação de dados analíticos, já que não há certeza de onde o conteúdo de um editor será carregado, e cookies de terceiros dificultam a identificação dos visitantes.

Além disso, para reduzir o volume de conteúdo e acelerar o tempo de peso da página, as AMPs limitam o uso de JavaScript e cookies. Apesar de ser uma boa experiência para o seu dispositivo móvel, por reduzir a quantidade de processamento, essa limitação introduz desafios na medição precisa de visitantes únicos e na compreensão da aquisição e retenção de usuários.

Para solucionar esses problemas, a Adobe trabalhou juntamente a parceiros e editores de AMPs em duas opções que podem ser escolhidas de acordo com as necessidades empresariais dos editores, usando a tag `amp-analytics`. A primeira abordagem usa o modelo de rastreamento `"adobeanalytics"` para criar a solicitação do Analytics diretamente da AMP. A segunda abordagem usa o modelo de rastreamento `"analytics_nativeConfig"`, que usa um iframe contendo o código AppMeasurement implantado no site normal. A tabela a seguir apresenta os prós e contras de cada abordagem.

|  | **modelo "adobeanalytics"** | **modelo "adobeanalytics_nativeConfig"** |
|---|---|---|
| Contagem de visitante/visitas (no conjunto de relatórios atual) | Inflação alta | Inflação mínima |
| Uso de um conjunto de relatórios diferente | Recomendado | Não é necessário |
| Visitantes novos vs. retornos | Não suportado | Suportado |
| Serviço de ID de visitante | Não suportado | Suportado |
| Rastreamento de vídeo e link | Suporte parcial | Ainda não é suportado |
| Dificuldade da implementação | Um pouco difícil | Relativamente fácil |
| [!DNL Experience Cloud] integrações | Não suportado | Suportado com limitações |

## Uso da tag amp-analytics tag com o modelo "adobeanalytics" {#section_2E4EBF4EF623440D95DE98E78C47244E}

O `"adobeanalytics"`modelo de rastreamento usa a tag `amp-analytics` para criar diretamente uma solicitação de rastreamento. Ao usar o modelo `"adobeanalytics"` na tag `amp-analytics`, você pode especificar solicitações de hit que são acionadas em eventos específicos da página, como tornar a página visível, ou em um clique (e, em breve, visualizações de vídeo e muito mais). Eventos de clique podem ser personalizados para se aplicarem a certas IDs de elemento ou classes ao especificar um seletor. A Adobe facilitou a configuração usando o modelo `"adobeanalytics"` criado especificamente para o [!DNL Adobe Analytics]. É possível carregar o modelo ao adicionar `type="adobeanalytics"` à tag amp-analytics.

No código de exemplo a seguir, há dois disparadores definidos: `pageLoad` e `click`. O disparador `pageLoad` será acionado quando o documento se tornar visível e incluirá a variável `pageName`, como definido na `vars section`. O segundo disparador `click` é acionado ao clicar em um botão. Para este evento, `eVar 1` será definido com o valor `button clicked`.

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
      }, 
      "click": { 
        "on": "click", 
        "selector": "button", 
        "request": "myClick", 
        "vars": { 
          "eVar1": "button clicked" 
        } 
      } 
    } 
  } 
  </script> 
  </amp-analytics> 
```

No disparador `click`, você pode especificar um seletor para garantir que, ao clicar no elemento DOM (nesse caso, qualquer botão), a solicitação `buttonClick` é acionada e definida automaticamente para denotar essa ocorrência como um evento (ou seja, chamada `trackLink`).

Além disso, o `amp-analytics` suporta uma quantidade de substituições para as variáveis, para que o AMP possa fornecer valores de dados conhecidos. Para obter mais informações, visite [a documentação da variável amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md).

Se desejar incorporar uma tecnologia ou variável DOM (como browser, screen size, device, referrer etc.), terá que adicioná-las a qualquer solicitação, já que não são geradas automaticamente. A documentação de cada parâmetro de cadeia de caracteres de consulta disponível usada para o rastreamento pode ser encontrada [aqui](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html).

Ao analisar as ocorrências criadas por amp-analytics, percebe-se que em cada solicitação, a Adobe incluiu o parâmetro de consulta `vid`. Configuramos o `vid` com base em uma função AMP integrada para definir uma ID de cookie personalizada do Analytics chamada `adobe_amp_id`. A ID não depende de nenhuma outra ID sendo definida pelo [!DNL Adobe Analytics] em qualquer outro lugar (por exemplo, `s_vi cookie`) e cria novos visitantes em qualquer conjunto de relatórios que esteja recebendo as ocorrências.

A seguir estão algumas observações a ter em mente. Ao usar a tag amp-analytics conforme mencionado acima, os visitantes não serão incluídos no seu rastreamento habitual, e porque a AMP pode ser carregada de qualquer rede de fornecimento de conteúdo, você terá um visitante para cada CDN na qual a AMP for visualizada (o que causa a inflação de visitante mencionada acima). Por isso, a Adobe recomenda que, se você usar o modelo `"adobeanalytics"` para `amp-analytics`, seus dados sejam colocados em um conjunto de relatórios separados específico para a AMP. Além disso, o Serviço de ID [!DNL Experience Cloud] (antigo *`visitor ID service`*) não é compatível com este método, portanto, se a sua empresa requer integrações adicionais da [!DNL Experience Cloud] ou pretende tê-las no futuro, esta opção não é recomendada para você.

Por fim, é importante saber que essa solução `amp-analytics` exige que o servidor de rastreamento seja especificado na seção `vars` corresponda ao servidor de rastreamento no seu site principal, para que os controles da sua política de privacidade sejam respeitados. Caso contrário, é preciso criar uma política de privacidade exclusiva às AMPs.

## Uso da tag amp-analytics com o modelo "adobeanalytics_nativeConfig" {#section_3556B68304A4492991F439885727E9FF}

A tag `"adobeanalytics_nativeConfig"` é mais fácil de implementar, pois usa a mesma metodologia de marcação usada nas páginas normais da Web. Para isso, adicione o seguinte à sua tag `amp-analytics`:

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

Essa abordagem envia dados a uma página da Web de utilitário por meio de parâmetros de cadeias de caracteres de consulta especiais adicionados ao parâmetro de solicitação `iframeMessage`. Nesse caso, observe que adicionamos a variável `ampdocUrl AMP`, e `documentReferrer` aos parâmetros de cadeias de caracteres de consulta `pageURL`, relacionam-se com a solicitação `iframeMessage` acima. Esses parâmetros de cadeias de caracteres de consulta podem ser renomeados de acordo com a sua preferência, contanto que a sua página [!DNL stats.html] (exibida abaixo) esteja configurada para coletar os dados apropriados.

O modelo `"adobeanalytics_nativeConfig"` também adiciona parâmetros da sequência de consulta com base nas variáveis listadas na seção `extraUrlParams` da tag amp-analytics. Nesse caso, observa-se que especificamos os parâmetros `pageName` e `v1`, que serão usados na sua página [!DNL stats.html].

É possível usar somente um modelo `amp-analytics` por vez e o modelo `"adobeanalytics"` não pode ser usado junto ao modelo `"adobeanalytics_nativeConfig"` na mesma AMP. Ao tentar fazer isso, ocorrerá um erro no console do navegador e a sua contagem de visitantes aumentará incorretamente.

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam("ref"); 
s.t(); 
</script> 
</body> 
</html> 
```

Conforme mostrado acima, você pode usar ou vincular aos seus [!DNL VisitorAPI.js] e [!DNL AppMeasurement.js] (como no exemplo), ou ao que a sua implementação usar, e adicionar os parâmetros de configuração corretos. Para capturar os valores corretos nas variáveis correspondentes, use a função `s.Util.getQueryParam` fornecida para coletar os valores passados do URL `iframeMessage` e definir as variáveis apropriadas, conforme você faria em outros sites. If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. Nesse caso, `s.pageName` está definido como o valor passado no parâmetro de cadeia de caracteres de consulta `pageName`. Aqui, o nome da página será definido como *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>Devido a restrições nos iframes na estrutura da AMP, sua página [!DNL stats.html] deve ser hospedada em um subdomínio diferente do domínio no qual a AMP está hospedada. A estrutura da AMP não permite iframes do mesmo subdomínio no qual a AMP está. Por exemplo, se a sua AMP estiver hospedada em [!DNL amp.example.com], hospede sua página [!DNL stats.html] em um subdomínio diferente, como [!DNL ampmetrics.example.com], ou similar.

Devido à página de utilitários estar hospedada no seu site original, nenhum ajuste adicional é necessário para respaldar a sua política de privacidade em todas as AMPs. Isso significa que, se um usuário final optar por não ser rastreado no seu site primário, ele também deixará de ser rastreado em todas as suas AMPs, sem etapas adicionais. Usar essa página de utilitário também significa que o AMP oferece suporte ao serviço da [!DNL Experience Cloud] ID da Adobe, para que você possa integrar as medições capturadas nos AMPs com o restante da [!DNL Experience Cloud] (para publicidade direcionada usando o [!DNL Adobe Audience Manager], por exemplo).

Em outras palavras, se a sua empresa ainda não estiver usando o serviço de ID [!DNL Experience Cloud] (ou se tiver um software de Tag Management como o [!DNL Dynamic Tag Manager] da Adobe), você poderá aplicar tags à página [!DNL stats.html] da maneira que quiser. Use a sua implementação atual como um ponto de referência. A única diferença é que você obtém pontos de dados apropriados por meio do URL `iframeMessage` da amp-analytics (ou [!DNL document.URL] de dentro da página [!DNL stats.html]) para cada uma das variáveis que você deseja definir. Além disso, se você desejar usar uma das [variáveis específicas de AMPs](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (mencionadas acima) como o referrer da AMP ou o URL da página AMP, certifique-se de incluí-las no objeto iframeMessage, conforme mostrado no exemplo acima.

Apesar de ser flexível, essa solução apresenta limitações. Devido a restrições inerentes no `amp-analytics` `iframeMessage`, só é possível carregá-lo em uma página uma vez. Portanto, não será possível realizar o rastreamento de link ou de vídeo com o modelo `"adobeanalytics_nativeConfig"`. Além disso, alguns valores DOM que são capturados normalmente pelo nosso código do [!DNL AppMeasurement], como `referrer` (que afeta os relatórios do Search Engine Keyword, o Referenciador e os relatórios do Tipo de referenciador ou que pode incluir um código de rastreamento de campanha de marketing) terão que ser passados automaticamente para o `iframeMessage` usando as variáveis de AMP que [estiverem disponíveis](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). Por esse motivo, a Adobe recomenda a definição de uma variável personalizada com o valor AMP, se você colocar dados AMP em um conjunto de relatórios ja existe, para que você possa filtrar o tráfego da AMP ao visualizar os relatórios previamente mencionados. Com isso em consideração, relatórios de tecnologia padrão, como navegadores, dispositivos, tamanho ou resolução da tela funcionarão automaticamente.

Por fim, devido ao iframe carregar como uma página separada e executar nela o JavaScript por completo, a AMP não é tão leve quanto planejado para o padrão. Para esclarecer, o tempo de carregamento da página não é afetado (o iframe é carregado depois que o carregamento da página é concluído), entretanto, a CPU e a rede terão um esforço maior que o normal, o que pode afetar a experiência de rolagem da página. Ainda não encontramos grandes problemas na prática, mas estamos trabalhando com o Google para reduzir o impacto na experiência do usuário com essa abordagem. 

## Resumo {#section_4D8ED26084F249738A5C2BC66B933A07}

Se você precisar usar o rastreamento de cliques, mesmo que os visitantes do seu site sejam contados como novos visitantes, use o modelo de rastreamento `"adobeanalytics"`, seguindo a nossa recomendação para colocar os dados em um *`separate report suite`*. Se você precisar do serviço de ID [!DNL Experience Cloud], se não quiser o aumento de visitantes ou visitas e se estiver de acordo com o acionamento do Analytics somente quando a página for carregada, recomendamos que você use a solução `"adobeanalytics_nativeConfig"`.

O Adobe Analytics tem orgulho da parceria com o Google e nossos editores para fornecer recursos de análise líderes do mercado a editores na Web móvel em uma experiência do usuário extremamente rápida. Apesar dessas soluções oferecerem objetivos diferentes, estamos trabalhando para construir a melhor solução a longo prazo para atender às necessidades de análises dos nossos clientes.

O Projeto AMP está em rápido desenvolvimento, passando por mudanças regularmente, portanto consulte [esta página](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) com frequência para obter exemplos atualizados. As informações apresentadas até agora são suficientes para ajudá-lo a começar, mas mudanças estão sujeitas a acontecer conforme aprimoramos nossas integrações e mais editores adotam AMPs ao longo do tempo.

Se tiver perguntas ou encontrar problemas, entre em contato com o Atendimento ao cliente ou o seu Consultor da Adobe.

## Perguntas frequentes {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> No momento, não. O padrão da AMP é compatível somente com disparadores como "visible", "click" e "timer", e ainda não oferece suporte a disparadores explícitos para rastreamento de vídeo que possam ser escutados pela tag amp-analytics. Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Você menciona que a inflação de visitante é menor para o modelo "<code> adobeanalytics_nativeConfig </code>" na sua comparação. O que isso quer dizer? What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> "adobeanalytics_nativeConfig" </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> "adobeanalytics" </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> "adobeanalytics_nativeConfig" </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. Isso significa que todos os visitantes do Safari que não visitaram anteriormente o site de um editor serão inflados nos relatórios do Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo usar um conjunto de relatórios separado para AMPs? </p> </td> 
   <td colname="col2"> <p>Recomendamos o uso de um conjunto de relatórios separado para AMPs se você usar o modelo adobeanalytics, por causa do conflito de inflação de visitante/visita. Entretanto, também iremos definir a versão do JavaScript para "AMP vX.X" do modelo de tag amp-analytics para que você possa filtrar o tráfego de um conjunto de relatórios combinado, caso necessário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>O que é o serviço da <span class="keyword">Experience Cloud</span> ID? É necessário? </p> </td> 
   <td colname="col2"> <p>O <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"  > Serviço de identidade </a> (antigo <span class="term"> serviço de ID de visitante </span>) ativa os serviços principais da <span class="keyword"> Adobe Experience Cloud </span> e permite integrações entre diferentes soluções da Adobe <span class="keyword"> Experience Cloud</span>. Se você tiver integrações com o <span class="keyword">Adobe Audience Manager</span> ou o <span class="keyword">Adobe Target</span>, você já deve estar usando esse serviço. Além disso, o serviço é a base de vários recursos do <span class="keyword">Adobe Analytics</span> que estão por vir. Se precisar de suporte ao serviço de ID, recomendamos o uso da solução <code> iframeMessage </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>O padrão de AMP não permite que iframes sejam carregados do mesmo subdomínio e subdomínio que a AMP. Portanto, recomendamos que você hospede a página de utilitários em um subdomínio separado do seu site principal, especialmente se a sua empresa tem uma própria CDN que planeja em usar AMPs. Para ter compatibilidade máxima, escolha um subdomínio como <span class="filepath">ampmetrics.publisher.com</span> que esteja separado de onde o conteúdo da AMP se encontra.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Isso não é parecido com os <span class="keyword">Instant Articles do Facebook </span>? Como configurar o <span class="keyword">Adobe Analytics</span> com o Instant Articles do Facebook? </p> </td> 
   <td colname="col2"> <p> Os Instant Articles do Facebook são compatíveis com uma solução similar à solução nativeConfig resumida acima. De fato, a página stats.html criada acima pode atender às suas necessidades de análise tanto para a AMP quanto para os Instant Articles do Facebook, simultaneamente. Para obter mais informações sobre como implementar o rastreamento nos Instant Articles do Facebook, consulte <a href="/help/implement/js-implementation/analytics-facebook-instant-articles.md"  > Instant Articles do Facebook </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

