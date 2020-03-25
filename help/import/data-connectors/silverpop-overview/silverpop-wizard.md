---
description: O Assistente de integração do Data Connectors guia você durante o processo de integração.
title: Integração do Silverpop
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Integração do Silverpop {#silverpop-integration}

O Assistente de integração do Data Connectors guia você durante o processo de integração.

Para configurar a integração:

1. Na Adobe Experience Cloud, selecione Data Connectors™ na lista suspensa de produtos.
1. Clique em **[!UICONTROL Adicionar novo]** e selecione **[!UICONTROL Por nome]** na lista suspensa **[!UICONTROL Mostrar]**.
1. Encontre o ícone **Silverpop Engage 2.0** e arraste-o para um slot de plug-in vazio em seu conjunto de relatórios do Analytics para iniciar o Assistente de integração dos Data Connectors.
1. Na página de introdução da integração do Silverpop, revise o texto e marque a caixa de seleção para aceitar as tarifas associadas à integração.
1. Selecione o Conjunto de relatórios que deseja usar nessa integração.
1. Forneça um nome amigável para identificar essa integração e clique em **[!UICONTROL Criar e configurar essa integração]**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há tarifas da Adobe e do Silverpop associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de tarifas.
1. Em cada página do Assistente de integração dos Data Connectors, forneça as informações necessárias, conforme descrito na tabela a seguir:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>Campo</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>Seção Configuração</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Descrição</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Nome da integração </p> </td> 
   <td colname="col03"> <p>(1) Configurações de integração </p> </td> 
   <td colname="col3"> <p>Especifique o nome da integração que o Data Connectors exibe na lista Integração ativa do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Baixar arquivo </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p> Para uso com remarketing após download de arquivo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Endereço de email </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Usada em remarketing para visitantes sem uma ID do Silverpop conhecida. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Especifique sua ID de conta do Silverpop (o identificador exclusivo atribuído à sua organização pelo Silverpop) e clique em <b>Avançar</b> para prosseguir para a Etapa 3 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Nome do formulário </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Para uso no remarketing após abandonos de formulário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID de mala direta </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID do Silverpop </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Devoluções </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de total de rejeições de email importados do sistema de email. </p> <p>O evento Total-Bounces permite ver a quantidade de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Clicados </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de email clicados importados do sistema de email. </p> <p>O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Arquivo baixado </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p> Para uso com remarketing após download de arquivo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formulário concluído </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Para uso no remarketing após abandonos de formulário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formulário iniciado </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Para uso no remarketing após abandonos de formulário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Abertos </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de email abertos importados do sistema de email. </p> <p>O evento Abertos permite ver o número de visitantes que abriram a mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Enviado </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de email Enviado importados do sistema de email. </p> <p>O evento Enviado permite ver o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Inscrições canceladas </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de Cancelamento de inscrição de email importados do sistema de email. </p> <p>O evento Inscrições canceladas permite ver quantos visitantes abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segmentos </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. </p> <p>Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Solicitações de acesso </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p> (Obrigatório) Ativar <span class="uicontrol"> Permita que essa integração baixe dados de produtos</span>. </p> <p>Opcional: permita que essa integração baixe dados de receita, pedidos e unidades. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Coleta de dados </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p>Selecione <b>Plug-in do JavaScript</b> se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração (consulte <a href="../silverpop-overview/silverpop-analytics-code.md">Código do plug-in do Analytics</a>). </p> <p>Selecione <b>Solução automatizada</b> se desejar usar um modelo de coleta automatizada para essa integração e, depois, especifique os identificadores exclusivos usados nessa integração. </p> <p>Se você selecionar essa opção, especifique os identificadores exclusivos usados nessa integração: </p> <p> <b>Parâmetro da string de consulta da ID da mensagem:</b> esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email. </p> <p> <b>Parâmetro da string de consulta da ID de destinatário:</b> esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Geração de painel e marcador </p> </td> 
   <td colname="col03"> <p>(4) Configurações do relatório </p> </td> 
   <td colname="col3"> <p>Gera automaticamente um painel e marcadores para a integração. </p> </td> 
  </tr> 
 </tbody> 
</table>

