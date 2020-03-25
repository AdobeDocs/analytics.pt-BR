---
description: O Assistente de integração do Data Connectors guia você durante o processo de integração.
title: Execução do Assistente de integração do Data Connectors
uuid: 387ac9d0-3719-49ff-81cb-1f05accf9b6c
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Execução do Assistente de integração do Data Connectors {#running-the-data-connectors-integration-wizard}

O Assistente de integração do Data Connectors guia você durante o processo de integração.

Para configurar a integração:

1. Fazer Logon na Experience Cloud.
1. Na página inicial do Analytics, clique no ícone Data Connectors™ no cata-vento ou na barra de ferramentas.
1. Na página Data Connectors, selecione o Conjunto de relatórios no qual deseja configurar a integração.

   >[!NOTE]
   >
   >Certifique-se de selecionar o conjunto de relatórios desejado na lista suspensa **Conjunto de relatórios** no canto superior esquerdo da página Data Connectors.

1. Clique na guia **Alfabético** na parte superior da **Lista de parceiros** no lado esquerdo da interface do usuário do Data Connectors e localize o ícone **Delivra**.
1. Arraste o ícone **Delivra** para um slot de plug-in vazio no conjunto de relatórios do Analytics para iniciar o Assistente de integração do Data Connectors.
1. Na página de introdução da Integração do Delivra, veja o texto, marque a caixa de seleção para aceitar as tarifas associadas à integração e clique em **Avançar**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há tarifas da Adobe e do Delivra associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de tarifas.
1. Em cada página do Assistente de integração dos Data Connectors, forneça as informações necessárias, conforme descrito na tabela a seguir:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>PÁGINA DO ASSISTENTE #</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>CAMPO</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIÇÃO</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nome da integração </p> </td> 
   <td colname="col3"> <p>Especifique o nome da integração que o Data Connectors exibe na lista Integração ativa do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Endereço de email de integração </p> </td> 
   <td colname="col3"> <p>Especifique o endereço de email que recebe todas as notificações relacionadas a essa integração e clique em <b>Avançar</b> para prosseguir para a Etapa 2 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col3"> <p>Especifique a ID de conta do Delivra (o identificador exclusivo atribuído à organização pelo Datran) e clique em <b>Avançar</b> para prosseguir para a Etapa 3 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID de mensagem </p> </td> 
   <td colname="col3"> <p>Identifique a eVar do Analytics usada para rastrear a ID da mensagem de email. </p> <p>A ID da mensagem é usada para campanhas de marketing/remarketing. A ID da mensagem geralmente é chamada de "Código de rastreamento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID de destinatário </p> </td> 
   <td colname="col3"> <p>Identifique a eVar do Analytics usada para rastrear a ID do destinatário do email. </p> <p>A ID do destinatário é usada para campanhas de marketing/remarketing. A ID da mensagem geralmente é chamada de "Código do visitante". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Caixa de seleção Aceitação </p> </td> 
   <td colname="col3"> <p>Revise as informações exibidas ao lado da caixa de seleção Aceitação: </p> <p><i>Entendo que ao ativar o rastreamento da "ID do destinatário", esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por minha organização, como informar e dar o consentimento aos visitantes do site. </i> </p> <p>Se você concordar com a declaração de aceitação, marque a caixa de seleção e clique em <b>Avançar</b> para prosseguir para a Etapa 4 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos no nível do conjunto de relatórios definidos pelo cliente </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos no lado esquerdo da página Segmentos de integração do Assistente de integração. </p> <p>Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. </p> <p>Selecione os segmentos desejados no lado direito da página e clique em <b>Avançar</b> para prosseguir para a Etapa 5 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicados </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados de email Clicados importados do sistema de email. </p> <p>O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Abertos </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados de email Abertos importados do sistema de email. </p> <p>O evento Abertos permite ver o número de visitantes que abriram a mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Enviados </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados de email Enviados importados do sistema de email. </p> <p>O evento Clicados permite ver o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Total de rejeições </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados de Total de rejeições de email importados do sistema de email. </p> <p>O evento Total-Bounces permite ver a quantidade de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Inscrições canceladas </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Analytics que armazena os dados de Cancelamento de inscrição de email importados do sistema de email. </p> <p>O evento Inscrições canceladas permite ver quantos visitantes abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> Compartilhamentos </td> 
   <td colname="col3"> <p>Especifique o número de vezes que a mensagem de email foi compartilhada em uma rede social e clique em <b>Avançar</b> para prosseguir para a Etapa 6 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: plug-in JavaScript </p> </td> 
   <td colname="col3"> <p>Selecione <b>Plug-in do JavaScript</b> se desejar usar o plug-in como o modelo de coleção dessa integração, em seguida, clique em <b>Avançar</b> para prosseguir para a Etapa 7 do Assistente. </p> <p> <p>Observação: a Solução automatizada é a seleção padrão. </p> </p> <p>Entre em contato com o consultor da Adobe para obter uma cópia do plug-in JavaScript usado nessa integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: solução automatizada </p> </td> 
   <td colname="col3"> <p>Selecione <b>Solução automatizada</b> se desejar usar um modelo de coleta automatizada para essa integração e, depois, especifique os identificadores exclusivos usados nessa integração. </p> <p> <p>Observação: a Solução automatizada é a seleção padrão. </p> </p> <p>Se você selecionar essa opção, especifique os identificadores exclusivos usados nessa integração: </p> <p><b>Parâmetro da cadeia de caracteres de consulta da ID da mensagem:</b> esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de email. </p> <p><b>Parâmetro da cadeia de caractere de consulta da ID do destinatário:</b> esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de email. </p> <p>Clique em <b>Avançar</b> para prosseguir para a Etapa 7 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumo da integração </p> </td> 
   <td colname="col3"> <p>Verifique os parâmetros de integração clicando no sinal de adição (+) ao lado de cada categoria e clique em <b>Salvar</b> para prosseguir para a Etapa 8 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integração concluída </p> </td> 
   <td colname="col3"> <p>Clique em <b>Concluir</b> para concluir a integração. </p> <p><b>IMPORTANTE:</b> o Analytics não salva as configurações de integração até que você clique em <b>Concluir</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>
