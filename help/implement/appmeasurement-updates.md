---
title: Notas de versão do AppMeasurement para JavaScript
description: Notas de versão cumulativas do AppMeasurement para JavaScript.
subtopic: Release notes
translation-type: tm+mt
source-git-commit: 55150b8f6968fff973c889c8011e89eecc0d1720

---


# Notas de versão do AppMeasurement para JavaScript

Notas de versão cumulativas do [!DNL AppMeasurement] para JavaScript.

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

Você pode baixar a versão mais recente do AppMeasurement no Gerenciador [de](/help/admin/admin/code-manager-admin.md)código.

## Versão 2.20.0

Data de lançamento: **5 de março de 2020**

* Correção de um problema relacionado à segurança.

## Versão 2.19.0

Data de lançamento: **21 de fevereiro de 2020**

* Atualização do módulo Gerenciamento de público-alvo DIL 9.4. (AN-209341)

## Versão 2.18.0

Data de lançamento: **13 de fevereiro de 2020**

* O AppMeasurement agora pode forçar os cookies a incluírem o atributo Protegido ao configurar a [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) variável. O requisito para essa variável é que todo o site do cliente seja atendido com segurança (HTTPS). (AN-204604)

## Versão 2.17.0

Data de lançamento: **23 de agosto de 2019**

* Suporte adicionado para reordenação da sequência de consulta do Baidu. (AN-182483)
* Correção de um problema que causava valores de visitantes obsoletos nas ocorrências que estavam em fila ao aguardar a aceitação. (AN-184391)

## Versão 2.16.0

Data de lançamento: **15 de agosto de 2019**

* Implementação de `sendBeacon` suporte no [!UICONTROL AppMeasurement] para links de saída. Se uma ocorrência usar `sendBeacon` e a página for descarregada, a solicitação ainda será concluída. Isso é muito útil para links de saída porque é mais provável que a ocorrência atinja os servidores de coleta de dados. (AN-175142)
* Os valores de ECID/fid são agora armazenados em cache na primeira ocorrência, mesmo se as configurações OptIn forem alteradas. (AN-175142)
* Atualização do módulo Gerenciamento de Público-Alvo para DIL 9.3. (AN-182704)
* Exposed switch in `s.ActivityMap.trackScrollReach` to turn scroll reach tracking on or off. (AN-182754)
* Atualização do AppMeasurement para usar o Serviço de ID de Visitante 4.4.0. (AN-182912)

## Versão 2.15.0

Data de lançamento:**15 de julho de 2019**

* Adição do rastreamento de alcance de rolagem do ActivityMap na extensão do Activity Map (AN-172949)
* Adição de DIL 9.2 ao AppMeasurement (AN-182472)

## Versão 2.14.0

Data de lançamento: **21 de maio de 2019**

* Correção de problemas com o gerenciamento do estado dos parâmetros do rastreador quando várias ocorrências estavam pendentes. (AN-176931, AN-176629, DTM-12758)
* Atualização do AppMeasurement para incluir Visitor.js 4.3.0 (AN-180049)

## Versão 2.13.0

Data de lançamento:**10 de abril de 2019**

* Correção de muitos problemas relatados a clearVars. O problema ocorre quando os hits são enviados antes que o rastreador esteja pronto. Quando o rastreador estiver pronto, a biblioteca poderá definir variáveis que já foram limpas ou alteradas. (AN-176931, AN-176629, DTM-12758).

## Versão 2.12.0

Data de lançamento: **22 de fevereiro de 2019**

* Atualização do módulo Gerenciamento de público-alvo DIL 9.1. (AN-175255)
* A Política de segurança GTM não permite o módulo Activity Map. (AN-174679)
* Aprimoramento do AppMeasurement para dar prioridade à opção de não participação, quando o Serviço de identidade não for aprovado na opção de não participação. (AN-175259)

## Versão 2.11.0

Data de lançamento: **11 de fevereiro de 2019**

* Adição de suporte para o novo recurso Serviços de Opt-in da Adobe no AppMeasurement. (AN-163546)
* Adição de suporte para armazenar dados de rastreamento de link no armazenamento de sessão. (AN-162272)
* Adição de suporte para tipo de transmissão de mídia para Análise de áudio. (AN-173265)

## Versão 2.10.0

Data de lançamento: **20 de setembro de 2018**

Esta versão garante que a biblioteca [!DNL AppMeasurement] envie cookies corretamente para todos os tipos de conexão.

* [!DNL AppMeasurement] bloqueia transmissões de cookies durante a POST. (AN-165538)
* Suporte à ação de soltar para XDomainRequest. (AN-165733)
* Reduza [!DNL AppMeasurement]o tempo de vida do cookie padrão do de cinco para dois anos. (AN-158572)
* Remover o Módulo de mídia do Gerenciador de código ([!DNL AppMeasurement]) (AN-166590)

## Versão 2.9.0

Data de lançamento: **24 de maio de 2018**

> [!NOTE]A API de visitante 3.0 ou superior é necessária para clientes que usam o serviço de ID [!DNL Experience Cloud]. A Adobe recomenda atualizar para a versão mais recente da API de visitante sempre que as bibliotecas de código associadas forem atualizadas ( [!DNL at.js], [!DNL AppMeasurement.js], e assim por diante).

* Atualização do [!DNL AppMeasurement] para usar a interface de Visitante atualizada para solicitar IDs. (AN-151483)
* Correção de um problema que fazia com que o cookie de rastreamento de link continuasse sendo gravado mesmo depois da desativação do rastreamento de link. (AN-156332)
* Correção de um problema onde `registerPreTrackCallback` e `registerPostTrackCallback` interrompem a assinatura da função de callback ao serem chamados várias vezes. (AN-158566)

## Versão 2.8.2

Data de lançamento: **12 de abril de 2018**

* Atualização do [!DNL AppMeasurement] para usar a interface de visitante atualizada para solicitar IDs. (AN-151483)
* O cookie de rastreamento de link continua sendo gravado, mesmo com o recurso desativado. (AN-156332)
* Reduza [!DNL AppMeasurement] o tempo de vida do cookie padrão do de cinco para dois anos. (AN-158572)

## Versão 2.8.1

Data de lançamento: **29 de março de 2018**

Re-compilação da API de visitante 3.1.0 (AN-159524), que inclui as correções de erros: (CORE-11390, CORE-10634)

## Versão 2.8.0

Data de lançamento: **15 de março de 2018**

Re-compilação da API de visitante 3.1.0 (AN-159524), que inclui as correções de erros: (CORE-11390, CORE-10634)

* Compilar VAPI v3.1 com [!DNL AppMeasurement] v2.8. (AN-158353)
* Refatoração da criação do terminal de coleta de dados para facilitar o compartilhamento. (AN-156647)
* Adicionar solicitação de métricas de sincronização completa para o [!DNL AppMeasurement]. (AN-158343)

## Versão 2.7.0

Data de lançamento: **18 de janeiro de 2018**

* Cessou o suporte para o IE do 6 ao 9
* Inclusão da API de Visitante v3.0.0
* Inclusão da DIL v7.00

## Versão 2.6.0

Data de lançamento: **9 de novembro de 2017**

Correção de um problema no qual a biblioteca [!DNL AppMeasurement] nem sempre definia a combinação de contas correta quando s_gl é chamada. (AN-152153)

## Versão 2.5.0

Data de lançamento: **21 de setembro de 2017**

* Inclusão de [!DNL dil.js 6.12] (módulo do [!DNL Audience Manager])
* Inclusão da API de Visitante 2.5.0.

## Versão 2.4.0

Data de lançamento: **17 de agosto de 2017**

* Inclui dil.js v6.11
* Inclui a API de Visitante 2.4.0

## Versão 2.3.0

Data de lançamento: **20 de julho de 2017**

* Corrigido o bug no qual `s.Util.getQueryParam` capturado `#`
* Adição da v6.10 do `dil.js` (AN-145701)

## Versão 2.2.0

Data de lançamento: **8 de junho de 2017**

* Adição do suporte para várias ordens de instanciação do [!DNL AppMeasurement]. (AN-138237)
* Inclusão da API de Visitante versão 2.2.0. (AN-144042)

## Versão 2.1.0

Data de lançamento: **20 de abril de 2017**

* Foi incluída a versão mais recente de `dil.js` (AN-140396)
* Foi adicionado o suporte ao parâmetro `adobe_mc_ref` que substitui o referenciador de página. (AN-131920)
* Foi incluída novamente a API de Visitante 2.1.0. (AN-140873)
* Adição do parâmetro `mcorgid`. (AN-139586)
* Foi adicionado o parâmetro cp (customerPerspective). (AN-140897)

## Versão 2.0.0

Data de lançamento: **9 de março de 2017**

* Movido para um novo processo de build que requer a atualização da versão para 2.0.0. (AN-137878)
* A gestão do mboxMCSDID foi movida para o local correto da seção em que as ligação de rastreamento é feita. (AN-138483)

## Versão 1.8.0

Data de lançamento: **19 de janeiro de 2017**

* Inclui VisitorAPI 2.0.0
* A função faz chamadas e verificações para que a SDID seja consumida após a conclusão da verificação de anulação. (AN-134364)
* Adicionados `s.registerPreTrackCallback` e `s.registerPostTrackCallback` ganchos. (AN-134567)

## Versão 1.7.0

Atualizado em: **11 novembro de 2016**

* Inclui a API de Visitante 1.10.1.
* Atualização do módulo [!DNL Audience Manager] com o Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusão da API de Visitante 1.9.0. (AN-132072)
* Atualizar [!DNL AppMeasurement] [!DNL Audience Manager] Módulo com DIL 6.5 e configurações adicionais (AN-129411)
* Inclusão da API de Visitante 1.8.0 (AN-129887)

## Versão 1.6.4

Updated: **August 18, 2016**

*  Atualização do [!DNL AppMeasurement] para ler e gravar cookies AMCV. (AN-127098)
* Inclusão da API de Visitante 1.7.0.

> [!NOTE] Consulte também as notas de versão a seguir para o [!DNL JavaScript] versão 1.6.3, que inclui requisitos atualizados para o serviço Experience Cloud ID.

## Versão 1.6.3

Updated: **August 4, 2016**

* Correção de um problema em que [!DNL AppMeasurement] encerrava prematuramente as conexões de solicitação. (AN-126448)

>[!IMPORTANT] A versão 1.6.0 do serviço da [!DNL Experience Cloud] ID *requer* [!DNL AppMeasurement] o para [!DNL JavaScript] versão 1.6.3 ou superior. If you want to upgrade to version 1.6.0 of the Experience Cloud ID service, please make sure you are using [!DNL AppMeasurement] code version 1.6.3 or higher.

## Versão 1.6.2

Data de lançamento: **21 de julho de 2016**

* Inclusão da API de Visitante 1.6.0.
* Correção de um problema que fazia com que [!DNL AppMeasurement] chamasse o método ofuscado errado na API do visitante. (AN-126006)
* Correção de um problema que causava o erro [!DNL JavaScript]: &quot;Atributo válido apenas na v:image&quot;. (AN-124009)

## Versão 1.6.1

Data de lançamento: **16 de junho de 2016**

* Inclusão da API de Visitante 1.5.7.
* Correção do manuseio do rastreamento de cliques em links no Firefox, que não estava disparando o evento completo.

## Versão 1.6

Data de lançamento: **21 de abril de 2016**

* O módulo de Activity Map [!DNL AppMeasurement] foi integrado ao módulo padrão [!DNL AppMeasurement], portanto, é necessário consultar apenas um arquivo [!DNL .js]. Além disso, o rastreamento de Activity Map está ativado por padrão. (AN-112689)
* Correção de um problema de truncamento que ocorria com a ordem das variáveis da sequência de consulta em [!DNL AppMeasurement], para que *`pageURLRest`*   fosse o último. (AN-114647)

## Versão 1.5.4

Data de lançamento: **17 de março de 2016**

* Inclusão da API de Visitante 1.5.4
* Compatível com o cancelamento da API de Visitante versão 1.5.4 ou superior

## Versão 1.5.3

Data de lançamento: **21 de janeiro de 2016**

* Correção da manipulação do módulo [!DNL Audience Manager] quando os POSTs são usados para rastrear chamadas. (AN-115381)
* O restante do URL (&quot;-g&quot;) da página foi movido para o final da solicitação de rastreamento da string de consulta. (AN-114647)

## Versão 1.5.2

Data de lançamento: **5 de novembro de 2015**

* Inclusão da API de Visitante 1.5.3.
* Corrigida a detecção do IE11 for URL Truncation 2047 (AN-114914)

## Versão 1.5.1

Data de lançamento: **17 de setembro de 2015**

* Inclusão da API de Visitante 1.5.2
* Atualização do módulo de [!DNL Audience Manager] para usar AAM DIL 6.2 - getCustomer IDs do VisitorAPI.js e transmitir a chamada /event para o AAM. (AN-104978)

## Versão 1.5

Data de lançamento: **18 de junho de 2015**

* Suporte para API de Visitante 1.5, que usa o método  *`getCustomerIDs`* para coletar IDs de cliente e estado autenticado, e envia as IDs com as solicitações de coleta de dados.
* Correção da criação de iframe de destino duplicado no módulo **[!UICONTROL AudienceManagement]** (DIL 6.1)
* Solucionado o problema conhecido descrito na versão 1.4.5.

## Versão 1.4.5

Data de lançamento: **21 de maio de 2015**

* A partir do iOS SDK versão 4.5, uma nova extensão do iOS permite coletar dados de uso dos aplicativos Apple Watch, widgets Today, widgets Photo Editing e todos os outros aplicativos de extensão iOS. Consulte Implementação [da extensão do](https://docs.adobe.com/content/help/en/mobile-services/ios/ios-ext/ios-ext.html) iOS no guia do usuário dos Mobile Services.
* A partir do Android SDK versão 4.5, uma nova extensão do Android permite coletar dados do aplicativo Android wearable. Consulte [Android wearables](https://docs.adobe.com/content/help/en/mobile-services/android/wearables-android/android-wearable.html) no guia do usuário do Mobile Services.
* Inclusão da API de Visitante 1.4.
* Foi atualizado o módulo do AudienceManagement para usar o DIL versão 6.0.

> [!NOTE] Problema **conhecido**: Nas integrações da API/ [!DNL AppMeasurement] [!DNL Audience Manager] módulo do visitante, há duas solicitações de publicação de destino do iFrame feitas no IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` e `//fast.<subdomain>.demdex.net/dest4.html`. O comportamento correto, conforme observado em outros navegadores, é o de carregar apenas `//fast.<subdomain>.demdex.net/dest5.html`.

## Versão 1.4.4

Data de lançamento: **16 de abril de 2015**

* Agora é possível incluir variáveis de dados de contexto personalizados com medições de ciclo de vida.
* As chamadas `trackBeacon` e `clearCurrentBeacon` agora estão disponíveis no  PhoneGap.
* A minor fix to clear the light server call profile ID after the `trackLight` call.

## Versão 1.4.3

Data de lançamento: **19 de fevereiro de 2015**

* Tornou o gerenciamento do rastreio tardio de chamadas consistente, o que corrigiu problemas com as variáveis revertidas durante o atraso, como por exemplo o objeto clicado.
* Alteração realizada para que o rastreamento de referenciador não fosse automático após a primeira chamada de rastreamento. Assim, as chamadas de rastreamento subsequentes (geralmente nos rastreamentos em cadeia) não contarão o referenciador duas vezes quando  *`s.referrer`* for definido manualmente antes da primeira chamada de rastreamento.
* O zip de distribuição foi atualizado para incluir a API de Visitante 1.3.5.

## Versão 1.4.2

Data de lançamento: **15 de janeiro de 2015**

* Solucionado o manuseio da pré-renderização do WebKit para evitar o monitoramento de páginas pré-renderizadas que não são visualizadas.
* O zip de distribuição foi atualizado para incluir a API de visitante 1.3.4 e um módulo atualizado **[!UICONTROL AudienceManagement]** que inclui DIL versão 5.5.

## Versão 1.4.1

Data de lançamento: **18 de setembro de 2014**

* A variável `tagContainerMarker` que permite que a implementação especifique até 4 caracteres que anexados à sequência da versão junto com um delimitador de caractere de travessão foi adicionada. Isto é usado pelo Dynamic Tag Management.

   ```js
   // JavaScript
   s.tagContainerMarker = "D1.0";
   
   // Data Collection request
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   Os 4 caracteres são limitados aos que são permitidos nos caminhos de arquivo URL, como caracteres alfanuméricos e pontos.

* Nas páginas que são marcadas duas vezes com o H Code, foi solucionado um loop que poderia ocorrer durante o rastreamento de link automático (fazer download e sair) quando o rastreamento de link forçado está ativado (padrão nos navegadores Webkit). Além disso, foi adicionada uma proteção geral no rastreamento de link automático para impedir loops similares. Essa proteção limita cliques repetidos no rastreamento automático de link no *mesmo* objeto a um clique a cada 10 segundos. Essa proteção é aplicada somente no monitoramento automático de link, sendo assim, as chamadas do monitoramento de link manual (s.tl) não ficam limitadas. Cliques em diferentes objetos também não são afetados por essa proteção e serão rastreados.
* Solucionado o gerenciamento de objeto clicado quando um atraso é necessário.
* Solucionado o problema gerava um contagem de visualização de página dupla quando o s.t era chamado a partir de uma função de link clicável, se a API de Visitante não tivesse os valores necessários.
* Suporte para HTTP POST.

   > [!IMPORTANT] Para uma [!DNL Analytics] chamada para usar o método POST em vez do método GET em [!DNL AppMeasurement] (um método de solução de URLs [truncados no IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), você deve estar usando a implementação mais recente do Serviço de ID de visitante para a Experience Cloud.

## Versão 1.4

Data de lançamento: **21 de agosto de 2014**

* O rastreamento de plug-ins de navegadores foi removido (parâmetro de consultas `p`), já que os plug-ins não são mais relatados na versão 15.
* Adição do módulo **[!UICONTROL AudienceManagement]** no zip de download.
* Adicionado suporte para eVars adicionais (76 - 250) e eventos (101-1000).

> [!NOTE] O código H não é compatível com eVars e eventos adicionais.

## Versão 1.3.2

Data de lançamento: **19 de junho de 2014**

* Corrigido o uso das bandeiras de conclusão e espera para os campos da API do visitante, como a [!DNL Analytics]ID do visitante do antiga, que gerava erros.
* Suporte para novos recursos no serviço de ID do visitante 1.3.

## Versão 1.3.1

Data de lançamento: **22 de maio de 2014**

* [!DNL AppMeasurement]A função [!DNL JavaScript] `s_gi` do para não encontrava instâncias corretamente criadas com o código H `s_gi`. Observe que esse problema afetou apenas algumas implementações de marcação dupla, onde o [!DNL AppMeasurement] para [!DNL JavaScript] e o código H estavam na mesma página com instâncias separadas, e `s_gi` era usado para encontrar instâncias por conjunto de relatórios.

## Versão 1.3

Data de lançamento: **17 de abril de 2014**

* Suporte para [Serviço de ID de visitante da Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html).

## Versão 1.2.4

Data de lançamento: **13 de março de 2014**

* Correções de bugs para vídeo heartbeat.

## Versão 1.2.3

Data de lançamento: **20 de fevereiro de 2014**

* Correções de bugs para vídeo heartbeat.

## Versão 1.2.2

Data de lançamento: **6 de fevereiro de 2014**

* Correção de um problema de compatibilidade com o módulo DIL [!DNL Audience Manager]. [!DNL Audience Manager]Os clientes do também devem atualizar para a versão 4.8 do módulo DIL.

## Versão 1.2.1

Data de lançamento: **15 de novembro de 2013**

* Corrigidos os eventos de página usados para a medição de vídeo Heartbeat.

## Versão 1.2

Data de lançamento: **14 de novembro de 2013**

* Added support for [Heartbeat video measurement](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).
* `VisitorAPI.js` foi adicionado para oferecer suporte ao [Serviço de ID do visitante](https://docs.adobe.com/content/help/en/id-service/using/home.html).

## Versão 1.1.1

* Impossibilitava o envio de uma chamada de rastreamento de link de navegadores Opera para links que começavam com &quot;opera:&quot; (&quot;opera:&quot; é similar a &quot;sobre:&quot; e &quot;chrome:&quot; em outros navegadores).
* `alt=""` =&quot;&quot; foi adicionado a todos os objetos de Imagem para estar de acordo com a Lei de Vídeos Acessíveis e Comunicação.

## Versão 1.1

Data de lançamento: **18 de setembro de 2013**

* Correção do suporte para colocar a biblioteca e código de página na tag `head`.
* Módulo perdido de suporte `onLoad` adicionado.

## Versão 1.0.3

Data de lançamento: **15 de agosto de 2013**

* Acrescentamos suporte para implantação através do Tag Management da Adobe.
* Correção de um problema que impedia que variáveis de hierarquia fossem definidas no objeto [!DNL AppMeasurement].

## Versão 1.0.2

Data de lançamento: **18 de julho de 2013**

* Agora, o hash/fragmento é omitido pelo rastreamento automático de link. Antes, o URL a seguir era rastreado automaticamente se o `href` inteiro terminasse em `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Agora, o hash/fragmento é omitido para que o link seja rastreado somente quando o nome do arquivo terminar em uma extensão correspondente. 

## Versão 1.0.1

Data de lançamento: **23 de maio de 2013**

Uma nova biblioteca de [!DNL JavaScript] [!DNL AppMeasurement] está disponível no Gerenciador de código. Essa biblioteca oferece a mesma funcionalidade principal de [!DNL s_code.js], mas é mais leve e rápida de usar em sites móveis e para desktop.

* De 3 a 7 vezes mais rápida do que o código H.25.
* Somente 21k descompactado e 8k compactado por gzip (o código H.25 pesa 33k descompactado e 13k compactado por gzip).
* Suporte nativo para obter parâmetros de consulta, cookies de leitura e gravação e executar rastreamento de links avançado.
* Pequeno e rápido o suficiente para ser usado em sites móveis e robusto o suficiente para ser usado na Web completa para desktop, permitindo que você utilize uma única biblioteca em todos os ambientes da Web.
