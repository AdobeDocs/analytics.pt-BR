---
description: Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.
keywords: Implementação do Analytics, javascript, implementação de javascript, appmeasurement, baixar appmeasurement, serviço de identidade, visitorapi.js, armazenamento em cache, compactação de appmeasurement
seo-description: Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.
seo-title: Visão geral da implementação do JavaScript
solution: Analytics
title: Visão geral da implementação do JavaScript
topic: Desenvolvedor e implementação
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
translation-type: ht
source-git-commit: 0a1db598a2b113ad71eb5d05d3f5c97f1af7cd62

---


# Visão geral da implementação do JavaScript

Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.

A maneira mais fácil e recomendada de enviar dados para [!DNL Analytics] é usar o [Launch](/help/implement/implement-with-launch/create-analytics-property.md). No entanto, em alguns casos, você pode querer implementar o Analytics usando o método JavaScript mais antigo.

>[!NOTE]
>
>Esta seção descreve o método antigo de implementação do Analytics. Todos os clientes do Analytics têm acesso ao [Launch](/help/implement/implement-with-launch/create-analytics-property.md), que é o método padrão para implantar as tags da Experience Cloud.

## Etapas da implementação {#section_73961BAD5BB4430A95E073DE5C026277}

Para implementar com êxito uma página com código para coletar dados, você deve ter acesso aos seus servidores de hospedagem para fazer o upload do novo conteúdo em seu site. Também é útil ter um site para implementar um código. 

As etapas a seguir oferecem orientações para a implementação básica do Analytics.

| Tarefa | Descrição |
|--- |--- |
| 1. Baixe o AppMeasurement para JavaScript e o serviço de ID. | Faça Logon no Analytics por meio da Experience Cloud. O arquivo de download está disponível em Analytics &gt; Admin &gt; Gerenciador de código.  Este zip de download contém vários arquivos.  AppMeasurement.js e VisitorAPI.js são os arquivos relevantes ao implementar o Analytics. |
| 2. Configure o Serviço de identidade. (antigo Serviço de ID de visitante) | Consulte [Configurar o Serviço de identidade do Analytics](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html) |
| 3. Atualize `AppMeasurement.js`. | Copie o [exemplo de código AppMeasurement.js](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) e cole no início do arquivo `AppMeasurement.js`. No mínimo, atualize as seguintes variáveis:<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>Consulte [Preencher corretamente as variáveis trackingServer e o trackingServerSecure](https://helpx.adobe.com/br/analytics/kb/determining-data-center.html) ou entre em contato com o Atendimento ao cliente se não tiver certeza sobre esses valores. Se não forem definidos corretamente, os dados não serão coletados pela implementação.</br> |
| 4. Host `AppMeasurement.js` e `VisitorAPI.js`. | Esses arquivos JavaScript principais devem ser hospedados em um servidor Web acessível para todas as páginas em seu site. Você precisa do caminho até esses arquivos na próxima etapa. |
| 5. Mencione `AppMeasurement.js` e `VisitorAPI.js` em todas as páginas do site. | <ul><li>Inclua o Serviço de ID de visitante ao adicionar a seguinte linha de código na tag `head` ou `body` em cada página. (`VisitorAPI.js` deve ser incluído antes de `AppMeasurement.js`).<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>Inclua o AppMeasurement para JavaScript ao adicionar a seguinte linha de código na tag `head` ou `body` em cada página:<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. Atualize e implante o código de página. | Copie o [Exemplo de código de página](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) e cole logo após a tag de abertura `body` em cada página que você deseja rastrear. No mínimo, atualize as seguintes variáveis:<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s.pageName="INSERT-NAME-HERE" (por exemplo, s.pageName=document.title)</li></ul> |
| 7. Use o Experience Cloud Debugger para verificar se os dados estão sendo enviados. | Instale o [Experience Cloud Debugger](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). Depois de instalá-lo, carregue uma página onde você implantou o código da página e abra o depurador. O depurador exibe detalhes sobre os dados de coleta enviados. |

## Armazenamento em cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e uma versão dele também é baixada ao menos uma vez por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, a transferência do JavaScript usado várias vezes neste arquivo pode resultar em menos download de dados em geral.

## Compactação do JavaScript para AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Se você estiver preocupado com o peso da página (tamanho) do Código H (AppMeasurement para JavaScript 1.0 é pré-compactado), a Adobe recomenda considerar a compactação de arquivo usando o GZIP. O GZIP é compatível com a maioria dos navegadores e oferece desempenho superior à compactação JavaScript para compactar e descompactar o arquivo JavaScript principal [!DNL s_code.js].

O link a seguir explica como usar a funcionalidade GZIP em seu site para lidar com a compactação do código de JavaScript [!DNL s_code.js]:

[Módulo Apache mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Ativação da compactação gzip com Tomcat e Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
