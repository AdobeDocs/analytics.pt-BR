---
description: Perguntas frequentes sobre a implantação e links para mais informações.
keywords: Implementação do Analytics;faq;perguntas frequentes;expiração de evar;visibilidade de evento personalizado;carimbo de data e hora;período de carência da id de visitante;id de visitante;id de visitante da Experience Cloud;id de visitante do Analytics;dtm;heartbeat;cookies;servidor de rastreamento;desempenho;javascript;coleta de dados;versão de s_code;depuração de s_code;rastrear tipos de link;rastrear vídeo;rastrear aplicativo para dispositivo móvel;cookie primário;certificado ssl;expiração da certificação;expiração do certificado;plug-ins;api de inserção de dados;erro 500;500;Gerenciar usuário;gerenciar grupo;usuários;grupos
seo-description: Perguntas frequentes sobre a implantação e links para mais informações.
seo-title: Perguntas frequentes sobre a implementação do Analytics
solution: Analytics
title: Perguntas frequentes sobre a implementação do Analytics
topic: Desenvolvedor e implementação
uuid: 983d759a-c4f2-4021-84c8-0486dbb951b8
translation-type: tm+mt
source-git-commit: c723d0938a2ea782d026daf67599d7be38a93c46

---


# Perguntas frequentes sobre a implementação do Analytics

Perguntas frequentes sobre a implantação e links para mais informações.

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>Pergunta</b> </td> 
   <td> <b>Resposta</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Como gerencio usuários e grupos do Analytics? </p> </td> 
   <td colname="col3"> <p>Para obter informações sobre como gerenciar usuários e grupos, consulte <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html">Gerenciamento de usuários e produtos</a> na ajuda da Adobe Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Expiração da eVar - Por que as eVars estão sendo atribuídas a "Nenhum" nos relatórios? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol"> Expira após</span> especifica um intervalo de tempo, ou evento, relacionado à expiração do valor de eVar (não recebe mais crédito para eventos de sucesso). Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). Se você selecionar um evento como valor de expiração, a variável expirará somente se o evento ocorrer. Se o evento não ocorrer, a variável nunca expirará. <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visibilidade de evento personalizado - Por que os Eventos personalizados não aparecem no menu de relatórios? </p> </td> 
   <td colname="col3"> <p>Na coluna Visibilidade, você pode ocultar métricas padrão (incorporadas), eventos personalizados e eventos incorporados no Menu, Seletores de métricas, Construtor de métricas calculadas e o Construtor de segmentos. Essa configuração não afeta a coleta de dados da métrica ou do evento, afeta somente a visibilidade na interface do usuário. <a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Carimbos de data e hora - O que é preciso ser considerado antes de alterar as configurações de carimbo de data e hora? </p> </td> 
   <td colname="col3"> <p>Ao usar o recurso Carimbos opcionais de data e hora, é possível combinar dados com e sem informações de data e hora, sem perda de dados. Dados offline com carimbos de data e hora gerados em um dispositivo móvel podem ser combinados com dados ativos de uma página da Web que não tenha essas informações ou integrados com dados de qualquer plataforma usando uma chamada de carimbo de data e hora do lado do cliente. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID do visitante - Como o período de carência da ID do visitante funciona e como ele é ativado? </p> </td> 
   <td colname="col3"> <p>Caso tenha vários arquivos JavaScript que enviam dados para o mesmo conjunto de relatórios, ou se estiver usando outras tecnologias no seu site, como a medição de vídeo Flash, recomendamos configurar um período de carência. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID de visitante - Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics? </p> </td> 
   <td colname="col3"> <p>O serviço de identidade atribui um identificador contínuo e exclusivo para todos os visitantes do site. Com essa ID, os visitantes e seus dados podem ser compartilhados entre outras soluções na Experience Cloud. Além disso, essa ID pode substituir ou trabalhar com IDs específicas à solução, como a ID de visitante do Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID de visitante - Como a ID do visitante é definida quando os cookies estiverem bloqueados? </p> </td> 
   <td colname="col3"> <p>Se o cookie padrão s_vi estiver indisponível, um cookie de fallback é criado no domínio do sie com uma ID exclusiva gerada aleatoriamente. Esse cookie, chamado s_fid, é definido com uma validade de 2 anos e é usado como o método de identificação de fallback adiante. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management - por que minha regra de DTM não é acionada? </p> </td> 
   <td colname="col3"> <p>Se a sua regra baseada em eventos não é ativada, provavelmente há um problema com o seletor ou condição da regra. Localize o elemento em seu site em que a ação do evento desejado ocorre, clique com o botão direito do mouse e selecione Inspecionar elemento. Inspecione o script realçado na caixa que é aberta e verifique se você está direcionando o elemento correto. <a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Como implementar o rastreamento de Video Heartbeat? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/"> Esta seção</a> contém instruções de download dos SDKs do Video Heartbeat e guias do desenvolvedor para a sua plataforma. Ao baixar o SDK, baixe também o guia do desenvolvedor localizado na página de documentos, pois ele contém instruções de implementação específicas para o Vídeo Heartbeat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Como adicionar cookies ao subdomínio certo? </p> </td> 
   <td colname="col3"> A variável <span class="varname">cookieDomainPeriods</span> determina o domínio em que os cookies s_cc e s_sq do Analytics são definidos, estabelecendo o número de períodos no domínio do URL da página. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in. Consulte [Variáveis de configuração] (/help/implement/js-implementation/c-variables/configuration-variables.md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Servidor de rastreamento - Como preencher corretamente o servidor de rastreamento? </p> </td> 
   <td colname="col3"> <p>Ao configurar uma implementação para enviar dados aos servidores do Adobe Analytics, é preciso enviá-los ao local correto. Se isso não for feito, haverá uma inflação na contagem de visitantes ou perda de dados. <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html"> [Mais...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Desempenho: uma falha no carregamento do Adobe JavaScript externo devido a conexão com a Internet, proxy, firewall ou interrupção de serviço na Adobe pode prejudicar o desempenho? </p> </td> 
   <td colname="col3"> <p>Não. O arquivo JavaScript não fica hospedado nos servidores da Adobe, para que uma interrupção da Adobe não prejudique a execução. Em caso de uso do Dynamic Tag Management, o arquivo JavaScript é hospedado pela Akamai ou em um local de servidor determinado pelos clientes. </p> <p>Consulte <i>O Dynamic Tag Management reduzirá o desempenho do meu site?</i> nas <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html">Perguntas frequentes sobre o Dynamic Tag Management </a>. </p> <p>Além disso, se não quiser depender do CDN da Akamai, é possível hospedar seu próprio arquivo principal de Dynamic Tag Management. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html">Opções de codificação e hospedagem embutidas </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Desempenho: o carregamento de um Adobe JavaScript externo pode gerar uma redução no desempenho? </p> </td> 
   <td colname="col3"> <p> O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e uma versão dele também é baixada ao menos uma vez por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, transferir o JavaScript que é usado várias vezes neste arquivo pode resultar em menos download de dados em geral. </p> <p> Compactação de JavaScript para AppMeasurement: se estiver preocupado com o peso da página (tamanho) do cliente JavaScript da Adobe, a Adobe recomenda a compactação do arquivo usando GZIP. O GZIP é compatível com a maioria dos navegadores e oferece desempenho superior à compactação JavaScript para compactar e descompactar o arquivo JavaScript principal <span class="filepath">s_code.js</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Desempenho: o envio de dados de um navegador para os serviços da Adobe reduz o desempenho? </p> </td> 
   <td colname="col3"> <p> Os arquivos Adobe JavaScript criam um objeto de imagem dentro da página HTML e, em seguida, o navegador solicita o envio do objeto de imagem aos servidores da Adobe. Caso os servidores da Adobe fiquem lentos e com pouca capacidade de resposta, o thread responsável pela solicitação será adiado até que a imagem volte ou o tempo limite seja atingido. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Desempenho: um evento de JavaScript da Adobe pode afetar o comportamento ou a funcionalidade do sistema? </p> </td> 
   <td colname="col3"> <p>Não. Consulte as respostas anteriores sobre desempenho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Como faço para alterar os dados coletados, com base nas condições que eu definir? </td> 
   <td colname="col3"> Use as regras de processamento para simplificar a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Qual é a versão mais recente do arquivo s_code? </td> 
   <td> Esta seção contém um histórico das versões das bibliotecas do [!DNL AppMeasurement] nas plataformas da Web e dispositivos móveis. A versão mais recente de cada biblioteca pode ser baixada em Reports &amp; Analytics &gt; Ferramentas administrativas &gt; Gerenciador de código. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/c_release_notes_javascript.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Como depurar o arquivo s_code? </td> 
   <td> O Adobe Debugger (anteriormente chamado DigitalPulse Debugger) é uma ferramenta gratuita oferecida pela Adobe, que permite a visualização dos dados coletados em seu site em qualquer página específica. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Como rastrear diferentes tipos de links? </td> 
   <td> É possível rastrear automaticamente os downloads de arquivo e links de saída com base nos parâmetros definidos no arquivo AppMeasurement para JavaScript. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Como rastrear vídeos? </td> 
   <td> O JavaScript pode ser utilizado para rastrear vários reprodutores. Para rastrear com o JavaScript, basta adicionar o código à página da Web que contém o reprodutor o rastreá-lo utilizando manipuladores de evento. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Como rastrear um aplicativo para dispositivos móveis? </td> 
   <td> É possível gerar links de aquisição com códigos de rastreamento exclusivos no Adobe Mobile Services. Quando um usuário baixa e executa um aplicativo da Apple App Store depois de clicar em um link gerado, o SDK coleta e envia automaticamente os dados de aquisição para o Adobe Mobile Services. <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/acquisition.html"> iOS</a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/acquisition.html">Android </a> </td> 
  </tr> 
  <tr> 
   <td> Como implementar o rastreamento de vídeo? </td> 
   <td> É possível rastrear reprodutores de mídia ao criar funções vinculadas aos manipuladores de evento do reprodutor de vídeo. Isso permite chamar Media.open, Media.play, Media.stop e Media.close no momento certo. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js_events.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Como configurar o cookie primário? </td> 
   <td> O Analytics usa cookies para fornecer informações sobre variáveis e componentes que não persistem entre as solicitações de imagem e as sessões do navegador. Esses cookies inofensivos são originários de um domínio hospedado pela Adobe, conhecidos como cookies de terceiros. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Como posso obter um certificado SSL? </td> 
   <td> Determine se seu site usa o protocolo https://. Se o fizer, é necessário solicitar um CSR e comprar um certificado SSL. Observação: não é necessário um certificado SSL se você não tem páginas ou conteúdos seguros. Esta etapa pode ser ignorada se você só usar somente o protocolo https:// no site. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Onde encontro informações sobre o aviso de expiração da certificação? </td> 
   <td> Os certificados SSL expiram anualmente, o que significa que a Adobe exige uma solicitação de certificado atualizada sempre que isso acontece. O especialista FPC fornece os avisos necessários quando isso ocorre, no entanto, recomenda-se ser proativo no monitoramento da validade e no fornecimento à Adobe deste certificado atualizado. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_renewals.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> O que são plug-ins? </td> 
   <td> Os plug-ins do AppMeasurement para JavaScript são programas ou funções que executam várias funções avançadas. Esses plug-ins estendem a capacidade de seu arquivo JavaScript para fornecer a você mais funcionalidade do que a disponível com a implementação básica. A Adobe oferece diversos outros plug-ins como parte das soluções avançadas. Entre em contato com seu gerente de conta se você quiser capturar dados usando o JavaScript, mas se não tiver certeza sobre como proceder. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/impl_plugins.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> Informações sobre a API de inserção dos dados? </td> 
   <td> A Adobe criou várias maneiras de enviar dados para o Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/usecase_sending_data_to_sc.html"> [Mais...] </a> </td> 
  </tr> 
  <tr> 
   <td> O que é um erro 500? </td> 
   <td> Informações sobre o erro do servidor interno que causou um status "Erro de consulta 500". <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html">Consulte a variável pageType</a> </td> 
  </tr> 
 </tbody> 
</table>

| Pergunta | Resposta |
|---|---|
| Como gerencio usuários e grupos do Analytics? | Para obter informações sobre como gerenciar usuários e grupos, consulte [Gerenciar usuários e produtos](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) da Experience Cloud na ajuda dos principais serviços da Adobe Experience Cloud. |
| Expiração da eVar - Por que as eVars estão sendo atribuídas a "Nenhum" nos relatórios? | `Expire After` especifica o período ou evento após o qual o valor do eVar expira (não recebe mais crédito por eventos bem-sucedidos). Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). Se você selecionar um evento como valor de expiração, a variável expirará somente se o evento ocorrer. Se o evento não ocorrer, a variável nunca expirará. [[Mais...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Visibilidade de evento personalizado - Por que os Eventos personalizados não aparecem no menu de relatórios? | Na coluna Visibilidade, você pode ocultar métricas padrão (incorporadas), eventos personalizados e eventos incorporados no Menu, Seletores de métricas, Construtor de métricas calculadas e o Construtor de segmentos. Essa configuração não afeta a coleta de dados da métrica ou do evento, afeta somente a visibilidade na interface do usuário. [[Mais...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/metric-visibility.html) |
| Carimbos de data e hora - O que é preciso ser considerado antes de alterar as configurações de carimbo de data e hora? | Ao usar o recurso Carimbos opcionais de data e hora, é possível combinar dados com e sem informações de data e hora, sem perda de dados. Dados offline com carimbos de data e hora gerados em um dispositivo móvel podem ser combinados com dados ativos de uma página da Web que não tenha essas informações ou integrados com dados de qualquer plataforma usando uma chamada de carimbo de data e hora do lado do cliente. [[Mais...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/timestamps-overview.html) |
| ID do visitante - Como o período de carência da ID do visitante funciona e como ele é ativado? | Caso tenha vários arquivos JavaScript que enviam dados para o mesmo conjunto de relatórios, ou se estiver usando outras tecnologias no seu site, como a medição de vídeo Flash, recomendamos configurar um período de carência.  [Mais...](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html) |
| ID de visitante - Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics? | O serviço de identidade atribui um identificador contínuo e exclusivo para todos os visitantes do site. Com essa ID, os visitantes e seus dados podem ser compartilhados entre outras soluções na Experience Cloud. Além disso, essa ID pode substituir ou trabalhar com IDs específicas à solução, como a ID de visitante do Analytics.  [Mais...](https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html) |
| ID de visitante - Como a ID do visitante é definida quando os cookies estiverem bloqueados? | Se o cookie padrão s_vi estiver indisponível, um cookie de fallback é criado no domínio do sie com uma ID exclusiva gerada aleatoriamente. Esse cookie, chamado s_fid, é definido com uma validade de 2 anos e é usado como o método de identificação de fallback adiante.  [Mais...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html) |
| Dynamic Tag Management - por que minha regra de DTM não é acionada? | Se a sua regra baseada em eventos não é ativada, provavelmente há um problema com o seletor ou condição da regra. Localize o elemento em seu site em que a ação do evento desejado ocorre, clique com o botão direito do mouse e selecione Inspecionar elemento. Inspecione o script realçado na caixa que é aberta e verifique se você está direcionando o elemento correto.  [Mais...](https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html) |
| Como implementar o rastreamento de Video Heartbeat? | [Esta seção](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) contém instruções de download dos SDKs do Video Heartbeat e guias do desenvolvedor para a sua plataforma. Ao baixar o SDK, baixe também o guia do desenvolvedor localizado na página de documentos, pois ele contém instruções de implementação específicas para o Vídeo Heartbeat. |
| Como adicionar cookies ao subdomínio certo? | A variável cookieDomainPeriods determina o domínio em que os cookies s_cc e s_sq do Analytics são definidos, estabelecendo o número de períodos no domínio do URL da página. Essa variável também é usada por alguns plug-ins na determinação do domínio correto para definir o cookie do plug-in. See [Configuration Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html) |
| Servidor de rastreamento - Como preencher corretamente o servidor de rastreamento? | Ao configurar uma implementação para enviar dados aos servidores do Adobe Analytics, é preciso enviá-los ao local correto. Se isso não for feito, haverá uma inflação na contagem de visitantes ou perda de dados. [Mais...](https://helpx.adobe.com/analytics/kb/determining-data-center.html) |
| Desempenho: uma falha no carregamento do Adobe JavaScript externo devido a conexão com a Internet, proxy, firewall ou interrupção de serviço na Adobe pode prejudicar o desempenho? | Não. O arquivo JavaScript não fica hospedado nos servidores da Adobe, para que uma interrupção da Adobe não prejudique a execução. |
| Desempenho: o carregamento de um Adobe JavaScript externo pode gerar uma redução no desempenho? | O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e uma versão dele também é baixada ao menos uma vez por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, transferir o JavaScript que é usado várias vezes neste arquivo pode resultar em menos download de dados em geral. <br>Compactação de JavaScript para AppMeasurement: se estiver preocupado com o peso da página (tamanho) do cliente JavaScript da Adobe, a Adobe recomenda a compactação do arquivo usando GZIP. O GZIP é compatível com a maioria dos navegadores e oferece desempenho superior à compactação JavaScript para compactar e descompactar o arquivo JavaScript principal `s_code.js`. |
| Desempenho: o envio de dados de um navegador para os serviços da Adobe reduz o desempenho? | Os arquivos Adobe JavaScript criam um objeto de imagem dentro da página HTML e, em seguida, o navegador solicita o envio do objeto de imagem aos servidores da Adobe. Caso os servidores da Adobe fiquem lentos e com pouca capacidade de resposta, o thread responsável pela solicitação será adiado até que a imagem volte ou o tempo limite seja atingido. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar. |
| Desempenho: um evento de JavaScript da Adobe pode afetar o comportamento ou a funcionalidade do sistema? | Não. Consulte as respostas anteriores sobre desempenho. |
| Como faço para alterar os dados coletados, com base nas condições que eu definir? | Use as regras de processamento para simplificar a coleta de dados e o gerenciamento do conteúdo conforme é enviado para os relatórios.  ([Mais...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Qual é a versão mais recente do arquivo s_code? | Esta seção contém um histórico das versões das bibliotecas do AppMeasurement nas plataformas da Web e de dispositivos móveis. As versões mais recentes das bibliotecas podem ser baixadas em Analytics &gt; Administração &gt; Gerenciador de código. [Mais...](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md) |
| Como depurar o arquivo s_code? | O Experience Cloud Debugger é uma ferramenta gratuita oferecida pela Adobe, que permite a visualização dos dados coletados em seu site em qualquer página. [Mais...](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) |
| Como rastrear diferentes tipos de links? | É possível rastrear automaticamente os downloads de arquivo e links de saída com base nos parâmetros definidos no arquivo AppMeasurement para JavaScript. [Mais...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/function-tl.html) |
| Como rastrear vídeos? | O JavaScript pode ser utilizado para rastrear vários reprodutores. Para rastrear com o JavaScript, basta adicionar o código à página da Web que contém o reprodutor o rastreá-lo utilizando manipuladores de evento. [Mais...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| Como rastrear um aplicativo para dispositivos móveis? | É possível gerar links de aquisição com códigos de rastreamento exclusivos no Adobe Mobile Services. Quando um usuário baixa e executa um aplicativo da Apple App Store depois de clicar em um link gerado, o SDK coleta e envia automaticamente os dados de aquisição para o Adobe Mobile Services. [iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html), [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) |
| Como implementar o rastreamento de vídeo? | É possível rastrear reprodutores de mídia ao criar funções vinculadas aos manipuladores de evento do reprodutor de vídeo. Isso permite chamar Media.open, Media.play, Media.stop e Media.close no momento certo. [Mais...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| Como configurar o cookie primário? | O Analytics usa cookies para fornecer informações sobre variáveis e componentes que não persistem entre as solicitações de imagem e as sessões do navegador. Esses cookies inofensivos são originários de um domínio hospedado pela Adobe, conhecidos como cookies de terceiros. [Mais...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Como posso obter um certificado SSL? | Determine se seu site usa o protocolo `https://`. Se o fizer, é necessário solicitar um CSR e comprar um certificado SSL. Observação: não é necessário um certificado SSL se você não tem páginas ou conteúdos seguros. Esta etapa pode ser ignorada se você só usar o protocolo `https://` no site.  [Mais...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Onde encontro informações sobre o aviso de expiração da certificação? | Os certificados SSL expiram anualmente, o que significa que a Adobe exige uma solicitação de certificado atualizada sempre que isso acontece. O especialista FPC fornece os avisos necessários quando isso ocorre, no entanto, recomenda-se ser proativo no monitoramento da validade e no fornecimento à Adobe deste certificado atualizado. [Mais...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) |
| O que são plug-ins? | Os plug-ins do AppMeasurement para JavaScript são programas ou funções que executam várias funções avançadas. Esses plug-ins estendem a capacidade de seu arquivo JavaScript para fornecer a você mais funcionalidade do que a disponível com a implementação básica. A Adobe oferece diversos outros plug-ins como parte das soluções avançadas. Entre em contato com seu gerente de conta se você quiser capturar dados usando o JavaScript, mas se não tiver certeza sobre como proceder. [Mais...](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) |
| Como encontrar informações sobre a API de inserção de dados? | A Adobe criou várias maneiras de enviar dados para o Analytics. [Mais...](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
| O que é um erro 500? | Informações sobre o erro interno do servidor que causou o status "Erro de consulta 500" podem ser encontradas na variável [](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985)pageType. |
