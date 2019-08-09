---
description: O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.
seo-description: O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.
seo-title: Executar o assistente de integração dos Conectores de dados
title: Executar o assistente de integração dos Conectores de dados
uuid: 714417 f 7-c 1 df -4 e 61-a 07 f-d 319 f 6581 c 9 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Executar o assistente de integração dos Conectores de dados{#running-the-data-connectors-integration-wizard}

O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.

Para configurar a integração:

1. Fazer logon no Marketing Cloud. 
1. Na página inicial do Adobe Analytics, clique no ícone dos Conectores de dados™ no cata-vento ou na barra de ferramentas.
1. Na página Conectores de dados, selecione o Conjunto de relatórios onde deseja configurar a integração.

   >[!NOTE]
   >
   >Certifique-se de selecionar o conjunto de relatórios desejado na lista **suspensa Conjunto** de relatórios, no canto superior esquerdo da página Conectores de dados.

1. Clique na **guia Alfabética** na parte superior da Lista **de parceiros** no lado esquerdo da interface do usuário dos Conectores de dados e localize o **ícone Datran** .
1. Arraste o **ícone Datran** até um slot de plug-in vazio no conjunto de relatórios do Adobe Analytics para iniciar o Assistente de integração dos Conectores de dados.

1. Na página de introdução da Integração Datran, revise o texto e marque a caixa de seleção para aceitar as taxas associadas à integração e clique **em Avançar**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há taxas da Adobe e Datran associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de taxas.
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
   <td colname="col3"> <p>Especifique o endereço de email que recebe todas as notificações relacionadas a essa integração e clique <b>em Avançar</b> para ir para a Etapa 2 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col3"> <p>Especifique a ID da conta de datran (o identificador exclusivo atribuído à sua organização por Datran) e clique <b>em Avançar</b> para ir para a Etapa 3 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID da mensagem </p> </td> 
   <td colname="col3"> <p>Identifique a evar do Adobe Analytics usada para rastrear a ID da mensagem de email. </p> <p>A ID da mensagem é usada para campanhas de marketing/remarketing. A ID da mensagem é geralmente chamada de "Código de rastreamento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Recipient ID </p> </td> 
   <td colname="col3"> <p>Identifique a evar do Adobe Analytics usada para rastrear a ID do destinatário do e-mail. </p> <p>A ID do destinatário é usada para campanhas de marketing/remarketing. A ID da mensagem é geralmente chamada de "Código do visitante". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Caixa de seleção de aceitação </p> </td> 
   <td colname="col3"> <p>Revise as informações exibidas ao lado da caixa de seleção Aceitar: </p> <p><i>Entendo que ao ativar o rastreamento "ID do destinatário", esse recurso pode rastrear informações de identificação pessoal de nossos visitantes do site. Isso tem implicações de privacidade que requerem a implementação dos procedimentos apropriados pela minha organização, como fornecer aviso e consentimento de nossos visitantes do site. </i> </p> <p>Se você concordar com a declaração de aceitação, marque a caixa de seleção e clique <b>em Avançar</b> para ir para a Etapa 4 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmentos de nível de conjunto de relatórios definidos pelo cliente </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos no lado esquerdo da página Segmentos de integração do Assistente de integração. </p> <p>Além disso, você pode selecionar segmentos existentes no Nível do conjunto de relatórios para incluir na integração. </p> <p>Selecione os segmentos desejados no lado direito da página e clique <b>em Avançar</b> para ir para a Etapa 5 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clicado </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados clicados por email importados do sistema de email. </p> <p>O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Abertos </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados abertos por email importados do sistema de email. </p> <p>O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Enviado </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena os dados enviados por email importados do sistema de email. </p> <p>O evento Clicado permite visualizar o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Total de rejeições </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena o e-mail Total de dados importados do sistema de email. </p> <p>O evento Total de rejeições permite ver o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Cancelar inscrição </p> </td> 
   <td colname="col3"> <p>Especifique o evento do Adobe Analytics que armazena o email Cancelar assinatura de dados importados do sistema de email. </p> <p>O evento Cancelar inscrição permite ver o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> <p>Clique em Avançar para ir para a Etapa 6 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: Plug-in javascript </p> </td> 
   <td colname="col3"> <p>Selecione <b>o plug-in javascript</b> caso deseje usar o plug-in como o modelo de coleção para essa integração e clique <b>em Avançar</b> para ir para a Etapa 7 do assistente. </p> <p> <p>Observação: A Solução automatizada é a seleção padrão. </p> </p> <p>Entre em contato com seu consultor Adobe para obter uma cópia do plug-in javascript usado para essa integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Coleta de dados: Solução automatizada </p> </td> 
   <td colname="col3"> <p>Selecione <b>Solução automatizada</b> se quiser usar um modelo de coleção automatizado para essa integração e especifique os identificadores exclusivos usados para essa integração. </p> <p> <p>Observação: A Solução automatizada é a seleção padrão. </p> </p> <p>Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração: </p> <p><b>Parâmetro da string de consulta da ID da mensagem:</b>Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail. </p> <p><b>Parâmetro da sequência de consulta da ID do destinatário:</b> Esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail. </p> <p>Clique <b>em Avançar</b> para ir para a Etapa 7 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Resumo de integração </p> </td> 
   <td colname="col3"> <p>Verifique os parâmetros de integração clicando no sinal de mais (+) ao lado de cada categoria e clique <b>em Salvar</b> para ir para a Etapa 8 do assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integração concluída </p> </td> 
   <td colname="col3"> <p>Clique <b>em Concluir</b> para concluir a integração. </p> <p><b>IMPORTANTE:</b> O Adobe Analytics não salva as configurações de integração até que você clique <b>em Concluir</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

