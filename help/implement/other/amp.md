---
title: Implementação com AMP
description: Implemente o Adobe Analytics em páginas AMP.
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# Implementação com AMP

[AMP](https://amp.dev) é uma estrutura HTML de código aberto que fornece uma maneira simples de criar páginas da Web rápidas e com carregamento suave.

Como o Adobe Analytics usa uma biblioteca JavaScript para compilar e enviar uma solicitação de imagem, os ajustes são necessários na sua implementação para enviar dados para a Adobe nas páginas que usam a AMP.

## Determine que método deve ser implementado no Adobe Analytics em páginas usando AMP

A Adobe criou dois métodos para implementar o Adobe Analytics em páginas usando AMP. Ambos usam a tag `<amp-analytics>` HTML. Consulte a tag [](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) amp-analytics no GitHub do projeto ampproject para obter mais informações.

* **Use o modelo`"adobeanalytics"`de** rastreamento: Construa a solicitação do Analytics diretamente na página
* **Use o modelo`"analytics_nativeConfig"`de** rastreamento: Use um iframe que contenha o mesmo código do AppMeasurement que você implantou no site normal

A tabela a seguir compara esses dois métodos:

|  | **modelo &quot;adobeanalytics&quot;** | **modelo &quot;adobeanalytics_nativeConfig&quot;** |
|---|---|---|
| Contagem de visitantes/visitas no conjunto de relatórios existente | Inflação alta | Inflação mínima |
| Usar um conjunto de relatórios separado | Recomendado | Não é necessário |
| Visitantes novos vs. retornos | Não suportado | Suportado |
| Serviço de ID de visitante | Não suportado | Suportado |
| Rastreamento de vídeo e link | Suporte parcial | Ainda não é suportado |
| Dificuldade da implementação | Um pouco difícil | Relativamente fácil |
| Integrações da Adobe Experience Cloud | Não suportado | Suporte parcial |

Ponha os prós e os contras em sua organização para determinar qual método você deseja usar. Consulte exemplos [de](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) AMP no repositório GitHub da Adobe para obter exemplos de código.

> [!WARNING] Não use os modelos `"adobeanalytics"` e `"adobeanalytics_nativeConfig"` na mesma página usando AMP. Se você tentar fazer isso, poderá gerar erros no console do navegador e contar os visitantes duas vezes.

## Método 1: Use a tag amp-analytics com o modelo &quot;adobeanalytics&quot;

The `"adobeanalytics"` tracking template uses the `<amp-analytics>` HTML tag to construct a tracking request directly. Você pode especificar solicitações de ocorrência que são acionadas em eventos de página específicos, como a página se tornando visível ou em um clique. Eventos de clique podem ser personalizados para se aplicarem a certas IDs de elemento ou classes ao especificar um seletor. É possível carregar o modelo ao adicionar `type="adobeanalytics"` à tag amp-analytics.

No código de exemplo a seguir, há dois disparadores definidos: `pageLoad` e `click`. O `pageLoad` disparador é acionado quando o documento se torna visível e inclui a `pageName` variável conforme definido na `vars` seção. The second trigger `click` fires when a button is clicked. `eVar1` é definida para esse evento com o valor `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
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

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and is automatically set to denote this hit as a link tracking call.

Além disso, o `amp-analytics` suporta uma quantidade de substituições para as variáveis, para que o AMP possa fornecer valores de dados conhecidos. Consulte [variáveis compatíveis com amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) no GitHub para obter mais informações.

> [!NOTE] As solicitações de imagem enviadas para a Adobe usando esse método não incluem dados para muitos relatórios padrão (por exemplo, navegador, tamanho de tela ou referenciador). Se desejar incluir essas informações nas ocorrências, verifique se elas foram incluídas como parte da string de consulta da solicitação de imagem. Consulte [Parâmetros de consulta de coleta de dados](../validate/query-parameters.md) para obter mais informações.

A Adobe identifica visitantes usando uma função AMP integrada e define o cookie `adobe_amp_id`. Essa ID de visitante é exclusiva de qualquer outra ID definida pelo Adobe Analytics (por exemplo, o `s_vi` cookie). O serviço da Adobe Experience Cloud ID não é compatível com esse método de implementação.

> [!NOTE] A AMP usa CDNs para fornecer conteúdo. É estruturado para contar um visitante único diferente para cada CDN do qual um visitante recupera o conteúdo, o que pode aumentar a contagem de visitantes únicos.

O uso de um conjunto de relatórios separado para páginas AMP é recomendado por causa de como a AMP identifica visitantes únicos.

This solution requires that the tracking server you specify in the `host` property matches the tracking server on your main site, so that your existing privacy policy controls are respected. Caso contrário, crie uma política de privacidade separada para as páginas que usam AMP.

## Método 2: Use a tag amp-analytics com o modelo &quot;adobeanalytics_nativeConfig&quot;

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it uses the same tagging methodology you use on your normal web pages. Adicione o seguinte à sua `amp-analytics` tag:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

Uma página HTML hospedada em seus servidores da Web também é necessária:

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
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
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

This approach sends data to a utility web page through query string parameters added to the `iframeMessage` request parameter. These query string parameters can be named whatever you like, as long as your `stats.html` page is configured to collect data from them.

O modelo `"adobeanalytics_nativeConfig"` também adiciona parâmetros da sequência de consulta com base nas variáveis listadas na seção `extraUrlParams` da tag amp-analytics. No exemplo acima, os parâmetros `pageName` e `v1` são incluídos.

> [!IMPORTANT] Sua `stats.html` página deve ser hospedada em um subdomínio separado do domínio em que a AMP está hospedada. A estrutura da AMP não permite iframes do mesmo subdomínio no qual a AMP está. Por exemplo, se sua AMP estiver hospedada `amp.example.com`, hospede sua `stats.html` página em um subdomínio separado, como `ampmetrics.example.com`.

Usando esse método, se um usuário optar por não ser rastreado no site principal, ele também deixará de ser rastreado em todas as suas AMPs. Usar essa página de utilitários também significa que a AMP pode suportar o serviço da Adobe Experience Cloud ID. Não é necessário um conjunto de relatórios separado.

O rastreamento de link e de vídeo não podem ser usados com este método. A `iframeMessage` tag na AMP só pode ser carregada uma vez por página, portanto, não é possível enviar outras solicitações de imagem depois que o quadro é carregado. Esse método também requer mais recursos de processamento para execução, o que pode afetar o desempenho da rolagem. Esse método não afeta o tempo de carregamento da página, pois todos os recursos são carregados de forma assíncrona.

## Perguntas frequentes

**O rastreamento de vídeo está disponível para qualquer método?**

Não. O padrão AMP suporta apenas acionadores para &quot;visível&quot;, &quot;clique&quot; e &quot;timer&quot;. Ele ainda não oferece suporte a acionadores explícitos para rastreamento de vídeo que a `amp-analytics` tag pode escutar. Além disso, o `"adobeanalytics_nativeConfig"` modelo só pode ser carregado uma vez, de modo que as solicitações de imagem subsequentes após o carregamento de uma página não são possíveis.

**Como posso diferenciar visitantes AMP de outros em meus dados?**

Para todas as páginas AMP, a dimensão Versão [!UICONTROL do] JavaScript coleta um valor semelhante ao `AMP vX.X`. Você também pode definir uma dimensão personalizada como &quot;AMP&quot; para segmentar esses visitantes.

**Como esse método de implementação se compara aos Instant Articles do Facebook?**

Os Instant Articles do Facebook suportam uma solução semelhante ao `"adobeanalytics_nativeConfig"` método. A `stats.html` página desse método pode atender às suas necessidades de análise tanto para AMP quanto para FIA simultaneamente. Para obter mais informações sobre como implementar o rastreamento no FIA, consulte Instant Articles [do](fb-instant-articles.md)Facebook.
