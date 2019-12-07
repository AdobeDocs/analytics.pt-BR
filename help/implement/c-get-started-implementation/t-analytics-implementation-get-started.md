---
description: Saiba mais sobre a experiência dos novos clientes ao executarem a implementação do Adobe Analytics.
keywords: Getting Started
subtopic: Analysis Workspace
title: Modal de implementação simplificada
topic: Reports and analytics
uuid: 6fad2c1f-476c-4985-90df-7c222e751ddc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Modal de implementação simplificada

Saiba mais sobre a experiência dos novos clientes ao executarem a implementação do Adobe Analytics.

<!-- 

<p>https://activation.adobedtm.com/index.php?redirected=1 </p>

 -->

Novos usuários podem criar rapidamente o primeiro conjunto de relatórios (repositório de dados) do [!DNL Analytics], usando o modo de configuração do *`Getting Started with Adobe Analytics`*. Em seguida, é possível implantar o código do [!DNL Analytics] usando o [!DNL Dynamic Tag Management].

O[!DNL Dynamic Tag Management] permite administrar a implementação do Adobe Analytics sem precisar fazer alterações ao seu site todas as vezes. Se estiver implementando um aplicativo para dispositivos móveis, você pode obter o SDK que precisa para começar a coletar dados valiosos dos aplicativos.

Esse procedimento permite:

* Criar rapidamente o seu primeiro [conjunto de relatórios](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html).
* Implantar [!DNL Analytics] e o Serviço [de](https://marketing.adobe.com/resources/help/en_US/mcvid/)identidade.

* Executar relatórios de dados básicos a nível de página.

> [!NOTE] Antes de começar, verifique se o Analytics está [ativado na Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html) (o processo de provisionamento da solução). Caso tenha recebido um email convidando para efetuar logon no Analytics com o painel Empresa, você completou o pré-requisito.

**Para executar a janela restrita da implementação simplificada**

1. Log in to the [!DNL Adobe Experience Cloud] ( [experiencecloud.adobe.com](https://experiencecloud.adobe.com)).

   Ao acessar o [!DNL Analytics], o sistema identifica se você tem um conjunto de relatórios. Caso não tenha, a página [!UICONTROL Introdução ao Adobe Analytics] é exibida.

   ![](assets/analytics-implementation-rs-wizard.png)

   Como alternativa, execute essa configuração no [!DNL Analytics] clicando em **[!UICONTROL Ajuda]** &gt; **[!UICONTROL Bem-vindo ao Adobe Analytics]**.

1. Especifique as seguintes informações fundamentais sobre a sua empresa:

   <table id="table_1741878A1B284CB78D297D531DC703D6"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Elemento </th> 
       <th colname="col2" class="entry"> Descrição </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Tipo de propriedade </p> </td> 
       <td colname="col2"> <p>A implementação é para Web, dispositivos móveis ou ambos? </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Setores </p> </td> 
       <td colname="col2"> <p>Especifique como a sua empresa ganha dinheiro (produtos, atendimento ao cliente, leads, reconhecimento de marca e anúncios). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Camada de dados </p> </td> 
       <td colname="col2"> <p>(Recomendado) Um baco de dados JavaScript é usado para armazenar informações. Se executar a configuração automática usando o Dynamic Tag Management, estará usando uma camada de dados. </p> <p>Para um blog sobre camadas de dados, consulte <a href="https://blogs.adobe.com/digitalmarketing/analytics/data-layers-buzzword-best-practice/">Camada de dados: de chavão a práticas recomendadas</a>. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Repositório de dados (conjunto de relatórios) </p> </td> 
       <td colname="col2"> <p> Um <a href="https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html">conjunto de relatórios</a> é um conjunto discreto de dados que geralmente corresponde a uma única propriedade (site ou aplicativo) ou marca. Cada conjunto de relatórios tem seu próprio aglomerado de relatórios e métricas. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Fuso Horário </p> </td> 
       <td colname="col2"> <p>Seu horário local. (Detectado automaticamente.) </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Estimativa de Exibições da página </p> </td> 
       <td colname="col2"> <p>Número aproximado de exibições da página que o seu site recebe por dia. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Moeda de base </p> </td> 
       <td colname="col2"> <p>A moeda que usa para fazer negócios. </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Clique em **[!UICONTROL Próximo]**.

   O sistema cria um conjunto de relatórios.

1. Para iniciar a implantação, clique em **[!UICONTROL Avançar]** e, em seguida, clique em uma das seguintes opções:

   <table id="table_71C7F7B9677346CD8D5130519D32464B"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Elemento </th> 
       <th colname="col2" class="entry"> Descrição </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Implantar </p> </td> 
       <td colname="col2"> <p> Inicia o <span class="keyword">Dynamic Tag Management</span> onde é possível efetuar o logon e implantar o Analytics. Esse processo implementa automaticamente o arquivo <span class="filepath">AppMeasurement.js</span> e o Serviço de identidade (<span class="filepath"> VisitorAPI.js</span>). </p> <p> <p>Importante: em uma nova guia do navegador, uma página de ajuda é exibida, orientando você pela implementação do <span class="keyword">Adobe Analytics</span> por meio do Dynamic Tag Management. </p> </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Baixar </p> </td> 
       <td colname="col2"> <p> Baixe o arquivo de instalação chamado <span class="filepath">INSTALAR &lt;nome do conjunto de relatórios&gt;.js</span>. Essa opção é adequada para usuário experientes que compreendem a <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html">implementação do JavaScript</a>. </p> <p> <p>Importante: a ação de baixar o código não equivale a implementar o <span class="keyword">Analytics</span>. Isso é uma implantação manual realizada nas páginas do site ou pelos serviços do Adobe Consulting. </p> </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Executar um relatório.

   Após implantar a ferramenta Analytics, é possível executar um relatório no Reports &amp; Analytics para confirmar o envio de dados ao seu site. (Consulte [Fazer logon e navegar](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/analytics-navigation.html) para se familiarizar com a interface do Analytics.)

   Por exemplo, as **[!UICONTROL Métricas do site]** &gt; **[!UICONTROL Tempo real]** permitem a visualização dos dados mais recentes.

   >[!NOTE]
   >
   >O relatório em [!UICONTROL Tempo real] exige configuração prévia à execução. Consulte [Configurar relatório em tempo real](https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html).

**Exemplo de relatório em tempo real**

![](assets/real-time-report.png)
