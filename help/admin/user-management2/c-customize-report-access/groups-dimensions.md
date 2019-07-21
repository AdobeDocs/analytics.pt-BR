---
description: Personalize detalhadamente o acesso dos usuários, inclusive a eVars e relatórios de tráfego, de soluções e de definição de caminho.
keywords: grupos; permissões
seo-description: Personalize detalhadamente o acesso dos usuários, inclusive a eVars e relatórios de tráfego, de soluções e de definição de caminho.
seo-title: Personalizar permissões de dimensão
solution: Analytics
subtopic: Usuários e grupos
title: Personalizar permissões de dimensão
topic: Ferramentas administrativas
uuid: aaf 164 ad -3863-4129-864 e -39 ec 71 c 6 a 8 eb
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Personalizar permissões de dimensão

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). A Adobe enviará uma notificação quando for a sua vez de migrar os usuários. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Personalize detalhadamente o acesso dos usuários, inclusive a eVars e relatórios de tráfego, de soluções e de definição de caminho.

**[!UICONTROL Gerenciamento de usuários]** &gt; **[!UICONTROL Grupos]** &gt; **[!UICONTROL Acesso ao Relatório]** &gt; **[!UICONTROL Dimensões]** &gt; **[!UICONTROL Personalizar]**

>[!IMPORTANT]
>
>Neste momento, algumas dimensões não são permissões. Tais dimensões são: Comprimento do Mobile Bookmark; Número do Mobile Device, DRM do Mobile; Serviços de informações do Mobile; VM de Java Mobile; Decoração de email do Mobile; Protocolos de rede do Mobile; Mobile OS; Aperte para falar do Mobile.
>
>Essas dimensões estão disponíveis para todos os usuários, independentemente de outras permissões.

As configurações desta página pertencem aos conjuntos de relatórios selecionados na página [!UICONTROL Definir grupos de usuários].

![](assets/permissions-dimensions.png)

Entenda as informações a seguir sobre a categoria Dimensão para permissões.

* eVars 1-250 autorizados individualmente.
* Todos os relatórios de tráfego são dimensões.
* Os relatórios de vídeo e móveis são dimensões, bem como outros relatórios de soluções do Analytics (Experience Manager, Advertising Cloud, Social e fazer isso).
* Há relatórios de definição de caminho disponíveis, se o usuário tiver acesso à dimensão principal.
* Todas as dimensões e métricas atuais dos grupos personalizados foram automaticamente migradas para as novas categorias. Se um grupo tiver métricas ativadas, receberá por padrão todas as novas dimensões (eVars e com sensível a conteúdo) e métricas permissíveis.
* Permissões do Importador de classificações (antigo SAINT): o acesso a classificações é determinado pelo acesso à [variável](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html) em que se baseia a classificação.

Para obter mais informações, consulte [Perguntas frequentes sobre mudanças de permissão](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html).

**Personalizar dimensões**

Os itens a seguir são dimensões que você pode permitir.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrições </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../admin/admin/conversion-var-admin/conversion-var-admin.md#concept_C02F7AA01DE242F1AA1A4E74022BE9DE" format="dita" scope="local"> eVars </a> </p> </td> 
   <td colname="col2"> <p>eVars 1-250 autorizados individualmente. As eVars são variáveis de conversão personalizadas, usadas para segmentar métricas de sucesso em relatórios personalizados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external"> Props </a> </p> </td> 
   <td colname="col2"> <p>As props são variáveis de tráfego personalizadas. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">Props de tráfego e eVars de conversão</a> em Implementação do Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html" format="html" scope="external"> Hierarquia </a> </p> </td> 
   <td colname="col2"> <p> A variável de hierarquia (hierN) determina a localização de uma página da hierarquia do site ou na estrutura da página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html" format="html" scope="external"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Com funcionamento semelhante ao das Propriedades de lista, as variáveis de lista permitem vários valores na mesma solicitação de imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão </p> </td> 
   <td colname="col2"> <p>Faz referência a dimensões (out-of-the-box) no Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/" format="https" scope="external"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/" format="https" scope="external"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/" format="https" scope="external"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensões do relatório do Activity Map: página do Activity Map; link do Activity Map; região do Activity Map; link por região do Activity Map; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Esta Integração de parceiro não está mais ativa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html" format="html" scope="external"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Integrações de parceiros. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Não usado. </p> </td> 
  </tr> 
 </tbody> 
</table>

