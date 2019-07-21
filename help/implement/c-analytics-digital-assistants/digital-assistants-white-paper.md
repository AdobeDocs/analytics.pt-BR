---
description: 'null'
seo-description: 'null'
seo-title: Implementar o Analytics para assistentes digitais
title: Implementar o Analytics para assistentes digitais
uuid: c 61 e 6 a 1 a-ec 08-4936-9053-5 f 57223 f 57 ff
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Implementar o Analytics para assistentes digitais

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

Com os recentes avanços em computação em nuvem, aprendizado de máquina e processamento em linguagem natural, os assistentes digitais estão saindo da era das trevas e se tornando parte da vida cotidiana. Os consumidores estão começando a conversar com seus dispositivos e esperando que eles ouçam, compreendam e respondam de maneira natural e humana a frases como “Alexa, acenda as luzes da sala” ou “Ok, Google, como está o tempo lá fora?”.

À medida que essas plataformas vão se consolidando, as marcas podem apresentar seus serviços aos consumidores dessa mesma forma realista. Por exemplo, os consumidores podem perguntar coisas como:

* "Alexa, pergunte ao meu carro quando será preciso trocar o óleo."
* "Cortana, qual é o saldo da minha conta corrente?"
* "Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário."

Este white paper fornece uma visão geral de como usar melhor a Adobe Analytics Cloud para medir e otimizar esses tipos de experiências.

## Visão geral da arquitetura de experiência digital {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

A maioria dos assistentes digitais atuais segue uma arquitetura de alto nível semelhante:

1. **Dispositivo:** existe um dispositivo (como um Amazon Echo ou um telefone) com um microfone que permite ao usuário fazer uma pergunta.
1. **Assistente digital:** esse dispositivo interage com o serviço que possibilita o assistente digital. O serviço é onde boa parte da mágica acontece. É onde o discurso é convertido em intenções compreensíveis por máquina e os detalhes da solicitação são analisados. Quando a intenção do usuário é compreendida, o assistente digital passa a intenção e os detalhes da solicitação para o aplicativo, que a processa.
1. **"Aplicativo":** pode ser um aplicativo no telefone ou um aplicativo de voz. O aplicativo é responsável por responder à solicitação. Ele responde ao assistente digital e o assistente digital responde ao usuário.

## Onde implementar o Analytics {#concept_F53A0566589042658DEA5B86B22C10CB}

Um dos melhores lugares para implementar o Analytics é no aplicativo. O aplicativo recebe a [intenção](../../implement/c-analytics-digital-assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A) e seus detalhes do assistente digital e decide como responder.

Há duas ocasiões no ciclo de vida de uma solicitação nas quais pode ser útil chamar a Analytics Cloud.

1. Quando a solicitação é enviada ao “Aplicativo”. Se você precisar de contexto adicional sobre o usuário antes de responder à solicitação, aproveite o recurso do Audience Manager para obter os segmentos aos quais ele pertence.
1. Depois que a resposta é retornada do aplicativo. Se você estiver interessado apenas em registrar o que aconteceu com o cliente para otimização futura, envie uma solicitação ao Adobe Analytics após a resposta ser retornada. Dessa forma, você terá o contexto completo da solicitação e como o sistema respondeu.

## Novas instalações {#section_FD63267479DB47C2A081244A3E65A0CC}

Para alguns assistentes digitais, você receberá uma notificação quando alguém instalar a habilidade. Principalmente quando envolver autenticação. Neste momento, você deve enviar um evento *`Install`*&#x200B;à Adobe, definindo os dados de contexto para `a.InstallEvent=1`. Observe que isso não está disponível em todas as plataformas, mas é útil quando está para observar a retenção. A amostra de código a seguir envia *`Install`*, *`Install Date`* e *`AppID`*.

**Amostra de código**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="https: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="https:>
```

## Vários assistentes ou vários aplicativos {#section_81740741752E4142BE42DA4C9DDEEDF5}

É provável que você desenvolva aplicativos para várias plataformas. A prática recomendada é incluir uma ID de aplicativo com a solicitação. Ela pode ser definida nos dados de contexto `a.AppID`. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**Amostra de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Identificação de usuário/visitante {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. Na maioria dos casos, é isso que você deve transmitir como o serviço ECID. Algumas plataformas retornam um *`userID`* que ultrapassa o limite de 100 caracteres permitidos pelo Analytics. If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

Embora você possa usar o serviço ECID para isso, ele apenas fornecerá valor se você estiver tentando mapear ECIDs em diferentes dispositivos (por exemplo, da Web ao assistente digital). Se o aplicativo for um aplicativo para dispositivos móveis (por exemplo, um deep link), você deverá usar o SDK como está e enviar as informações adiante. O *`userID`* pode ser anexado ao serviço ECID usando o método setCustomerID, permitindo uma melhor combinação com o dispositivo. However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. Isso permite ver como as pessoas usam o assistente digital ao longo do tempo.

**Amostra de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Sessões {#section_BA4F996F976043B8993F2F7D24FE27FB}

Como os assistentes digitais são conversacionais, eles geralmente seguem o conceito de uma sessão. Por exemplo:

**Consumidor:** “Ok, Google, chame um táxi para mim”

**Google:** "Claro, a que horas você gostaria?"

**Consumidor:** “20h30”

**Google:** “Ótimo, o motorista chegará às 20h30”

Essas sessões são importantes para manter o contexto. Elas ajudam a obter mais detalhes e tornam os assistentes digitais mais naturais.

Ao implementar o Analytics em uma conversa, há duas coisas que você deve fazer quando uma nova sessão for iniciada:

1. **Acessar o Audience Manager:** obtenha os segmentos relevantes dos quais um usuário faz parte para que você possa personalizar a resposta. (Por exemplo, essa pessoa está qualificada atualmente para o desconto de vários canais.)
1. **Enviar uma nova sessão ou um evento de lançamento:** ao enviar a primeira resposta ao Analytics, inclua um evento de lançamento. Normalmente, isso pode ser enviado definindo dados de contexto de `a.LaunchEvent=1`.

**Amostra de código para[!DNL Launch, by Adobe]**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Intenções {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

Cada um dos assistentes digitais possui algoritmos que detectam intenções e a transmitem para o “Aplicativo”, para que o aplicativo saiba o que fazer. Essas intenções são uma representação sucinta da solicitação.

Por exemplo, se um usuário disser: "Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário", a intenção pode ser algo como *`sendMoney`*.

Ao enviar cada uma dessas solicitações como uma eVar, você poderá executar relatórios de definição de caminho cada uma das intenções para aplicativos de conversação. Você também desejará garantir que o "Aplicativo" possa processar solicitações sem uma intenção. Recomendamos transmitir *`No Intent Specified`* em vez de deixar o valor em branco.

**Amostra de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

ou

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Parâmetros/Slots/Entidades {#section_041CD1730F9E4096BE75DFF2CC810852}

Além da intenção, o assistente digital geralmente terá um conjunto de pares de valores-chave que fornecem os detalhes da intenção. Eles são chamados de slots, entidades ou parâmetros. Por exemplo:

"Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário" teria os seguintes parâmetros:

* Quem = John
* Valor = 20
* Porquê = Jantar

Normalmente, há um número finito deles no seu aplicativo. Para rastreá-los no Analytics, envie-os com os dados de contexto e mapeie cada um dos parâmetros a uma eVar.

**Amostra de código**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Sessão {#section_17D69D6B298E46E88E175F62F1ACD831}

Embora nem todos os aplicativos gerem receita, é importante pensar no que seria sucesso e incluir algumas medidas para isso. O Adobe Analytics pode medir receita, impressões de anúncios e outras formas de sucesso, juntamente com o comportamento do usuário.

## Estados de erro {#section_E8EFF8D610B24DC899C34E50B058864D}

Às vezes, o Assistente digital fornecerá ao aplicativo entradas que ele não sabe processar. Por exemplo.

"Siri, transfira 20 sacos de carvão para John pelo jantar de ontem à noite através do meu aplicativo bancário"

Quando isso acontece, o aplicativo deve pedir esclarecimentos. Além disso, quando estiver respondendo a uma solicitação como essa, você deverá enviar ao Analytics um evento que indique que o aplicativo está em um estado de erro junto com uma evar que especifique o tipo de erro ocorrido.

Certifique-se de incluir erros nos quais as entradas não estejam corretas e erros nos quais o "Aplicativo" teve um problema.

**Amostra de código**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## Recursos do dispositivo {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

Embora a maioria das plataformas não revele o dispositivo real com o qual o usuário falou, elas revelam os recursos do dispositivo, como as interfaces disponíveis (por exemplo, áudio, tela, vídeo, etc.). Essa é uma informação útil porque define os tipos de conteúdo que podem ser usados ao interagir com seus usuários. Ao medir as interfaces, é melhor concatená-las (em ordem alfabética).

Exemplo: `:Audio:Camera:Screen:Video:`

Observe os dois-pontos à esquerda e entre os itens. These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Recursos da Amazon: [https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Recursos do Google: [https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## Relatórios do Analytics para assistentes digitais {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

Depois da implementação do aplicativo de assistente digital, você poderá usar todos os recursos do Adobe Analytics com ele. Aqui estão apenas alguns exemplos do que você pode fazer com o Analytics.

## Monitorar intenções {#section_6632D9F2EF9045A7A1A4263D3561C78F}

A maioria dos aplicativos apresenta várias intenções e coisas diferentes que você pode fazer. You could easily use [!UICONTROL Analysis Workspace] to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

Isso permite ver quais recursos são usados com mais frequência e pode fornecer uma visão da adoção de novos recursos.

## Solicitações com erros {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

Você poderá monitorar os erros para ver se há um lugar em comum no qual os usuários estão tendo problemas.

<!-- 

<p>--- Image of Errors --- </p>

 -->

## Fluxo entre eventos {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

Uma das coisas mais poderosas a fazer é observar o fluxo de intenções. Isso é útil de duas maneiras: Primeiro, você pode ver em uma sessão como as pessoas fluem entre as intenções em uma conversa. Segundo, você pode ver como as pessoas fluem entre as intenções em intervalos de tempo mais longos para ver como o uso do “Aplicativo” está evoluindo.

## Exemplo {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**Aplicativo pré-instalado**

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pessoa </th> 
   <th colname="col2" class="entry"> Resposta do dispositivo </th> 
   <th colname="col3" class="entry"> Ação/intenção </th> 
   <th colname="col4" class="entry"> Solicitação Get </th> 
   <th colname="col5" class="entry"> Dados do Analytics </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reproduzir o Spoofify </p> </td> 
   <td colname="col2"> <p> "ok reproduzindo o Spoofify" </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. a. launchevent = 1 &amp; c. Intent = Play &amp; pagename = playapp HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">ID de visitante </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">Versão do aplicativo </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10">Número de inicializações </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">Intenção </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Trocar música </p> </td> 
   <td colname="col2"> <p> “ok, que música você deseja?” </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changesong &amp; pagename = askforsong HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">ID de visitante </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">Versão do aplicativo </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">Intenção </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">*lista de reprodução vazia </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduzir “My Heart Will Go On” da Celine Dion </p> </td> 
   <td colname="col2"> <p> “ok, reproduzindo ‘My Heart Will Go On’ da Celine Dion” </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplaysong &amp; c. songid = [012345] HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">ID de visitante </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">Versão do aplicativo </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">Intenção </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">ID da música </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Alterar lista de reprodução </p> </td> 
   <td colname="col2"> <p> “ok, que lista de reprodução você deseja?” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = askforplaylist HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">ID de visitante </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">Versão do aplicativo </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">Intenção </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">*lista de reprodução vazia </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduzir Usher </p> </td> 
   <td colname="col2"> <p> “ok, reproduzindo Usher” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplayplaylist &amp; c. Playlist = Usher HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">ID de visitante </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">Versão do aplicativo </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">Intenção </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">Lista de reprodução </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Desligar música </p> </td> 
   <td colname="col2"> <p> *sem resposta, a música desliga </p> </td> 
   <td colname="col3"> <p> Desligado </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Propósito = Desativado &amp; pagename = turnsoffmusic HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">ID de visitante </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">Versão do aplicativo </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">Intenção </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exige que o usuário instale o aplicativo**

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pessoa </th> 
   <th colname="col2" class="entry"> Resposta do dispositivo </th> 
   <th colname="col3" class="entry"> Ação/intenção </th> 
   <th colname="col4" class="entry"> Solicitação Get </th> 
   <th colname="col5" class="entry"> Dados do Analytics </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Instalar Spoofify </p> </td> 
   <td colname="col2"> <p> *sem resposta </p> </td> 
   <td colname="col3"> <p> Instalar </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; amp; amp; c. a. installevent = 1 &amp; c. a. installdate = 2017-04-24 &amp; c. a. appid = Spoofify 1.0 &amp; c. ostype = Alexa &amp; c. Intent = Install &amp; pagename = Install HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">ID de visitante </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">Data </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">Intenção </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">Versão do SO </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduzir o Spoofify </p> </td> 
   <td colname="col2"> <p> "ok reproduzindo o Spoofify" </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. a. launchevent = 1 &amp; c. Intent = Play &amp; pagename = playapp HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">ID de visitante </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">Versão do aplicativo </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C">Número de inicializações </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">Intenção </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Trocar música </p> </td> 
   <td colname="col2"> <p> “ok, que música você deseja?” </p> </td> 
   <td colname="col3"> <p>ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changesong &amp; pagename = askforsong HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">ID de visitante </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">Versão do aplicativo </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">Intenção </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">*lista de reprodução vazia </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduzir “My Heart Will Go On” da Celine Dion </p> </td> 
   <td colname="col2"> <p> “ok, reproduzindo ‘My Heart Will Go On’ da Celine Dion” </p> </td> 
   <td colname="col3"> <p> ChangeSong </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplaysong &amp; c. songid = [012345] HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">ID de visitante </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">Versão do aplicativo </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">Intenção </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">ID da música </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Alterar lista de reprodução </p> </td> 
   <td colname="col2"> <p> “ok, que lista de reprodução você deseja?” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = askforplaylist HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">ID de visitante </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">Versão do aplicativo </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">Intenção </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">*lista de reprodução vazia </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Reproduzir Usher </p> </td> 
   <td colname="col2"> <p> “ok, reproduzindo Usher” </p> </td> 
   <td colname="col3"> <p> ChangePlaylist </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Intent = changeplaylist &amp; pagename = actionplayplaylist &amp; c. Playlist = Usher HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">ID de visitante </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">Versão do aplicativo </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">Intenção </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">Lista de reprodução </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Desligar música </p> </td> 
   <td colname="col2"> <p> *sem resposta, a música desliga </p> </td> 
   <td colname="col3"> <p> Desligado </p> </td> 
   <td colname="col4"> 
    <code>GET /b/ss/ [rsid]/0? vid = [userid] &amp; c. a. appid = Spoofify 1.0 &amp; c. Propósito = Desativado &amp; pagename = turnsoffmusic HTTP/1.1 
 Host: sc. omtrdc. net 
 Controle de cache: no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">ID de visitante </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">Versão do aplicativo </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">Intenção </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">Resposta </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

