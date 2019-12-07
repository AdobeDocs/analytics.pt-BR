---
description: Como implementar o Analytics no Instant Articles do Facebook.
keywords: Analytics Implementation;embed;custom variable;custom event;visitor tracking;tracking;limitations
title: Instant Articles do Facebook
topic: Developer and implementation
uuid: 04b6366b-7c52-4dae-b2dd-bb6b78fd409c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Instant Articles do Facebook

Como implementar o Analytics no Instant Articles do Facebook.

Instant Articles do Facebook é um novo método para editores criarem artigos rápidos e interativos no Facebook. Os Instant Articles podem carregar conteúdo em até 10 vezes mais rápido que a Web móvel.

O Adobe Analytics pode ser incorporado nos Instant Articles do Facebook para rastrear o comportamento de visitantes conforme interagem com o conteúdo. Devido ao conteúdo do editor estar no aplicativo do Facebook e não no site dele, a abordagem de aplicação de tags é diferente do que ocorre na implementação padrão do Analytics.

## Etapa 1. Incorpore uma página HTML do Analytics {#section_0DF847F8BA624CF8A239C10003A39E59}

Ao criar o conteúdo dos Instant Articles do Facebook, você pode incorporar o conteúdo de análise HTML em um iFrame. Por exemplo:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## Etapa 2. Modifique o seu HTML do Analytics {#section_76707B51D63A47FF833C2D3FFF8412B4}

O HTML de exemplo abaixo pode ser usado para capturar dados de estatística dos artigos instantâneos. Normalmente, este artigo seria hospedado em um dos servidores da sua empresa. Cada vez que um Instant Article é carregado, o arquivo é carregado em um iframe, como apresentado na primeira etapa, o que aciona o envio de dados analíticos para a Adobe.

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**Como modificar o HTML de exemplo para a sua implementação específica**

1. É recomendado que você hospede as cópias mais recentes das versões não modificadas do VisitorAPI.js e AppMeasurement.js em um diretório em comum nos servidores da Web sua empresa.

   Esses arquivos também podem ser baixados pelo Gerenciador de códigos na interface do usuário do Analytics, caso necessário.

1. Inclua as variáveis padrão de configuração da sua implementação do Analytics:

   1. Sua ID de org. da Experience Cloud.
   1. A ID do conjunto de relatórios no qual o tráfego dos Instant Articles do Facebook será capturado.
   1. O domínio de servidor de rastreamento da sua empresa.
   1. A variável namespace do seu visitante. **Observação:** muitos desses valores podem ser encontrados na sua implementação padrão do Analytics. Caso necessário, o Adobe Customer Care ou Adobe Consulting podem fornecer assistência no fornecimento dos valores apropriados.

1. [Definir a variável personalizada e o rastreamento de eventos](/help/implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B).
1. Inclua a sintaxe de solicitação de visualização da imagem da página `( s.t())`.

## Etapa 3. Definir a variável personalizada e o rastreamento de eventos {#section_932C41BD21154C25B99389299BDF3E0B}

Variáveis personalizadas e eventos podem ser rastreados com o seu HTML de análise por meio de várias abordagens. A primeira abordagem é incluir a lógica de JavaScript na sua configuração personalizada, da mesma forma que você faria com uma implementação padrão do Analytics. Por exemplo, para definir o valor de um item, use a mesma sintaxe usada em uma implementação normal:

```
s.prop10 = "Facebook Instant Article";
```

Você também pode enviar variáveis de maneira dinâmica ao iframe, aproveitando parâmetros de cadeias de caracteres de consulta no atributo `src` do iframe. Por exemplo:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

Esses parâmetros de cadeias de caracteres podem, mais adiante, ser definidos na seção de variáveis personalizadas do seu JavaScript HTML de análise, usando a `Util.getQueryParam` função [!DNL AppMeasurement] na biblioteca padrão, como a seguir:

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## Rastreamento de visitante {#section_60F0C77659534949831E85B5FD9AE81E}

Enquanto a página de HTML do Analytics estiver sendo hospedada no seu servidor da Web, a Adobe pode oferecer suporte à sua política de privacidade nos Instant Articles do Facebook. Ou seja, se um usuário final optar por não ser rastreado no seu site primário, ele também deixará de ser rastreado em todos os seus Instant Articles do Facebook, sem etapas adicionais. Usar essa página de utilitário também significa que o Serviço de identidade (ID de visitante) é suportado, para que você possa integrar as métricas e variáveis capturadas nos Instant Articles do Facebook com o restante da Experience Cloud. (Um exemplo é o uso de anúncios direcionados com o [!DNL Adobe Audience Manager]).

## Limitações do rastreamento {#section_1EE1BB069A3148DB9446371AFE196567}

Há algumas questões que devem ser observadas com essa abordagem. Valores DOM que tipicamente são acessíveis somente por meio de JavaScript nos Instant Articles do Facebook (como referrer), não poderão ser recuperados no iframe de rastreamento. Entretanto, relatórios de tecnologia padrão, como navegadores, dispositivos, tamanho ou resolução da tela funcionarão automaticamente. Além disso, pageURL pode ser obtido referenciando [!DNL document.referrer] da sua página de utilitários.

## O que está por vir? {#section_A170A10E2A3642A784DF720195DA8B38}

O[!DNL Adobe Analytics] tem orgulho da parceria com o Facebook e nossos editores para fornecer recursos de análise líderes do mercado a editores na Web móvel em uma experiência do usuário ultramente rápida. Estamos trabalhando para construir a melhor solução a longo prazo para atender às necessidades de análises dos nossos clientes.

O Projeto de Instant Articles do Facebook está em rápido desenvolvimento, passando por mudanças regularmente, portanto consulte nossas páginas com frequência para obter atualizações. Aguarde mudanças conforme aprimoramos ainda mais nossas integrações e mais editores adotam os Instant Articles do Facebook no futuro.

Se tiver perguntas ou encontrar problemas, entre em contato com o Atendimento ao cliente ou o seu Consultor da Adobe.
