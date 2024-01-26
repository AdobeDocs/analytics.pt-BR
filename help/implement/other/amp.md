---
title: Implementação com AMP
description: Implementar o Adobe Analytics em páginas AMP.
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 70%

---

# Implementação com AMP

O [AMP](https://amp.dev) é uma estrutura HTML de código aberto que fornece uma maneira simples de criar páginas da Web rápidas e com carregamento leve.

Como o Adobe Analytics usa uma biblioteca JavaScript para compilar e enviar uma solicitação de imagem, são necessários ajustes na implementação para enviar dados à Adobe nas páginas que usam o AMP.

## Determine que método deve ser implementado no Adobe Analytics em páginas que usam o AMP

A Adobe criou dois métodos para implementar o Adobe Analytics em páginas que usam o AMP. Ambos usam a tag HTML `<amp-analytics>`. Consulte [amp-analytics](https://amp.dev/pt_br/documentation/components/amp-analytics) na documentação da AMP para obter mais informações.

* **Use o `"adobeanalytics"` modelo**: construa a solicitação do Analytics diretamente na página
* **Use o `"analytics_nativeConfig"` modelo**: use um iframe que contenha o mesmo código de AppMeasurement implantado no site normal

A tabela a seguir compara estes dois métodos:

|   | **`"adobeanalytics"`modelo** | **`"adobeanalytics_nativeConfig"`modelo** |
|---|---|---|
| Contagem de visitante/visitas no conjunto de relatórios existente | Inflação alta | Inflação mínima |
| Usar um conjunto de relatórios separado | Recomendado | Não é necessário |
| Visitantes novos vs. retornos | Não suportado | Suportado |
| Serviço de ID de visitante | Não suportado | Suportado |
| Rastreamento de vídeo e link | Suporte parcial | Ainda não é suportado |
| Dificuldade da implementação | Difícil | Relativamente fácil |
| Integrações da Adobe Experience Cloud | Não suportado | Suporte parcial |

Considere os prós e os contras para que você possa escolher o melhor método de implementação para sua organização.

>[!WARNING]
>
>Não use os modelos `"adobeanalytics"` e `"adobeanalytics_nativeConfig"` na mesma página que usa o AMP. Se tentar fazer isso, poderá gerar erros no console do navegador, além de contar os visitantes duas vezes.

## Método 1: usar o `<amp-analytics>` com a tag `"adobeanalytics"` modelo

O modelo de rastreamento `"adobeanalytics"` usa a tag HTML `<amp-analytics>` para criar uma solicitação de rastreamento diretamente. Especifique as solicitações de ocorrência que são acionadas em eventos de página específicos, como a página se tornando visível ou em um clique. Eventos de clique podem ser personalizados para se aplicarem a certas IDs de elemento ou classes ao especificar um seletor. É possível carregar o modelo ao adicionar `type="adobeanalytics"` à tag amp-analytics.

No código de exemplo a seguir, há dois disparadores definidos: `pageLoad` e `click`. O acionador `pageLoad` é executado quando o documento se torna visível e inclui a variável `pageName`, conforme definido na seção `vars`. O segundo acionador `click` é acionado ao clicar em um botão. A variável `eVar1` para esse evento, é definida com o valor `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
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

A variável `<amp-analytics>` A tag do suporta substituições de variáveis para que o AMP possa fornecer valores de dados conhecidos. Consulte [variáveis compatíveis com o `amp-analytics`](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md) no GitHub para obter mais informações.

>[!NOTE]
>
>As solicitações de imagem enviadas ao Adobe usando esse método não incluem dados para muitos relatórios padrão (por exemplo, navegador, tamanho de tela ou referenciador). Se desejar incluir essas informações nas ocorrências, verifique se elas foram incluídas como parte da cadeia de caracteres de consulta da solicitação de imagem. Consulte [Parâmetros de consulta para coleta de dados](../validate/query-parameters.md) para obter uma lista completa de solicitações de imagem, consulte os parâmetros e suas variáveis associadas.

A Adobe identifica visitantes usando uma função AMP integrada e define o cookie `adobe_amp_id`. Essa ID de visitante é exclusiva de qualquer outra ID definida pelo Adobe Analytics. Um visitante único diferente é contado para cada CDN do qual um visitante recupera o conteúdo, o que pode aumentar a contagem de visitantes únicos. É altamente recomendado usar um conjunto de relatórios separado para páginas AMP devido à forma como o AMP identifica visitantes únicos. O serviço da Adobe Experience Cloud ID não é compatível.

Essa solução exige que o servidor de rastreamento seja especificado na propriedade `host` corresponda ao servidor de rastreamento no site principal, para que os controles da política de privacidade sejam respeitados. Caso contrário, crie uma política de privacidade separada para as páginas que usam AMP.

## Método 2: usar o `<amp-analytics>` com a tag `"adobeanalytics_nativeConfig"` modelo

A tag `"adobeanalytics_nativeConfig"` é mais fácil de implementar, pois usa a mesma metodologia de marcação usada nas páginas normais da Web. Adicione o seguinte à tag `amp-analytics`:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.data.adobedc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

Uma página HTML hospedada nos servidores da Web também é necessária:

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

Essa abordagem envia dados a uma página da Web de utilitário por meio de parâmetros de cadeias de caracteres de consulta especiais adicionados ao parâmetro de solicitação `iframeMessage`. Esses parâmetros de cadeias de caracteres de consulta podem ser nomeados quando desejar, contanto que a página `stats.html` esteja configurada para coletar os dados apropriados.

A variável `"adobeanalytics_nativeConfig"` O modelo também adiciona parâmetros da sequência de consulta com base nas variáveis listadas no `extraUrlParams` seção do `<amp-analytics>` tag. No exemplo acima, os parâmetros `pageName` e `v1` são incluídos.

>[!IMPORTANT]
>
>Sua página `stats.html` deve ser hospedada em um subdomínio separado do domínio em que o AMP está hospedado. A estrutura da AMP não permite iFrames do mesmo subdomínio no qual a AMP está. Por exemplo, se o AMP estiver hospedado no `amp.example.com`, hospede a página `stats.html` em um subdomínio separado, como o `ampmetrics.example.com`.

Usando esse método, se um usuário final optar por não ser rastreado no site primário, ele também deixará de ser rastreado em todos os AMPs sem etapas adicionais. Usar essa página de utilitários também significa que o AMP pode ser compatível com o serviço da Adobe Experience Cloud ID. Não é necessário um conjunto de relatórios separado.

O rastreamento de link e de vídeo não pode ser usado com este método. A tag `iframeMessage` no AMP só pode ser carregada uma vez por página, portanto, não é possível enviar outras solicitações de imagem depois que o quadro é carregado. Esse método também requer mais recursos de processamento para execução, o que pode afetar o desempenho da rolagem. Ele não afeta o tempo de carregamento da página, pois todos os recursos são carregados de forma assíncrona.

## Perguntas frequentes

**Como posso diferenciar visitantes AMP de outros em meus dados?**

Para todas as páginas AMP, a dimensão [!UICONTROL Versão do JavaScript] coleta um valor semelhante ao `AMP vX.X`. Também é possível definir uma dimensão personalizada como &quot;AMP&quot; para segmentar esses visitantes.

**Como esse método de implementação se compara aos Artigos Instantâneos do Facebook?**

Os Artigos Instantâneos do Facebook são compatíveis com uma solução semelhante ao método `"adobeanalytics_nativeConfig"`. A página `stats.html` desse método pode atender às necessidades de análise tanto para AMP quanto para FIA, simultaneamente. Para obter mais informações sobre como implementar o rastreamento no FIA, consulte [Artigos Instantâneos do Facebook](fb-instant-articles.md).
