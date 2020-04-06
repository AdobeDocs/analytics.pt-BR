---
description: Implante o Adobe Analytics (Standard e Premium) por meio do Dynamic Tag Management, criando a ferramenta Adobe Analytics e configurando o código da página de forma automática ou manual. Recomendamos o método automático para a maioria dos usuários.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
title: Adicionar a ferramenta Adobe Analytics
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adicionar a ferramenta Adobe Analytics

Implante o Adobe Analytics (Standard e Premium) por meio do Dynamic Tag Management, criando a ferramenta Adobe Analytics e configurando o código da página de forma automática ou manual. Recomendamos o método automático para a maioria dos usuários.

>[!NOTE] Para melhorar o rastreamento de visitantes, recomendamos que você ative o [Serviço de identidade](https://marketing.adobe.com/resources/help/pt_BR/mcvid/).

## Adicionar uma ferramenta Adobe Analytics {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Clique em  **[!UICONTROL  *`Web Property Name`*]** > **[!UICONTROL Overview]** > **[!UICONTROL Add a Tool]** > **[!UICONTROL Adobe Analytics]** .

   ![](assets/dtm-add-analytics-tool.png)

1. Preencha os campos:

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tipo de ferramenta </p> </td> 
   <td colname="col2">O tipo de ferramenta, como o <span class="keyword">Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome da ferramenta </p> </td> 
   <td colname="col2">Um nome descritivo para esta ferramenta. Esse nome é exibido na guia <span class="wintitle">Visão geral</span> em <span class="wintitle">Ferramentas instaladas</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Método de configuração </p> </td> 
   <td colname="col2"> <p> <b>Automático</b> (recomendado): Use o gerenciamento dinâmico de tags para gerenciar a configuração. Esse método permite a sincronização automática dos conjuntos de relatórios do <span class="keyword">Adobe Analytics</span> por meio do logon na <span class="keyword">Experience Cloud</span> ou da ID de serviços da Web, e gerencia o código AppMeasurement. </p> <p>Uma vez que as contas são conectadas, o Dynamic Tag Management insere as IDs e os nomes dos conjuntos de relatórios do <span class="keyword">Adobe Analytics</span> na interface da ferramenta de configuração, o que permite uma velocidade maior na implementação da ferramenta e um número menor de erros por parte do usuário. </p> <p> <p>Observação: escolha a opção <span class="wintitle">Automático</span> se você for cliente do <span class="keyword">Adobe Analytics Premium</span>. </p> </p> <p>Preencha os campos específicos da configuração automática: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (Padrão) Usa o logon único da <span class="keyword">Experience Cloud</span>. Especifique sua Experience Cloud ID e senha. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Serviços da Web</b>: especifique seu nome de usuário e o segredo compartilhado para os Serviços da Web. </p> <p>As credenciais de segredo compartilhado localizam-se em <span class="uicontrol">Administração</span> &gt; <span class="uicontrol">Configurações da empresa</span> &gt; <a href="https://docs.adobe.com/content/help/pt-BR/analytics/admin/company-settings/web-services-admin.html">Serviços da Web</a>. </p> <p>Desenvolvedores, consultem <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api">Obter acesso ao serviço da Web para a Enterprise API</a> a fim de obter ajuda para obter credenciais dos serviços da Web. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manual</b>: gerencie manualmente o código do AppMeasurement. É possível baixar o código de <span class="keyword">AppMeasurement</span> do <span class="keyword">Analytics</span> em <span class="ignoretag"><span class="uicontrol">Ferramentas Administrativas</span> &gt; <span class="uicontrol">Gerenciador de código</span></span>. </p> <p>Clique em <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html">JavaScript (novo)</a> para obter informações sobre como baixar o código localmente para copiar e colar no campo <span class="wintitle">Editar código</span> no <a href="/help/implement/other/dtm/c-aa-tool/library-management.md">Gerenciamento de biblioteca</a>. </p> <p>Preencha os campos específicos de uma configuração manual: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID da conta de produção: </b>(Obrigatório) Sua conta de produção para coleta de dados. Para o Analytics, essa é a ID do conjunto de relatórios. O Dynamic Tag Management instala automaticamente a conta correta no ambiente de produção e preparo. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID da conta de armazenamento temporário: </b>(Obrigatório) Usado em seu ambiente de desenvolvimento ou teste. Para o Analytics, essa é a ID do conjunto de relatórios. Uma conta de preparo mantém os dados de teste separados da produção. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Servidor de rastreamento de: </b>especifique as informações sobre seu servidor de rastreamento de. </p> <p>As variáveis <span class="wintitle">Servidor de rastreamento</span> e <span class="wintitle">Servidor de rastreamento de SSL</span> são usadas para implementação de cookies primários, para especificar o domínio em que a solicitação de imagem e o cookie são gravados. Para obter mais informações, consulte o artigo sobre <a href="https://helpx.adobe.com/br/analytics/kb/determining-data-center.html">Preenchimento correto das variáveis trackingServer e trackingServerSecure</a>. </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>Servidor de rastreamento de SSL:</b> especifique as informações sobre seu servidor de rastreamento de SSL. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Create Tool]** to create the tool and display it for editing.

   As ferramentas são exibidas na [!UICONTROL Overview] guia, em [!UICONTROL Installed Tools].

1. (Condicional) Configure a ferramenta ainda mais, conforme necessário, seguindo as instruções nos links abaixo ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]e [!UICONTROL Customize Page Code]).

Consulte [Perguntas frequentes sobre a ferramenta do Adobe Analytics](/help/implement/faq.md) para obter mais informações sobre essa ferramenta.

## Editar uma ferramenta Adobe Analytics existente {#section_148B16AF429B4949B06238D90635B726}

Você pode editar uma ferramenta Adobe Analytics existente para mudar suas configurações.

1. Click the  ![](assets/settings_gear.png) icon next to an installed tool from the [!UICONTROL Overview] tab.
1. Edite os campos conforme desejado.

   A tabela a seguir inclui apenas os elementos que diferem dos elementos disponíveis ao criar uma ferramenta do Analytics, conforme descrito acima. No entanto, você pode alterar qualquer elemento na página, conforme descrito em ambas as tabelas.

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ativar configuração automática </p> </td> 
   <td colname="col2"> <p>Observação: a ativação dessa configuração altera a implementação configurada manualmente para o método de configuração automática descrito no <span class="term">Método de configuração</span>. </p> <p>Essa opção permite que o Dynamic Tag Management recupere automaticamente as configurações da sua conta do <span class="keyword">Adobe Analytics</span>. </p> <p>O código AppMeasurement mais recente é usado e as notificações de atualização são exibidas para seleção à medida que novas versões se tornam disponíveis. Você também pode reverter para versões anteriores do AppMeasurement, conforme necessário, por exemplo, por motivos de compatibilidade. Até cinco versões anteriores são exibidas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atualizar credenciais </p> </td> 
   <td colname="col2"> <p>Atualize a API, por exemplo, para atualizar conjuntos de relatórios associados a um usuário. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Condicional) Configure a ferramenta ainda mais, conforme necessário, seguindo as instruções nos links abaixo ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]e [!UICONTROL Customize Page Code]).
1. Clique em **[!UICONTROL Save Changes]**.
