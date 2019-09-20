---
description: O Assistente de integração dos Conectores de dados o orientará pelo processo de integração dos Conectores de dados.
seo-description: O Assistente de integração dos Conectores de dados o orientará pelo processo de integração dos Conectores de dados.
seo-title: Integração do Silverpop
title: Integração do Silverpop
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Integração do Silverpop{#silverpop-integration}

O Assistente de integração dos Conectores de dados o orientará pelo processo de integração dos Conectores de dados.

Para configurar a integração:

1. Na Adobe Experience Cloud, selecione Conectores de dados™ na lista suspensa de produtos.
1. Clique em **[!UICONTROL Adicionar novo]** e selecione **[!UICONTROL Por nome]** na lista suspensa **[!UICONTROL Mostrar]** .
1. Encontre o ícone do **Silverpop Engage 2.0** e arraste-o para um slot de plug-in vazio em seu conjunto de relatórios do Analytics para iniciar o Assistente de integração dos conectores de dados.
1. Na página de introdução da Integração do Silverpop, reveja o texto e marque a caixa de seleção para aceitar as taxas associadas à integração.
1. Selecione o Conjunto de relatórios que deseja usar para essa integração.
1. Forneça um nome amigável para identificar essa integração e clique em **[!UICONTROL Criar e configurar essa integração]**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há taxas da Adobe e do Silverpop associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de taxas.
1. Em cada página do Assistente de integração dos conectores de dados, forneça as informações necessárias, conforme descrito na tabela a seguir:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>Campo</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>Seção de configuração</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Descrição</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Nome da integração </p> </td> 
   <td colname="col03"> <p>(1) Configurações de integração </p> </td> 
   <td colname="col3"> <p>Especifique o nome da integração que os Conectores de dados exibem na lista Integração ativa do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Baixar arquivo </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p> Para uso com remarketing de download de arquivo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Usada para remarketing de visitantes sem uma ID Silverpop conhecida. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Especifique sua ID de conta do Silverpop (o identificador exclusivo atribuído à sua organização pelo Silverpop) e clique em <b>Avançar</b> para prosseguir para a Etapa 3 do Assistente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Nome do formulário </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Para uso com recomercialização de abandono de formulário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID de correspondência </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Devoluções </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório)Especifique o evento do Analytics que armazena os dados de Rejeições totais de email importados do sistema de email. </p> <p>O evento Total-Rejeições permite que você veja o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Clicado </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório)Especifique o evento do Analytics que armazena os dados de e-mail clicados importados do sistema de e-mail. </p> <p>O evento Clicado permite que você veja o número de visitantes que clicaram na mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Arquivo baixado </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p> Para uso com remarketing de download de arquivo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formulário concluído </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Para uso com recomercialização de abandono de formulário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Formulário iniciado </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Para uso com recomercialização de abandono de formulário. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Aberto </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados Abertos por email importados do sistema de email. </p> <p>O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Enviados </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de email enviados importados do sistema de email. </p> <p>O evento Enviado permite que você veja o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Inscrito </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados de e-mail Cancelar assinatura importados do sistema de e-mail. </p> <p>O evento Cancelado de inscrição permite que você veja o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segmentos </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. </p> <p>Além disso, você pode selecionar segmentos existentes no nível do conjunto de relatórios para incluir na integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Solicitações de acesso </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p> (Obrigatório) Ative <span class="uicontrol"> Permitir que essa integração baixe dados</span>do produto. </p> <p>Opcional: Permite que essa integração baixe receita, pedidos e unidades. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Coleta de dados </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p>Selecione Plug-in <b>de</b> JavaScript se desejar usar o plug-in s_code.js como o modelo de coleção para essa integração (consulte <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Código</a>de plug-in do Analytics). </p> <p>Selecione Solução <b></b> automatizada se desejar usar um modelo de coleta automatizada para essa integração e especifique os identificadores exclusivos usados para essa integração. </p> <p>Se você selecionar essa opção, especifique os identificadores exclusivos usados para essa integração: </p> <p> <b>Parâmetro da string de consulta da ID da mensagem:</b>esse valor representa a ID da mensagem anexada ao URL da página inicial pelo seu parceiro de email. </p> <p> <b></b> Parâmetro da string de consulta da ID do destinatário: Esse valor representa a ID do destinatário anexada ao URL da página inicial pelo seu parceiro de email. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Geração de painel e marcador </p> </td> 
   <td colname="col03"> <p>(4) Configurações do relatório </p> </td> 
   <td colname="col3"> <p>Gerar automaticamente um painel e marcadores para a integração. </p> </td> 
  </tr> 
 </tbody> 
</table>

