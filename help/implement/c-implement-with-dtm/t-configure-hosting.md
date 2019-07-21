---
description: É possível implantar o Dynamic Tag Management usando uma ou mais das opções de hospedagem disponíveis.
keywords: Implementação do Analytics; método de implementação; gerenciamento dinâmico de tags; dtm; hospedagem; opções de hospedagem; akamai; auto-hospedagem; auto-hospedagem; entrega ftp; hospedagem ftp; download da biblioteca
seo-description: É possível implantar o Dynamic Tag Management usando uma ou mais das opções de hospedagem disponíveis.
seo-title: Configurar opções de hospedagem
solution: Analytics
title: Configurar opções de hospedagem
topic: Desenvolvedor e implementação
uuid: 04268 f 2 d-e 76 f -4 fe 4-8 fcc-f 0 db 3 a 016502
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Configurar opções de hospedagem

You can deploy [!UICONTROL Dynamic Tag Management] using one or more of the available hosting options.

[!UICONTROL O Dynamic Tag Management fornece várias opções para hospedar os arquivos JavaScript necessários.]

Para obter informações mais detalhadas sobre hospedagem, consulte [Opções de codificação e hospedagem incorporadas](https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html) na Documentação do produto de Dynamic Tag Management.

Na guia Incorporar, selecione uma opção de hospedagem.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opção de hospedagem </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Implementação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> A opção de hospedagem mais simples para implementar. </p> <p>Rede de entrega distribuída globalmente. </p> <p>Adiciona outras dependências de infraestrutura de terceiros (pesquisa de DNS, disponibilidade do Akamai). </p> <p>Para obter informações mais detalhadas, consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/akamai.html" format="html" scope="external">Akamai</a> na documentação do produto do Dynamic Tag Management </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">O Dynamic Tag Management gera bibliotecas JavaScript personalizadas. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">O Dynamic Tag Management exporta as bibliotecas JavaScript personalizadas para o Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">O site de destino faz referência às bibliotecas do Dynamic Tag Management hospedadas pelo Akamai diretamente no nível da página. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auto-hospedagem: Entrega FTP </td> 
   <td colname="col2"> <p>A <span class="term"> push</span> approach, whereby Dynamic Tag Management exports custom JavaScript libraries directly to the web content server host via the FTP protocol. </p> <p>Essa solução exige que um servidor FTP e credenciais estejam disponíveis no servidor de conteúdo da Web para publicar as alterações nas bibliotecas personalizadas do Dynamic Tag Management. </p> <p>Para obter informações mais detalhadas, consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_ftp.html" format="html" scope="external">FTP</a> na documentação do produto do Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">O Dynamic Tag Management gera bibliotecas JavaScript personalizadas. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">O Dynamic Tag Management exporta as bibliotecas JavaScript personalizadas para o servidor de hospedagem via FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">O site de destino referencia localmente as bibliotecas personalizadas do Dynamic Tag Management. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auto-hospedagem: Download da biblioteca </td> 
   <td colname="col2"> <p>A <span class="term"> pull</span> approach, whereby the application exports custom JavaScript libraries
     <!-- to Amazon S3-->. Nele, as bibliotecas podem ser acessadas por um processo do lado do servidor hospedado. </p> <p>Além disso, as bibliotecas estão disponíveis por download da Web diretamente da interface do Dynamic Tag Management. </p> <p>Essa solução exige recuperação e publicação manual das bibliotecas do Dynamic Tag Management ou a criação de um processo automatizado que extraia as bibliotecas do Akamai para o servidor de conteúdo da Web. </p> <p>Embora esse método seja o mais demorado, também é a opção mais segura e flexível. </p> <p>Para verificar se a versão mais recente do seu arquivo de biblioteca está sendo referenciada, use o comando </p> <p>Para obter informações mais detalhadas, consulte <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_download.html" format="html" scope="external">Download de biblioteca</a> na documentação do produto do Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">O Dynamic Tag Management gera bibliotecas JavaScript personalizadas. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">O Dynamic Tag Management exporta as bibliotecas JavaScript personalizadas para o Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">As bibliotecas personalizadas do Dynamic Tag Management são movidas manual ou programaticamente para o servidor de conteúdo da Web. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">O site de destino referencia localmente as bibliotecas personalizadas do Dynamic Tag Management. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

É possível usar mais de uma opção de hospedagem. Por exemplo, você pode hospedar os arquivos preparados usando o Akamai, mas auto-hospedar o site de produção. Observe que cada tipo de hospedagem possui seu próprio código de incorporação e somente um código de incorporação pode ser adicionado a uma página.
