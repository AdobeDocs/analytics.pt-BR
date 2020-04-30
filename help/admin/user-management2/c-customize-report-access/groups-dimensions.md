---
description: Personalize detalhadamente o acesso dos usuários, inclusive a eVars e relatórios de tráfego, de soluções e de definição de caminho.
keywords: groups;permissions
subtopic: Users and groups
title: Personalizar permissões de dimensões
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Personalizar permissões de dimensões

>[!IMPORTANT] O gerenciamento de usuários e de produtos está sendo transferido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). A Adobe enviará uma notificação quando for a sua vez de migrar os usuários. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

Personalize detalhadamente o acesso dos usuários, inclusive a eVars e relatórios de tráfego, de soluções e de definição de caminho.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

>[!IMPORTANT] Não é possível atribuir permissões a algumas dimensões neste momento. Tais dimensões são: Comprimento do Mobile Bookmark; Número do Mobile Device, DRM do Mobile; Serviços de informações do Mobile; VM de Java Mobile; Decoração de email do Mobile; Protocolos de rede do Mobile; Mobile OS; Aperte para falar do Mobile.
>
>Essas dimensões estão disponíveis para todos os usuários, independentemente de outras permissões.

The settings on this page pertain to the report suites selected on the [!UICONTROL Define User Groups] page.

![](assets/permissions-dimensions.png)

Entenda as informações a seguir sobre a categoria Dimensão para permissões.

* eVars 1-250 autorizados individualmente.
* Todos os relatórios de tráfego são dimensões.
* Os relatórios de Vídeo e Mobile são dimensões, como outros relatórios de soluções do Analytics (Experience Manager, Advertising Cloud, Social e outros.)
* Há relatórios de definição de caminho disponíveis, se o usuário tiver acesso à dimensão principal.
* Todas as dimensões e métricas atuais dos grupos personalizados foram automaticamente migradas para as novas categorias. Se um grupo tiver métricas ativadas, receberá por padrão todas as novas dimensões (eVars e com sensível a conteúdo) e métricas permissíveis.
* Permissões do Importador de classificações (antigo SAINT): o acesso a classificações é determinado pelo acesso à [variável](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html) em que se baseia a classificação.

Para obter mais informações, consulte Alterações [de permissão de](https://docs.adobe.com/content/help/pt-BR/analytics/admin/user-product-management/user-management/permissions-changes.html)usuário e grupo.

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
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVars </a> </p> </td> 
   <td colname="col2"> <p>eVars 1-250 autorizados individualmente. As eVars são variáveis de conversão personalizadas, usadas para segmentar métricas de sucesso em relatórios personalizados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/evar.html"> Props </a> </p> </td> 
   <td colname="col2"> <p>As props são variáveis de tráfego personalizadas. </p> <p>Consulte <a href="https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/evar.html">Props de tráfego e eVars de conversão</a> em Implementação do Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/page-variables.html"> Hierarquia </a> </p> </td> 
   <td colname="col2"> <p> A variável de hierarquia (hierN) determina a localização de uma página da hierarquia do site ou na estrutura da página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/page-variables.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Com funcionamento semelhante ao das Propriedades de lista, as variáveis de lista permitem vários valores na mesma solicitação de imagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Padrão </p> </td> 
   <td colname="col2"> <p>Faz referência a dimensões padrão (pronto para uso) no Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/br/support/experience-manager.html"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/br/support/advertising-cloud.html"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/pt-BR/analytics/analyze/activity-map/activity-map.html"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensões do relatório do Activity Map: página do Activity Map; link do Activity Map; região do Activity Map; link por região do Activity Map; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/pt-BR/media-analytics/using/media-overview.html"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Esta Integração de parceiro não está mais ativa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/pt-BR/media-analytics/using/media-overview.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Esta Integração de parceiro não está mais ativa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Não usado. </p> </td> 
  </tr> 
 </tbody> 
</table>
