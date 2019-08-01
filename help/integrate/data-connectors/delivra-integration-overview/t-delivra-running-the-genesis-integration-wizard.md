---
description: O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.
seo-description: O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.
seo-title: Executar o assistente de integração dos Conectores de dados
title: Executar o assistente de integração dos Conectores de dados
uuid: 387 ac 9 d 0-3719-49 ff -81 cb -1 f 05 accf 9 b 6 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d55b23a5baf5be1d7afb708cc6ef94851eac3e77

---


# Running the Data Connectors Integration Wizard{#running-the-data-connectors-integration-wizard}

O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.

Para configurar a integração:

1. Fazer logon no Marketing Cloud. 
1. Na página inicial do Analytics, clique no ícone dos Conectores de dados™ no cata-vento ou na barra de ferramentas.
1. Na página Conectores de dados, selecione o Conjunto de relatórios onde deseja configurar a integração.

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Delivra** icon.
1. Drag the **Delivra** icon to an empty plug-in slot in your Analytics report suite to launch the Data Connectors Integration Wizard.
1. On the Delivra Integration introduction page, review the text, then select the check box to accept the fees associated with the integration, then click **Next**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há taxas da Adobe e de Entregas associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de taxas.
1. Em cada página do Assistente de integração dos Conectores de dados, forneça as informações necessárias, conforme descrito na tabela a seguir:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>PÁGINA DO ASSISTENTE #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIÇÃO</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nome da integração </p> </td> 
   <td colname="col3"> <p>Especifique o nome da integração que os Conectores de dados exibem na Lista de integração ativa do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Endereço de email de integração </p> </td> 
   <td colname="col3"> <p>Specify the email address that receives all notifications related to this integration, then click <b>Next</b> to proceed to Step 2 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col3"> <p>Specify your Delivra Account ID (the unique identifier assigned to your organization by Delivra), then click <b>Next</b> to proceed to Step 3 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID da mensagem </p> </td> 
   <td colname="col3"> <p>Identifique a evar do Analytics usada para rastrear a ID da mensagem de email. </p> <p>A ID da mensagem é usada para campanhas de marketing/remarketing. A ID da mensagem é geralmente chamada de "Código de rastreamento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identifique a evar do Analytics usada para rastrear a ID do destinatário do e-mail. </p> <p>A ID do destinatário é usada para campanhas de marketing/remarketing. A ID da mensagem é geralmente chamada de "Código do visitante". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Caixa de seleção de aceitação </p> </td> 
   <td colname="col3"> <p>Revise as informações exibidas ao lado da caixa de seleção Aceitar: </p> <p><i>Entendo que ao ativar o rastreamento "ID do destinatário", esse recurso pode rastrear informações de identificação pessoal de nossos visitantes do site. This has privacy implications requiring the implementation of appropriate procedures by my organization, such as providing notice to, and consent of, our site visitors. </i> </p> <p>If you agree to the acceptance statement, select the check box, then click <b>Next</b> to proceed to Step 4 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos de nível de conjunto de relatórios definidos pelo cliente </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos no lado esquerdo da página Segmentos de integração do Assistente de integração. </p> <p>Além disso, você pode selecionar segmentos existentes no Nível do conjunto de relatórios para incluir na integração. </p> <p>Select the desired segments on the right side of the page, then click <b>Next</b> to proceed to Step 5 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicado </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados clicados por email importados do sistema de email. </p> <p>O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Abertos </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados abertos por email importados do sistema de email. </p> <p>O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Enviado </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados Enviados por email importados do sistema de email. </p> <p>O evento Clicado permite visualizar o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Total de rejeições </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena o e-mail Total de dados importados do sistema de email. </p> <p>O evento Total de rejeições permite ver o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Cancelar inscrição </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena o email Cancelar assinatura de dados importados do sistema de email. </p> <p>O evento Cancelar inscrição permite ver o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> Compartilhamentos </td> 
   <td colname="col3"> <p>Specify the number of times the email message was shared to a social network, then click <b>Next</b> to proceed to Step 6 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: Plug-in javascript </p> </td> 
   <td colname="col3"> <p>Select <b>JavaScript Plug-in</b> if you want to use the plug-in as the collection model for this integration, then click <b>Next</b> to proceed to Step 7 of the Wizard. </p> <p> <p>Observação: A Solução automatizada é a seleção padrão. </p> </p> <p>Entre em contato com seu consultor Adobe para obter uma cópia do plug-in javascript usado para essa integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: Solução automatizada </p> </td> 
   <td colname="col3"> <p>Select <b>Automated Solution</b> if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. </p> <p> <p>Observação: A Solução automatizada é a seleção padrão. </p> </p> <p>Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração: </p> <p><b>Parâmetro da string de consulta da ID da mensagem:</b>Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail. </p> <p><b>Parâmetro da sequência de consulta da ID do destinatário:</b> Esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail. </p> <p>Click <b>Next</b> to proceed to Step 7 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumo de integração </p> </td> 
   <td colname="col3"> <p>Verify the integration parameters by clicking the plus sign (+) next to each category, then click <b>Save</b> to proceed to Step 8 of the Wizard. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integração concluída </p> </td> 
   <td colname="col3"> <p>Click <b>Finish</b> to complete the integration. </p> <p><b>IMPORTANTE:</b> O Analytics não salva as configurações de integração até que você clique <b>em Concluir</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

