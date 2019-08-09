---
description: O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.
seo-description: O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.
seo-title: Integração com Silverpop
title: Integração com Silverpop
uuid: dc 5 e 6 a 09-3238-412 d -9980-4 a 105 ce 14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Integração com Silverpop{#silverpop-integration}

O Assistente de integração dos Conectores de dados executa o processo de integração dos Conectores de dados.

Para configurar a integração:

1. Na Adobe Marketing Cloud, selecione Conectores de dados™ na lista suspensa Produtos.
1. Clique **[!UICONTROL em Adicionar novo]** e selecione **[!UICONTROL Por nome]** na lista suspensa **[!UICONTROL Mostrar]** .
1. Encontre o **ícone Silverpop Mobilizar 2.0** e arraste-o até um slot de plug-in vazio no conjunto de relatórios do Analytics para iniciar o Assistente de integração dos Conectores de dados.
1. Na página de introdução da Integração Silverpop, revise o texto e marque a caixa de seleção para aceitar as taxas associadas à integração.
1. Selecione o Conjunto de relatórios que deseja usar para essa integração.
1. Forneça um nome amigável para identificar essa integração e clique **[!UICONTROL em Criar e configurar essa integração]**.

   Essa página contém uma visão geral da integração, além de links úteis para mais informações. Há taxas da Adobe e Silverpop associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de taxas.
1. Em cada página do Assistente de integração dos Conectores de dados, forneça as informações necessárias, conforme descrito na tabela a seguir:

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
   <td colname="col3"> <p>Especifique o nome da integração que os Conectores de dados exibem na Lista de integração ativa do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Baixar arquivo </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p> Para uso com o download de download de arquivo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Usado para recomercialização para visitantes sem uma ID Silverpop conhecida. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID da Conta </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>Especifique a ID da conta Silverpop (o identificador exclusivo atribuído à sua organização pelo Silverpop) e clique <b>em Avançar</b> para ir para a Etapa 3 do assistente. </p> </td> 
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
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena o e-mail Total de dados importados do sistema de email. </p> <p>O evento Total de rejeições permite ver o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Clicado </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados clicados por email importados do sistema de email. </p> <p>O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Arquivo baixado </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p> Para uso com o download de download de arquivo. </p> </td> 
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
   <td colname="col2"> <p>Abertos </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados abertos por email importados do sistema de email. </p> <p>O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Enviado </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena os dados Enviados por email importados do sistema de email. </p> <p>O evento Enviado permite que você veja o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Cancelar inscrição </p> </td> 
   <td colname="col03"> <p>(2) Mapeamentos de variáveis </p> </td> 
   <td colname="col3"> <p>(Obrigatório) Especifique o evento do Analytics que armazena o email Cancelar assinatura de dados importados do sistema de email. </p> <p>O evento Cancelar inscrição permite ver o número de visitantes que abriram a mensagem de email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segmentos </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p>Essa integração cria os segmentos definidos pelo parceiro exibidos na seção Segmentos do parceiro. </p> <p>Além disso, você pode selecionar segmentos existentes no Nível do conjunto de relatórios para incluir na integração. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Solicitações de acesso </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p> (Obrigatório) Ative <span class="uicontrol"> Permitir esta integração para baixar dados do produto</span>. </p> <p>Opcional: Permita essa integração para baixar receita, pedidos e unidades. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Coleção de dados </p> </td> 
   <td colname="col03"> <p>(3) Configurações de dados </p> </td> 
   <td colname="col3"> <p>Selecione <b>o plug-in javascript</b> caso deseje usar o plug-in s_ code. js como o modelo de coleta para essa integração (consulte <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Código de plug-in do Analytics</a>). </p> <p>Selecione <b>Solução automatizada</b> se quiser usar um modelo de coleção automatizado para essa integração e especifique os identificadores exclusivos usados para essa integração. </p> <p>Se você selecionar essa opção, especifique os identificadores únicos usados para essa integração: </p> <p> <b>Parâmetro da string de consulta da ID da mensagem:</b>Esse valor representa a ID da mensagem anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail. </p> <p> <b>Parâmetro da sequência de consulta da ID do destinatário:</b> Esse valor representa a ID do destinatário anexada ao URL da página de aterrissagem pelo seu parceiro de e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Geração de painel e marcador </p> </td> 
   <td colname="col03"> <p>(4) Configurações de relatório </p> </td> 
   <td colname="col3"> <p>Gerar automaticamente um painel e marcadores para a integração. </p> </td> 
  </tr> 
 </tbody> 
</table>

