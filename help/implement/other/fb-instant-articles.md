---
title: Implementação com Instant Articles do Facebook
description: Implemente o Adobe Analytics nas páginas Instant Articles do Facebook.
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Implementação com Instant Articles do Facebook

Os Instant Articles do Facebook permitem que os editores criem artigos rápidos e interativos no Facebook. Os Instant Articles podem carregar conteúdo em até 10 vezes mais rápido que a Web móvel.

Você pode incorporar o Adobe Analytics aos Instant Articles do Facebook para rastrear o comportamento do visitante. Como o conteúdo do editor está no aplicativo do Facebook e não nos sites do editor, a abordagem de marcação é um pouco diferente da implementação padrão do Analytics.

## Fluxo de trabalho

O fluxo de trabalho abrangente para implementar o Adobe Analytics é o seguinte:

1. Crie uma `stats.html` página. Programe esta página para obter parâmetros da string de consulta do URL e atribuir cada parâmetro a uma variável do Analytics
1.  Hospedar a `stats.html` página em seu servidor Web
1. Implemente o Analytics no Instant Article do Facebook fazendo referência ao arquivo em um `stats.html` iframe
1. Incluir parâmetros de sequência de consulta no `src` atributo iframe

### Etapa 1: Criar uma `stats.html` página

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

### Etapa 2: Hospedar a `stats.html` página em seu servidor Web

A Adobe recomenda hospedar sua `stats.html` página junto com a versão mais recente de `AppMeasurement.js` e `VisitorAPI.js`. Trabalhe com as equipes de engenharia apropriadas em sua organização para hospedar esse arquivo no local correto.

### Etapa 3: Referência `stats.html` em cada página de Instant Article do Facebook

Ao criar o conteúdo do Instant Article do Facebook, incorpore o conteúdo HTML de análise em um iframe. Por exemplo:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Etapa 4: Definir variável personalizada e rastreamento de eventos

As variáveis e os eventos personalizados podem ser rastreados dentro do HTML do Analytics por meio de duas abordagens diferentes:

* Inclua valores e eventos variáveis diretamente na `stats.html` página. As variáveis definidas aqui seriam as melhores para valores que normalmente são as mesmas para todos os Instant Articles do Facebook.
* Inclua valores variáveis como parte de uma string de consulta que faz referência ao iframe. Esse método permite que você envie valores variáveis do Instant Article do Facebook para o código de hospedagem do iframe do Analytics.

O exemplo a seguir mostra várias variáveis personalizadas incluídas em uma string de consulta. O JavaScript inside `stats.html` verificaria a string de consulta usando `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] A dimensão Referenciador não é rastreada automaticamente devido à natureza do iframes. Certifique-se de incluir essa dimensão como parte da sequência de caracteres de consulta se desejar acompanhá-la.

## Artigos instantâneos do Facebook e privacidade

Desde que a página HTML do Analytics esteja hospedada em seu servidor da Web, a Adobe oferece suporte à sua política de privacidade existente em todos os Instant Articles do Facebook. Se um usuário optar por não ser rastreado em seu site principal, ele também deixará de ser rastreado em todos os Instant Articles do Facebook. A página de utilitários também oferece suporte ao Adobe Experience Cloud Identity Service para que você possa integrar os dados do Instant Article do Facebook ao restante da Experience Cloud.
