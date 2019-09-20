---
description: O Assistente de integração dos Conectores de dados o orientará pelo processo de integração dos Conectores de dados.
seo-description: O Assistente de integração dos Conectores de dados o orientará pelo processo de integração dos Conectores de dados.
seo-title: Execução do Assistente de integração dos conectores de dados
title: Execução do Assistente de integração dos conectores de dados
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Execução do Assistente de integração dos conectores de dados{#running-the-data-connectors-integration-wizard}

O Assistente de integração dos Conectores de dados o orientará pelo processo de integração dos Conectores de dados.

Para configurar a integração:

1. Fazer Logon na Experience Cloud.
1. Na página inicial do Adobe Analytics, clique no ícone Conectores de dados™ no cata-vento ou na barra de ferramentas.
1. Na página Conectores de dados, selecione o Conjunto de relatórios no qual deseja configurar a integração.

   >[!NOTE]
   >
   >Certifique-se de selecionar o conjunto de relatórios desejado na lista suspensa Conjunto de **relatórios** no canto superior esquerdo da página Conectores de dados.

1. Clique na guia **Alfabético** na parte superior da Lista **de** parceiros no lado esquerdo da interface do usuário dos conectores de dados e localize o ícone **Datran** .
1. Arraste o ícone do **Datran** para um slot de plug-in vazio em seu conjunto de relatórios do Adobe Analytics para iniciar o Assistente de integração dos conectores de dados.

1. Na página de introdução da Integração do Datran, reveja o texto e marque a caixa de seleção para aceitar as taxas associadas à integração, em seguida, clique em **Avançar**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há taxas da Adobe e do Datran associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de taxas.
1. Em cada página do Assistente de integração dos conectores de dados, forneça as informações necessárias, conforme descrito na tabela a seguir:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>PÁGINA DO ASSISTENTE Nº</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>CAMPO</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIÇÃO</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nome da integração </p> </td> 
   <td colname="col3"> <p>Especifique o nome da integração que os Conectores de dados exibem na lista Integração ativa do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Endereço de email de integração </p> </td> 
   <td colname="col3"> <p>Especifique o endereço de email que recebe todas as notificações relacionadas a essa integração e clique em <b>Avançar</b> para prosseguir para a Etapa 2 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col3"> <p>Especifique sua ID de conta do Datran (o identificador exclusivo atribuído à sua organização pelo Datran) e clique em <b>Avançar</b> para prosseguir para a Etapa 3 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID da mensagem </p> </td> 
   <td colname="col3"> <p>Identifique a eVar do Adobe Analytics usada para rastrear a ID da mensagem de email. </p> <p>A ID da mensagem é usada para campanhas de marketing/remarketing. A ID da mensagem é geralmente chamada de "Código de rastreamento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identifique a eVar do Adobe Analytics usada para rastrear a ID do destinatário do email. </p> <p>A ID do destinatário é usada para campanhas de marketing/remarketing. A ID da mensagem é geralmente chamada de "Código do visitante". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Caixa de seleção Aceitação </p> </td> 
   <td colname="col3"> <p>Revise as informações exibidas ao lado da caixa de seleção Aceitação: </p> <p><i>Entendo que ao ativar o rastreamento de "ID do destinatário", esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte da minha organização, como informar os visitantes do site e o consentimento dos mesmos. </i> </p> <p>Se você concordar com a declaração de aceitação, marque a caixa de seleção e clique em <b>Avançar</b> para prosseguir para a Etapa 4 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos no nível do conjunto de relatórios definidos pelo cliente </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos no lado esquerdo da página Segmentos de integração do Assistente de integração. </p> <p>Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. </p> <p>Selecione os segmentos desejados no lado direito da página e clique em <b>Avançar</b> para prosseguir para a Etapa 5 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicado </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados de e-mail clicados importados do sistema de e-mail. </p> <p>O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Aberto </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados Abertos por email importados do sistema de email. </p> <p>O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Enviados </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados de email enviados importados do sistema de email. </p> <p>O evento Clicado permite que você veja o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Total de rejeições </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados de Rejeições totais de email importados do sistema de email. </p> <p>O evento Total-Rejeições permite que você veja o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Inscrito </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados de e-mail Cancelar assinatura importados do sistema de e-mail. </p> <p>O evento Cancelado de inscrição permite que você veja o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> <p>Clique em Avançar para prosseguir para a Etapa 6 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: Plug-in JavaScript </p> </td> 
   <td colname="col3"> <p>Selecione Plug-in <b></b> JavaScript se desejar usar o plug-in como o modelo de coleção para essa integração, em seguida, clique em <b>Avançar</b> para prosseguir para a Etapa 7 do Assistente. </p> <p> <p>Observação:  A Solução automatizada é a seleção padrão. </p> </p> <p>Entre em contato com seu consultor da Adobe para obter uma cópia do plug-in JavaScript usado para essa integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: Solução automatizada </p> </td> 
   <td colname="col3"> <p>Selecione Solução <b></b> automatizada se desejar usar um modelo de coleta automatizada para essa integração e especifique os identificadores exclusivos usados para essa integração. </p> <p> <p>Observação:  A Solução automatizada é a seleção padrão. </p> </p> <p>Se você selecionar essa opção, especifique os identificadores exclusivos usados para essa integração: </p> <p><b>Parâmetro da string de consulta da ID da mensagem:</b>esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email. </p> <p><b></b> Parâmetro da string de consulta da ID do destinatário: Esse valor representa a ID do destinatário anexada ao URL da página inicial pelo seu parceiro de email. </p> <p>Clique em <b>Avançar</b> para prosseguir para a Etapa 7 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumo da integração </p> </td> 
   <td colname="col3"> <p>Verifique os parâmetros de integração clicando no sinal de mais (+) ao lado de cada categoria e clique em <b>Salvar</b> para prosseguir para a Etapa 8 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integração concluída </p> </td> 
   <td colname="col3"> <p>Clique em <b>Concluir</b> para concluir a integração. </p> <p><b></b> IMPORTANTE: O Adobe Analytics não salva as configurações de integração até que você clique em <b>Concluir</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

