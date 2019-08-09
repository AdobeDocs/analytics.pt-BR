---
description: 'null'
seo-description: 'null'
seo-title: Fluxo de trabalho do GDPR do Adobe Analytics
title: Fluxo de trabalho do GDPR do Adobe Analytics
uuid: f 24 e 8 be 3-8 b 5 c -409 b-ad 6 b -770198 ae 2549
translation-type: tm+mt
source-git-commit: fc9dbf8e2590ca3d89b295be03ec8ef7dc511c72

---


# Fluxo de trabalho do GDPR do Adobe Analytics

Bem-vindo ao Adobe Analytics e à preparação para o GDPR. Esse fluxo de trabalho descreve as etapas necessárias para preparar a implementação do Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão do GDPR dos titulares dos dados.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Descrição da tarefa </th> 
   <th colname="col3" class="entry"> Links para instruções e mais informações </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" />Certifique-se de que qualquer um dos seus conjuntos de relatórios que possam conter dados relevantes para o GDPR seja mapeado para a sua organização da Experience Cloud (ou IMS). </p> <p>As solicitações do GDPR são enviadas por meio de uma organização da Experience Cloud e serão aplicadas a todos os conjuntos de relatórios reivindicados por essa organização. As solicitações não serão aplicadas a conjuntos de relatórios não mapeados para essa organização, mesmo se fizerem parte da sua empresa de logon. </p> </td> 
   <td colname="col3"> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Mapear conjuntos de relatórios para uma organização</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Defina sua política de retenção de dados. </p> </td> 
   <td colname="col3"> <p>Uma política de retenção de dados precisa estar em vigor para que a Adobe possa atender às solicitações de acesso/exclusão de dados do GDPR. </p> <p>Para obter mais informações, consulte estas <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Perguntas frequentes sobre a retenção de dados do Analytics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize-se com rótulos de DULE/GDPR, IDs do Adobe Analytics, namespaces e expansão de ID. </p> </td> 
   <td colname="col3"> <p> Leia os seguintes tópicos neste conjunto de documentação: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Rótulos do GDPR para variáveis do Analytics</a> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Item de lista </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Práticas recomendadas de rotulagem</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Atribua rótulos de identidade, sensibilidade e governança de dados a cada variável em um conjunto de relatórios. </p> <p>Observação: lembre-se de que a Rotulagem precisa ser analisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. Você também pode analisar a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. A reimplementação de aplicativos ou sites móveis pode alterar como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos. </p> </td> 
   <td colname="col3"> <p> Siga as instruções em <a href="../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Rótulo dos dados</a>do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Conecte-se à API do GDPR da Adobe e envie solicitações de acesso e de exclusão. </p> </td> 
   <td colname="col3"> <p>Como cliente do Adobe Analytics, você pode enviar solicitações individuais do GDPR para acessar e excluir dados do cliente, ao chamar a <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">API do GDPR da Adobe Experience Cloud</a>. </p> <p>É possível enviar qualquer identificador do Analytics (conforme descrito na seção <a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local">Práticas recomendadas de rotulagem</a>) nas solicitações, junto com suas respectivas IDs de namespace (IDs da fonte de dados). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Visualize e gerencie as configurações do GDPR do seu conjunto de relatórios. </p> </td> 
   <td colname="col3"> <p>Siga as instruções em <a href="../../admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> Visualizar configurações de gerenciamento de dados do conjunto de relatórios</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Descrição da tarefa | Links para instruções e mais informações |
|--- |--- |
| **Etapa 1**: Verifique se todos os conjuntos de relatórios que podem conter dados relevantes do RGPD estão mapeados para a organização da Experience Cloud (ou IMS). As solicitações do GDPR são enviadas por meio de uma organização da Experience Cloud e serão aplicadas a todos os conjuntos de relatórios reivindicados por essa organização. As solicitações não serão aplicadas a conjuntos de relatórios não mapeados para essa organização, mesmo se fizerem parte da sua empresa de logon. | Consulte [Mapear conjuntos de relatórios para uma organização](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Etapa 2** Defina a política de retenção de dados. | Uma política de retenção de dados precisa estar em vigor para que a Adobe possa atender às solicitações de acesso/exclusão de dados do GDPR.  Para obter mais informações, consulte estas [Perguntas frequentes sobre a retenção de dados do Analytics](/help/technotes/data-retention.md). |
| **Etapa 3**: Familiarize-se com rótulos DULE/RGPD, IDs do Adobe Analytics, namespaces e expansão da ID. | Leia os seguintes tópicos neste conjunto de documentação:<ul><li>[Rótulos do GDPR para variáveis do Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Práticas recomendadas de rotulagem](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-analytics-ids.html#concept_1BC4CA94B559481F8B08776DA100B23E)</li></ul> |
| **Etapa 4**: Atribua rótulos de identidade, sensibilidade e gerenciamento de dados a cada variável em um conjunto de relatórios. Observação: lembre-se de que a Rotulagem precisa ser analisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. Você também pode analisar a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. A reimplementação de aplicativos ou sites móveis pode alterar como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos. | Siga as instruções em [Rótulo dos dados](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-setup-reportsuite.html#concept_FAA948AD8CEA4BC38CB482EAF3648731)do conjunto de relatórios. |
| **Etapa 5**: Conecte-se à API do Adobe RGD e envie Acesso e Excluir solicitações. | Como cliente do Adobe Analytics, você pode enviar solicitações individuais do GDPR para acessar e excluir dados do cliente, ao chamar a [API do GDPR da Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html).  É possível enviar qualquer identificador do Analytics (conforme descrito na seção [Práticas recomendadas de rotulagem](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-analytics-ids.html#concept_1BC4CA94B559481F8B08776DA100B23E)) nas solicitações, junto com suas respectivas IDs de namespace (IDs da fonte de dados). |
| **Etapa 6**: Visualize e gerencie as configurações do RGD do conjunto de relatórios. | Siga as instruções em [Visualizar configurações de gerenciamento de dados do conjunto de relatórios](/help/admin/c-data-governance/gdpr-view-settings.md). |