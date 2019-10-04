---
description: 'null'
seo-description: 'null'
seo-title: Analytics para assistentes digitais
title: Analytics para assistentes digitais
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: de48a1211edd3a4fd35cc455f2002384deeed5be

---


# Implementação do Analytics para assistentes digitais

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

Com os recentes avanços na computação em nuvem, aprendizado de máquina e processamento de linguagem natural, os assistentes digitais estão se tornando parte do cotidiano. Os consumidores estão a começar a falar com os seus aparelhos e a esperar que eles compreendam e respondam de formas semelhantes às humanas. À medida que essas plataformas vão se consolidando, as marcas podem apresentar seus serviços aos consumidores dessa mesma forma realista. Por exemplo, os consumidores podem perguntar coisas como:

* "Alexa, pergunte ao meu carro quando será preciso trocar o óleo."
* "Cortana, qual é o saldo da minha conta corrente?"
* "Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário."

Esta página fornece uma visão geral de como usar o Adobe Analytics para medir e otimizar esses tipos de experiências.

## Visão geral da arquitetura da experiência digital

![](assets/Digital-Assitants.png)

A maioria dos assistentes digitais atuais segue uma arquitetura de alto nível semelhante:

1. **Dispositivo:** existe um dispositivo (como um Amazon Echo ou um telefone) com um microfone que permite ao usuário fazer uma pergunta.
1. **Assistente digital:** esse dispositivo interage com o serviço que possibilita o assistente digital. É onde o discurso é convertido em intenções compreensíveis por máquina e os detalhes da solicitação são analisados. Quando a intenção do usuário é compreendida, o assistente digital passa a intenção e os detalhes da solicitação para o aplicativo, que a processa.
1. **"Aplicativo":** pode ser um aplicativo no telefone ou um aplicativo de voz. O aplicativo é responsável por responder à solicitação. Ele responde ao assistente digital e o assistente digital responde ao usuário.

## Onde implementar o Analytics

Um dos melhores lugares para implementar o Analytics é no aplicativo. O aplicativo recebe a intenção e os detalhes do assistente digital e, em seguida, determina como responder.

Há duas vezes durante uma solicitação que pode ser útil para enviar dados ao Adobe Analytics.

1. Quando a solicitação for enviada para seu aplicativo.
1. Depois que a resposta é retornada do aplicativo.

Se você estiver interessado apenas em registrar o que aconteceu com o cliente para otimização futura, envie uma solicitação ao Adobe Analytics após a resposta ser retornada. Você terá o contexto completo do que era a solicitação e como o sistema respondeu.

## Novas instalações

Para alguns assistentes digitais, você recebe uma notificação quando alguém instala a habilidade, especialmente quando a autenticação está envolvida. A Adobe recomenda enviar um evento Install definindo a variável de dados de contexto `a.InstallEvent=1`. Este recurso não está disponível para todos os assistentes digitais, mas é útil quando está presente para analisar a retenção. A amostra de código a seguir envia os valores de evento Install, Data de instalação e AppID para as variáveis de dados de contexto.

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net" format="http" scope="external">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Vários assistentes ou vários aplicativos

É provável que sua organização queira aplicativos para várias plataformas. A prática recomendada é incluir uma ID de aplicativo com a solicitação. This variable can be set in the `a.AppID` context data variable. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Identificação do usuário/visitante

O Adobe Analytics usa o serviço [de identidade da](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud para unir interações ao longo do tempo à mesma pessoa. A maioria dos assistentes digitais retorna um item `userID` que você pode usar para manter a atividade para usuários diferentes. Na maioria dos casos, esse valor é o que você pode passar como um identificador exclusivo. Algumas plataformas retornam um identificador que tem mais de 100 caracteres. Nesses casos, a Adobe recomenda executar hash do identificador exclusivo para um valor de comprimento fixo usando um algoritmo de hash padrão, como MD5 ou Sha1.

O uso do serviço de ID fornece o maior valor ao mapear ECIDs em diferentes dispositivos (por exemplo, assistente da Web para dispositivos digitais). Se o aplicativo for móvel, use os SDKs da plataforma Experience como estão e envie a ID do usuário usando o `setCustomerID` método. No entanto, se o aplicativo for um serviço, use a ID do usuário fornecida pelo serviço como a ECID, bem como a configuração em `setCustomerID`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Sessões

Como os assistentes digitais são conversacionais, eles geralmente seguem o conceito de uma sessão. Por exemplo:

**Consumidor:** “Ok, Google, chame um táxi para mim”

**Google:** "Claro, a que horas você gostaria?"

**Consumidor:** “20h30”

**Google:** “Ótimo, o motorista chegará às 20h30”

As sessões são importantes para manter o contexto e ajudar a coletar mais detalhes para tornar o assistente digital mais natural. Ao implementar o Analytics em uma conversa, há duas coisas a serem feitas quando uma nova sessão é iniciada:

1. **Acessar o Audience Manager:** obtenha os segmentos relevantes dos quais um usuário faz parte para que você possa personalizar a resposta. (Por exemplo, essa pessoa está qualificada atualmente para o desconto de vários canais.)
2. **Enviar uma nova sessão ou um evento de lançamento:** ao enviar a primeira resposta ao Analytics, inclua um evento de lançamento. Normalmente, isso pode ser enviado definindo dados de contexto de `a.LaunchEvent=1`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Intenções

Cada um dos assistentes digitais possui algoritmos que detectam intenções e a transmitem para o “Aplicativo”, para que o aplicativo saiba o que fazer. Essas intenções são uma representação sucinta da solicitação.

Por exemplo, se um usuário disser: "Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário", a intenção pode ser algo como *sendMoney*.

Ao enviar cada uma dessas solicitações como uma eVar, você pode executar relatórios de definição de caminho em cada uma das intenções para aplicativos conversacionais. Certifique-se de que seu aplicativo possa lidar com solicitações sem um propósito também. A Adobe recomenda transmitir "Nenhum propósito especificado" para a variável de dados de contexto de intenção, em vez de omitir a variável.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

ou

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Parâmetros/Slots/Entidades

Além da intenção, os assistentes digitais muitas vezes têm um conjunto de pares chave/valor que dão detalhes da intenção. Eles podem ser chamados de slots, entidades ou parâmetros. Por exemplo, "Siri, Send John $20 for jantar ontem à noite do meu aplicativo bancário" teria os seguintes parâmetros:

* Quem = John
* Valor = 20
* Porquê = Jantar

Normalmente, há um número finito desses valores com seu aplicativo. Para rastrear esses valores no Analytics, envie-os para variáveis de dados de contexto e mapeie cada um dos parâmetros para uma eVar.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Estados de erro

Às vezes, o assistente digital fornece ao aplicativo entradas que ele não sabe como lidar. Por exemplo, "Siri, mande ao John 20 sacos de carvão para jantar ontem à noite do meu aplicativo bancário"

Quando esta situação ocorrer, peça ao seu aplicativo para obter esclarecimentos. Além disso, envie dados para a Adobe que indicam que o aplicativo tem um estado de erro junto com uma eVar que especifica que tipo de erro ocorreu. Certifique-se de incluir erros quando as entradas não estiverem corretas e erros nos quais o aplicativo teve um problema.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Recursos do dispositivo

Embora a maioria das plataformas não exponha o dispositivo ao qual o usuário falou, elas expõem os recursos do dispositivo. Por exemplo, Áudio, Tela, Vídeo etc. Essas informações são úteis porque definem os tipos de conteúdo que podem ser usados ao interagir com seus usuários. Ao medir as capacidades do dispositivo, é melhor concatená-las (em ordem alfabética).

Exemplo: `":Audio:Camera:Screen:Video:"`

Os dois pontos principais e posteriores ajudam a criar segmentos. Por exemplo, mostrar todas as ocorrências com `:Audio:` recursos.

* [Recursos](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) da Amazon usando o Amazon Alexa
* [Recursos](https://developers.google.com/actions/assistant/surface-capabilities) do Google usando ações no Google

## Exemplos

| Pessoa | Resposta do dispositivo | Ação/intenção | Solicitação GET |
| --- | --- | --- | --- | ---|
| Instalar Spoofify | Nenhuma resposta | Instalar | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Reproduzir o Spoofify | "Ok, jogando Spoofify" | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Trocar música | "Ok, que música você quer?" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Jogar "Baby Shark" | "Ok, tocando 'Baby Shark' de PinkFong" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Alterar lista de reprodução | "Ok, que lista de reprodução você quer?" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Reproduzir minha lista de músicas favorita | "Ok, tocando sua lista de músicas favoritas" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Desligar música | Sem resposta, a música desliga | Desligado | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
