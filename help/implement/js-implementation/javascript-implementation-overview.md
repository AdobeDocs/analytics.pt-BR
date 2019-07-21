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
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Visão geral da implementação do javascript

Para começar a usar o Analytics, os dados devem ser enviados até um conjunto de relatórios para exibição nos relatórios.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). No entanto, em alguns casos, você pode querer implementar o Analytics usando o método JavaScript mais antigo.

>[!NOTE]
>
>Esta seção descreve o método herdado de implementação do Analytics. Todos os clientes do Analytics têm acesso ao [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) que é o método padrão para implantar as tags da Experience Cloud.

## Etapas da implementação {#section_73961BAD5BB4430A95E073DE5C026277}

Para implementar com êxito uma página com código para coletar dados, você deve ter acesso aos seus servidores de hospedagem para fazer o upload do novo conteúdo em seu site. Também é útil ter um site para implementar um código. 

As etapas a seguir oferecem orientações para a implementação básica do Analytics.

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Etapa </th> 
   <th colname="col1" class="entry"> Tarefa </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Baixe o AppMeasurement para JavaScript e o serviço de ID de visitante. </td> 
   <td colname="col2"> <p>O download está disponível em <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external">Gerenciador de código </a>. </p> <p>Este zip de download contém vários arquivos. <code> AppMeasurement.js</code> e <code>VisitorAPI.js</code> são os arquivos relevantes ao implementar o Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Configure o Serviço de identidade. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>Em <code>VisitorAPI.js</code>, adicione o seguinte código de inicialização de ID de visitante no início do arquivo: </p> 
     <code class="syntax javascript">var visitor = Visitor. getinstance ("INSERT-MCORG-ID-HERE"); visitor. trackingserver = "INSERT-TRACKING-SERVER-HERE"; // o mesmo que s. trackingserver visitor. trackingserversecure = "INSERT-SECURE-TRACKING-SERVER-HERE"; //same como s. trackingserversecure/* = = NÃO ALTERE NADA ABAIXO DESTA LINHA = = </code>
  
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> " INSERT-MCORG-ID-HERE " </code> - (obrigatório) Essa ID de empresa da Adobe Experience Cloud é enviada para o administrador quando sua empresa for provisionada para a Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE"</code>: (Obrigatório) Seu servidor de rastreamento do Analytics. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE"</code> - (obrigatório se ssl estiver habilitado) Seu servidor de rastreamento seguro do Analytics. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Atualizar o <code>AppMeasurement.js </code>. </td> 
   <td colname="col2"> <p>Copie o <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local">Exemplo de código AppMeasurement.js</a> e cole-o no início do arquivo <code>AppMeasurement.js</code>. No mínimo, atualize as seguintes variáveis: </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code> s.account="INSERT-RSID-HERE" </code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. Se não forem definidos corretamente, os dados não serão coletados pela implementação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Hospedar <code>AppMeasurement.js</code> e <code>VisitorAPI.js </code>. </td> 
   <td colname="col2"> <p>Esses arquivos JavaScript principais devem ser hospedados em um servidor Web acessível para todas as páginas em seu site. Você precisa do caminho até esses arquivos na próxima etapa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Fazer referência a <code>AppMeasurement.js</code> e <code>VisitorAPI.js</code> em todas as páginas do site. </td> 
   <td colname="col2"> <p> Inclua o Serviço de ID do visitante ao adicionar a seguinte linha de código na tag <code>&lt;head&gt;</code> ou &lt;body&gt; em cada página. <code> VisitorAPI.js</code> deve ser incluído antes de <code>AppMeasurement.js </code>: </p> 
    <code class="syntax html">&lt; script language = "javascript" type = "text/javascript" src = "https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js" &gt; &lt;/script &gt; </code>
  <p> Inclua o AppMeasurement para JavaScript ao adicionar a seguinte linha de código na tag <code>&lt;head&gt;</code> ou <code>&lt;body&gt;</code> em cada página: </p> 
    <code class="syntax html">&lt; script language = "javascript" type = "text/javascript" src = "https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js" &gt; &lt;/script &gt; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> Atualizar e implantar o código da página. </td> 
   <td colname="col2"> <p>Copie o <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local">Exemplo de código da página</a> e cole-o depois de abrir a tag <code>&lt;body&gt;</code> em cada página que você deseja rastrear. No mínimo, atualize as seguintes variáveis: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // por exemplo, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> Use o DigitalPulse Debugger para verificar que os dados são enviados. </td> 
   <td colname="col2"> <p>Instale o bookmarklet <a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local"> Favorito</a> Adobe Debugger. Depois de instalá-lo, carregue uma página onde você implantou o código da página e abra o depurador. O depurador exibe detalhes sobre os dados de coleta enviados. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Armazenamento em cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

O arquivo JavaScript é armazenado em cache no navegador do visitante depois que é carregado inicialmente, e uma versão dele também é baixada ao menos uma vez por sessão. O download não ocorre em todas as páginas, embora o arquivo seja usado por todas as páginas do site. Na maioria dos sites, os usuários têm em média mais do que algumas visualizações de página por sessão. Portanto, a transferência do JavaScript usado várias vezes neste arquivo pode resultar em menos download de dados em geral.

## Compactação do JavaScript para AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Se você estiver preocupado com o peso da página (tamanho) do Código H (AppMeasurement para JavaScript 1.0 é pré-compactado), a Adobe recomenda considerar a compactação de arquivo usando o GZIP. O GZIP é compatível com a maioria dos navegadores e oferece desempenho superior à compactação JavaScript para compactar e descompactar o arquivo JavaScript principal [!DNL s_code.js].

O link a seguir explica como usar a funcionalidade GZIP em seu site para lidar com a compactação do código de JavaScript [!DNL s_code.js]:

[Apache Module mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Ativação da compactação gzip com Tomcat e Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
