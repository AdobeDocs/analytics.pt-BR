---
description: Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.
keywords: Implementação do Analytics; javascript; implementação de javascript; appmeasurement; baixar o appmeasurement; Serviço de identidade; visitorapi. js; cache; compactação de appmeasurement
seo-description: Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.
seo-title: Visão geral da implementação do javascript
solution: Analytics
title: Visão geral da implementação do javascript
topic: Desenvolvedor e implementação
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 0a1db598a2b113ad71eb5d05d3f5c97f1af7cd62

---


# Visão geral da implementação do javascript

Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Launch](/help/implement/implement-with-launch/create-analytics-property.md). No entanto, em alguns casos, você pode querer implementar o Analytics usando o método JavaScript mais antigo.

>[!NOTE]
>
>Esta seção descreve o método herdado de implementação do Analytics. All Analytics customers have access to [Launch](/help/implement/implement-with-launch/create-analytics-property.md), which is the standard method to deploy Experience Cloud tags.

## Etapas da implementação {#section_73961BAD5BB4430A95E073DE5C026277}

Para implementar com êxito uma página com código para coletar dados, você deve ter acesso aos seus servidores de hospedagem para fazer o upload do novo conteúdo em seu site. Também é útil ter um site para implementar um código. 

As etapas a seguir oferecem orientações para a implementação básica do Analytics.

| Tarefa | Descrição |
|--- |--- |
| 1. Baixe o appmeasurement para javascript e o serviço de ID. | Faça logon no Analytics por meio da Experience Cloud. O arquivo de download está disponível em Analytics &gt; Administrador &gt; Gerenciador de código. Este zip de download contém vários arquivos.  AppMeasurement.js e VisitorAPI.js são os arquivos relevantes ao implementar o Analytics. |
| 2. Configure o Serviço de identidade. (Antigo serviço de ID de visitante) | Consulte [Configurar o serviço de identidade do Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 3. Update `AppMeasurement.js`. | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. No mínimo, atualize as seguintes variáveis:<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>Consulte [Preencher corretamente a variável trackingserver e trackingserversecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) ou entre em contato com o Atendimento ao cliente caso não tenha certeza sobre esses valores. Se não forem definidos corretamente, os dados não serão coletados pela implementação.</br> |
| 4. Host `AppMeasurement.js` e `VisitorAPI.js`. | Esses arquivos JavaScript principais devem ser hospedados em um servidor Web acessível para todas as páginas em seu site. Você precisa do caminho até esses arquivos na próxima etapa. |
| 5. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Include the Visitor ID Service by adding the following line of code in the `head` or `body` tag on each page. (`VisitorAPI.js` must be included before `AppMeasurement.js`).<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page:<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. Atualize e implante o código da página. | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. No mínimo, atualize as seguintes variáveis:<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s. pagename = "INSERT-NAME-HERE" (por exemplo, s. pagename = document. title)</li></ul> |
| 7. Use o Depurador da Experience Cloud para verificar se os dados estão sendo enviados. | Install the [Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). Depois de instalá-lo, carregue uma página onde você implantou o código da página e abra o depurador. O depurador exibe detalhes sobre os dados de coleta enviados. |

## Armazenamento em cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e uma versão dele também é baixada ao menos uma vez por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, a transferência do JavaScript usado várias vezes neste arquivo pode resultar em menos download de dados em geral.

## Compactação do JavaScript para AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Se você estiver preocupado com o peso da página (tamanho) do Código H (AppMeasurement para JavaScript 1.0 é pré-compactado), a Adobe recomenda considerar a compactação de arquivo usando o GZIP. O GZIP é compatível com a maioria dos navegadores e oferece desempenho superior à compactação JavaScript para compactar e descompactar o arquivo JavaScript principal [!DNL s_code.js].

O link a seguir explica como usar a funcionalidade GZIP em seu site para lidar com a compactação do código de JavaScript [!DNL s_code.js]:

[Apache Module mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Ativação da compactação gzip com Tomcat e Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
