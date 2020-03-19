---
title: Implementação com Instant Articles do Facebook
description: Implementar o Adobe Analytics nas páginas Instant Articles do Facebook.
translation-type: ht
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Implementação com Instant Articles do Facebook

Os Instant Articles do Facebook permitem que publicadores criem artigos rápidos e interativos no Facebook. Os Instant Articles podem carregar conteúdo em até 10 vezes mais rápido que a Web móvel.

Incorpore o Adobe Analytics aos Instant Articles do Facebook para rastrear o comportamento do visitante. Como conteúdo do editor está no aplicativo do Facebook e não nos sites do publicador, a abordagem de aplicação de tags é diferente do que ocorre na implementação padrão do Analytics.

## Fluxo de trabalho

O fluxo de trabalho abrangente para implementar o Adobe Analytics é o seguinte:

1. Crie uma página `stats.html`. Programe esta página para obter parâmetros da cadeia de caracteres de consulta do URL e atribuir cada parâmetro a uma variável do Analytics
1. Hospede a página `stats.html` no servidor da Web
1. Implemente o Analytics no Instant Article do Facebook fazendo referência ao arquivo `stats.html` em um iframe
1. Incluir parâmetros de cadeia de caracteres de consulta no atributo `src` do iframe

### Etapa 1: criar uma página `stats.html`

O HTML de exemplo abaixo pode ser usado para capturar dados de estatística dos artigos instantâneos. Normalmente, este artigo seria hospedado em um dos servidores da sua empresa. Cada vez que um Instant Article é carregado, ele carrega o arquivo em um iframe, que aciona o envio de dados para a Adobe.

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;

      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### Etapa 2: hospedar a página `stats.html` no servidor da Web

A Adobe recomenda hospedar sua página `stats.html` junto com a versão mais recente de `AppMeasurement.js` e `VisitorAPI.js`. Trabalhe com as equipes de engenharia da organização para hospedar esse arquivo no local correto.

### Etapa 3: referenciar `stats.html` em cada página do Instant Article do Facebook

Ao criar o conteúdo do Instant Articles do Facebook, incorpore o conteúdo de análise HTML em um iFrame. Por exemplo:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Etapa 4. definir a variável personalizada e o rastreamento de eventos

As variáveis personalizadas e os eventos podem ser rastreados no HTML de análise por meio de várias abordagens:

* Inclua valores e eventos variáveis diretamente na página `stats.html`. As variáveis definidas aqui seriam as melhores para valores que normalmente são os mesmos em todos os Instant Articles do Facebook.
* Inclua valores de variável como parte de uma cadeia de caracteres de consulta que faz referência ao iframe. Esse método permite enviar valores de variável do Instant Article do Facebook para o código de hospedagem do iframe do Analytics.

O exemplo a seguir mostra diversas variáveis personalizadas incluídas em uma cadeia de caracteres de consulta. O JavaScript no `stats.html` verificaria a cadeia de caracteres de consulta usando `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] A dimensão Referenciador não é rastreada automaticamente devido à natureza dos iframes. Certifique-se de incluir essa dimensão como parte da cadeia de caracteres de consulta se desejar rastreá-la.

## Instant Articles do Facebook e privacidade

Enquanto a página de HTML do Analytics estiver hospedada no seu servidor da Web, a Adobe pode oferecer suporte à política de privacidade nos Instant Articles do Facebook. Se um usuário optar por não ser rastreado no site principal, ele também deixará de ser rastreado em todos os Instant Articles do Facebook. A página de utilitários também oferece suporte ao Adobe Experience Cloud Identity Service para que você possa integrar os dados do Instant Article do Facebook ao restante da Experience Cloud.
