---
description: A caixa de diálogo Governança de dados nas Ferramentas administrativas fornece uma visão geral de quais conjuntos de relatórios foram configurados para a governança de dados, se foram mapeados para uma organização da Experience Cloud e se uma política de retenção de dados está em vigor para este conjunto de relatórios.
seo-description: A caixa de diálogo Governança de dados nas Ferramentas administrativas fornece uma visão geral de quais conjuntos de relatórios foram configurados para a governança de dados, se foram mapeados para uma organização da Experience Cloud e se uma política de retenção de dados está em vigor para este conjunto de relatórios.
seo-title: Exibir/gerenciar as configurações de governança de dados do conjunto de relatórios
title: Exibir/gerenciar as configurações de governança de dados do conjunto de relatórios
uuid: f 3 b 83 e 8 e -00 af -4 a 60-a 5 de -29 b 5 c 43 f 6788
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Exibir/gerenciar as configurações de governança de dados do conjunto de relatórios

A caixa de diálogo Governança de dados nas Ferramentas administrativas fornece uma visão geral de quais conjuntos de relatórios foram configurados para a governança de dados, se foram mapeados para uma organização da Experience Cloud e se uma política de retenção de dados está em vigor para este conjunto de relatórios.

1. Faça logon na Adobe Experience Cloud.
1. Navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Governance]** .

   Você verá todos os conjuntos de relatórios que fazem parte da empresa de logon:

   ![](assets/gdpr_setup_an.png)

<table id="table_448292730FF0475E9DCB731882F9A29B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Conjuntos de relatórios </p> </td> 
   <td colname="col2"> <p>A primeira linha lista o nome amigável do conjunto de relatórios. A segunda linha contém o nome interno do conjunto de relatórios. Se você tiver permissão para definir rótulos para um conjunto de relatórios, a primeira linha será um link clicável que encaminhará você à página de rotulagem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mapeamento da organização </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EF8F613B0C5E42D19DB60BD0C89C114B"> 
     <li id="li_B35EE88555F547EFBF55ADE9D0C9EC3B"><b>Mapeado</b>: esse conjunto de relatórios já foi mapeado para a mesma organização da Experience Cloud que a empresa de logon do Analytics na qual você está conectado. Somente conjuntos de relatórios com essa configuração podem ser rotulados. </li> 
     <li id="li_4E800BF80CFF477BAA091EF272D9071C"><b>Mapear conjunto de relatórios</b>: ao clicar neste link, você <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">mapeia um conjunto de relatórios</a> para uma organização da Experience Cloud. <p>Isso significa que você será redirecionado para a organização da Experience Cloud - Mapeamento do conjunto de relatórios, onde é necessário encontrar o conjunto de relatórios e atribuí-lo à organização apropriada. Feito isso, retorne a essa interface do usuário de Governança de dados. </p> </li> 
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>Mapeado para outra organização</b>: outra organização da Experience Cloud já mapeou esse conjunto de relatórios para uma organização. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política de retenção de dados </p> </td> 
   <td colname="col2"> <p>A implementação do GDPR do Analytics exige que você tenha uma política de retenção de dados em vigor. </p> <p>Esta configuração mostra se </p> 
    <ul id="ul_AC1F0827293B47E39BFEC4B1766A0CAC"> 
     <li id="li_3AAD93EA92B94C6180E5AEBC5E4D10FB">uma política de retenção de dados está em vigor para este conjunto de relatórios e </li> 
     <li id="li_2E8D71905C734F8BB3245FEEDA953B3E">por quanto tempo os dados ficam retidos pela Adobe antes de serem excluídos. O período de retenção de dados padrão é de 25 meses. </li> 
    </ul> <p>Observação: o Adobe Analytics não pode ajudá-lo com o processamento de solicitações da API do GDPR (ou seja, com o processamento de solicitações de acesso ou de exclusão recebidas dos usuários finais), se um período de retenção de dados não tiver sido definido. Entre em contato com o gerente de sucesso do cliente para definir o período de retenção de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grupos </p> </td> 
   <td colname="col2"> <p>Atualmente, o recurso de agrupamento não está implementado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Barra à esquerda </p> </td> 
   <td colname="col2"> <p>Clique no ícone de funil para abrir ou fechar a barra lateral. </p> <p>A seção Mapeamento da organização exibe o número de conjuntos de relatórios que se enquadram em cada uma das categorias descritas. </p> <p>A seção Política de retenção de dados exibe cada política de retenção de dados exclusiva, atualmente em vigor para a sua organização, e o número de conjuntos de relatórios atribuídos a mesma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exportar para CSV </p> </td> 
   <td colname="col2"> <p>Se você marcar a caixa de seleção próxima de um ou mais conjuntos de relatórios, a opção <span class="uicontrol">Exportar para CSV</span> será exibida. Essa opção permite baixar um arquivo CSV que contenha todas as definições de rótulo atuais de todas as variáveis para todos os conjuntos de relatórios selecionados. </p> <p>Recomendamos que a sua equipe jurídica analise as escolhas de rotulagem e essa opção facilita a análise. Em vez de precisar executar a análise enquanto estiver conectado à interface do usuário na Governança de dados, você pode compartilhar o arquivo CSV com a equipe. </p> <p><img placement="break"  src="assets/export_csv.png" width="300px" id="image_5FE821B2D07B402D8E0F6FE53D6FC52E" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

