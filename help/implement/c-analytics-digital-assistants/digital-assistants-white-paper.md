---
description: 'null'
title: Analytics para assistentes digitais
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementar o Analytics para assistentes digitais

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

Com os recentes avanços na computação em nuvem, aprendizado de máquina e processamento de linguagem natural, os assistentes digitais estão fazendo parte do cotidiano. Os consumidores estão começando a falar com os seus aparelhos e a esperar que eles compreendam e respondam de formas semelhantes às humanas. À medida que essas plataformas vão se consolidando, as marcas podem apresentar seus serviços aos consumidores dessa mesma forma realista. Por exemplo, os consumidores podem perguntar coisas como:

* "Alexa, pergunte ao meu carro quando será preciso trocar o óleo."
* "Cortana, qual é o saldo da minha conta corrente?"
* "Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário."

Esta página fornece uma visão geral de como usar melhor o Adobe Analytics para medir e otimizar esses tipos de experiências.

## Visão geral da arquitetura de experiência digital

![](assets/Digital-Assitants.png)

A maioria dos assistentes digitais atuais segue uma arquitetura de alto nível semelhante:

1. **Dispositivo:** existe um dispositivo (como um Amazon Echo ou um telefone) com um microfone que permite ao usuário fazer uma pergunta.
1. **Assistente digital:** esse dispositivo interage com o serviço que possibilita o assistente digital. É onde o discurso é convertido em intenções compreensíveis por máquina e os detalhes da solicitação são analisados. Quando a intenção do usuário é compreendida, o assistente digital passa a intenção e os detalhes da solicitação para o aplicativo, que a processa.
1. **"Aplicativo":** pode ser um aplicativo no telefone ou um aplicativo de voz. O aplicativo é responsável por responder à solicitação. Ele responde ao assistente digital e o assistente digital responde ao usuário.

## Onde implementar o Analytics

Um dos melhores lugares para implementar o Analytics é no aplicativo. O aplicativo recebe a intenção e os detalhes do assistente digital e, em seguida, determina como responder.

Dois momentos durante uma solicitação podem ser úteis para enviar dados ao Adobe Analytics.

1. Quando a solicitação é enviada ao aplicativo.
1. Depois que a resposta é retornada do aplicativo.

Se você estiver interessado apenas em registrar o que aconteceu com o cliente para otimização futura, envie uma solicitação ao Adobe Analytics após a resposta ser retornada. Você terá o contexto completo da solicitação e como o sistema respondeu.

## Novas instalações

Em alguns assistentes digitais, você recebe uma notificação quando alguém instala a habilidade, especialmente quando a autenticação está envolvida. A Adobe recomenda enviar um evento Instalar ao definir a variável de dados de contexto `a.InstallEvent=1`. Esse recurso não está disponível em todos os assistentes digitais, mas é útil quando está presente para observar a retenção. A amostra de código a seguir envia os valores de evento Instalar, Data de instalação e AppID para as variáveis de dados de contexto.

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Vários assistentes ou vários aplicativos

É provável que sua empresa queira aplicativos para várias plataformas. A prática recomendada é incluir uma ID de aplicativo com a solicitação. Essa variável pode ser definida nos dados de contexto `a.AppID`. Siga o formato do `[AppName] [BundleVersion]`, por exemplo, BigMac para Alexa 1.2:

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

## Identificação de usuário/visitante

O Adobe Analytics usa o [Serviço de identidade da Adobe Experience Cloud](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html) para unir interações ao longo do tempo a mesma pessoa. A maioria dos assistentes digitais retorna um item `userID` que pode ser usado para manter a atividade para usuários diferentes. Na maioria dos casos, esse valor é o que você pode transmitir como um identificador exclusivo. Algumas plataformas retornam um identificador que tem mais de 100 caracteres. Nesses casos, a Adobe recomenda executar o hash do identificador exclusivo para um valor de comprimento fixo usando um algoritmo de hash padrão, como MD5 ou Sha1.

O uso do serviço de ID fornece maior valor ao mapear ECIDs em diferentes dispositivos (por exemplo, assistente da Web para dispositivos digitais). Se o aplicativo for móvel, use os SDKs da Experience Platform como estão e envie a ID do usuário usando o método `setCustomerID`. No entanto, se o aplicativo for um serviço, use a ID de usuário fornecida pelo serviço, como ECID, bem como a configuração na `setCustomerID`.

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

As sessões são importantes para manter o contexto e ajudar a coletar mais detalhes, de forma a tornar o assistente digital mais natural. Ao implementar o Analytics em uma conversa, há duas coisas a se fazer quando uma nova sessão for iniciada:

1. **Acessar o Audience Manager:** obtenha os segmentos relevantes dos quais um usuário faz parte para que você possa personalizar a resposta. (Por exemplo, essa pessoa está qualificada atualmente para o desconto de vários canais.)
2. **Enviar uma nova sessão ou um evento de lançamento:** ao enviar a primeira resposta ao Analytics, inclua um evento de lançamento. Normalmente, isso pode ser enviado definindo dados de contexto de `a.LaunchEvent=1`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Intenções

Cada um dos assistentes digitais possui algoritmos que detectam intenções e a transmitem para o “Aplicativo”, para que o aplicativo saiba o que fazer. Essas intenções são uma representação sucinta da solicitação.

Por exemplo, se um usuário disser: "Siri, transfira $20 para John pelo jantar de ontem à noite através do meu aplicativo bancário", a intenção pode ser algo como  *sendMoney*.

Ao enviar cada uma dessas solicitações como uma eVar, você poderá executar relatórios de definição de caminho cada uma das intenções para aplicativos de conversação. Certifique-se de que seu aplicativo possa lidar com solicitações sem um propósito também. A Adobe recomenda transmitir "Nenhum propósito especificado" para a variável de dados de contexto de intenção, em vez de a omitir.

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

Além da intenção, os assistentes digitais geralmente terão um conjunto de pares de valore/chave que fornecem os detalhes da intenção. Eles podem ser chamados de slots, entidades ou parâmetros. Por exemplo, "Siri, transfira $20 para John pelo jantar de ontem à noite pelo meu aplicativo bancário" teria os seguintes parâmetros:

* Quem = John
* Valor = 20
* Porquê = Jantar

Normalmente, há um número finito deles no seu aplicativo. Para rastrear esses valores no Analytics, envie-os com as variáveis de dados de contexto e mapeie cada um dos parâmetros a uma eVar.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Estados de erro

Às vezes, o assistente digital fornecerá ao aplicativo entradas que ele não sabe processar. Por exemplo, "Siri, transfira 20 sacos de carvão para John pelo jantar de ontem à noite pelo meu aplicativo bancário"

Quando esta situação ocorrer, peça ao seu aplicativo para obter esclarecimentos. Além disso, envie dados para a Adobe que indicam que o aplicativo tem um estado de erro junto com uma eVar que especifica o tipo de erro ocorrido. Certifique-se de incluir erros nos quais as entradas não estejam corretas e erros nos quais o aplicativo teve um problema.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Recursos do dispositivo

Embora a maioria das plataformas não exponha o dispositivo ao qual o usuário falou, elas mostram os recursos do dispositivo. Por exemplo, Áudio, Tela, Vídeo etc. Essa informação é útil porque define os tipos de conteúdo que podem ser usados ao interagir com seus usuários. Ao medir os recursos do dispositivo, é melhor concatená-los (em ordem alfabética).

Exemplo: `":Audio:Camera:Screen:Video:"`

Dois pontos anteriores e posteriores ajudam a criar segmentos. Por exemplo, mostrar todas as ocorrências com recursos `:Audio:`.

* [Recursos da Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) usando o Amazon Alexa
* [Recursos do Google](https://developers.google.com/actions/assistant/surface-capabilities) usando ações no Google

## Exemplos

| Pessoa | Resposta do dispositivo | Ação/intenção | Solicitação Get |
| --- | --- | --- | --- | ---|
| Instalar Spoofify | Sem resposta | Instalar | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Reproduzir o Spoofify | "Ok reproduzindo o Spoofify" | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Trocar música | “Ok, que música você deseja?” | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Tocar "Baby Shark" | "Ok, tocando 'Baby Shark' de PinkFong" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Alterar lista de reprodução | “Ok, que lista de reprodução você deseja?” | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Reproduzir minha lista de músicas favorita | "Ok, tocando sua lista de músicas favoritas" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Desligar música | Sem resposta, a música desliga | Desligado | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
