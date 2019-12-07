---
description: 'null'
title: Conector de dados inteligente para o Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

Essa integração inclui os seguintes benefícios principais:

* Consolide os dados de marketing e análise de email em uma interface de relatório.
* Otimize campanhas de email por conversão e contribuição para a receita e o sucesso do site.
* Recomercialize para visitantes principais e segmentos de mercado com base em segmentos de marketing dinâmicos.

## Segmentos dinâmicos de marketing {#section-a2216f3339304636bd5417249bd635a4}

Esta integração de email oferece suporte a segmentos dinâmicos de marketing para ajudá-lo a orientar sua empresa. Essa integração apresenta os seguintes segmentos de marketing, prontos para uso:

| Segmento | Descrição |
|---|---|
| **Perfil de abandono do carrinho** | Ajude os visitantes a converterem-se aos clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em preencher carrinhos. |
| **Perfil de compras** | Aumente os pedidos repetidos e o valor médio do pedido por meio de campanhas direcionadas pelos padrões de compra do visitante. |
| **Perfil comportamental de exibição de produto/conteúdo** | Alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo. |
| **Segmentos personalizados de remarketing** | Os clientes também podem criar e agendar segmentos personalizados de remarketing específicos às necessidades de seus usuários. |

## Antes de ativar esta integração{#before-you-activate-this-integration}

Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics e do software de email.

Isso garantirá que as práticas recomendadas e pré-requisitos apropriados estejam em vigor antes da ativação. Isso resultará em uma integração ideal e bem-sucedida.

## Pré-requisitos para o Adobe Analytics{#prerequisites-for-adobe-analytics}

Lista as ações necessárias a serem executadas no Adobe Analytics antes de implantar a integração.

| Pré-requisitos | Notas |
|---|---|
| Selecione o Conjunto de relatórios |  Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração. |
| Configurar variáveis do Analytics |  Essa integração exige eventos personalizados e eVars personalizadas, além de eventos adicionais e eVars adicionais. Consulte Configuração de variáveis do Analytics para selecionar. |
| Representante autorizado |  Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima. |
| Ativar o Adobe Data Warehouse™ | Essa integração exige que o Data Warehouse seja habilitado para gerar segmentos de recomercialização. Se você não tiver ativado o Adobe Data Warehouse, entre em contato com a Adobe para obter detalhes. |
| Recipient ID | A integração exige que capturemos e armazenemos uma "ID de visitante" em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema inteligente. Essa "ID do destinatário" está associada ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é devolvido ao sistema SelIntelligent e pode ser aproveitado para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente. |
| Rastreamento externo | Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Selecionar abaixo para obter detalhes. |
| Conformidade com a privacidade |  Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por sua organização, como informar e dar o consentimento aos visitantes do site. |

## Configurar variáveis do Analytics para seleção{#configure-analytics-variables-for-selligent}

Essa integração exige que duas eVars sejam reservadas para cada implementação do conjunto de relatórios.

Além dessas eVars, alguns eventos podem ser reservados, dependendo dos dados da SelIntelligent, que você gostaria de ver no Analytics. Essas eVars e eventos são descritos abaixo:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variável </th> 
   <th colname="col2" class="entry"> Nome da variável </th> 
   <th colname="col3" class="entry"> Como é usado </th> 
   <th colname="col4" class="entry"> Configurações </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID da mensagem </td> 
   <td colname="col3"> Para capturar a identificação individual da campanha de mensagem de email. </td> 
   <td colname="col4"> <p><b>Status</b>: Ativado </p> <p><b>Alocação</b>: Mais recente </p> <p><b>Expirar após</b>: "Decisão da empresa" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Para capturar a identificação anônima do cliente que clicou na campanha de email. </td> 
   <td colname="col4"> <p><b>Status</b>: Ativado </p> <p><b>Alocação</b>: Mais recente </p> <p><b>Expirar após</b>: "Decisão da empresa" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviados </td> 
   <td colname="col3"> Para armazenar o número de emails enviados da SelIntelligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Entregue </td> 
   <td colname="col3"> Para armazenar o número de emails entregues. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Exibições </td> 
   <td colname="col3"> Para armazenar o número de emails exclusivos que foram exibidos. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Cliques </td> 
   <td colname="col3"> Para armazenar o número de vezes que qualquer email foi clicado. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Rejeitado </td> 
   <td colname="col3"> Para armazenar o número de emails que foram enviados. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pré-requisitos para a Seleção{#prerequisites-for-selligent}

Lista as informações necessárias para fornecer a partir de sua conta inteligente antes de implantar a integração.

**Conta Selinteligente válida**

Para usar essa integração dos Conectores de dados, é necessário ter uma conta SelIntelligent válida.

**Informações da Conta**

Você exigirá as seguintes informações sobre sua conta Inteligente durante essa configuração de integração:

* **URL** do serviço Adobe:

   O URL pode ser derivado do URL usado para fazer logon na solução de Marketing Inteligente. Substitua a parte "/simweb/login.aspx" do url por "/automation/omniture.asmx"

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** Parâmetros da string de consulta: Eles são anexados no URL da página inicial para ID da mensagem e ID do destinatário (ID do visitante). São sempre MID e RID para ID de mensagem e ID de destinatário, respectivamente.

* **Token** de integração Inicie a ferramenta Manager de dentro da Simweb e vá até **[!UICONTROL Configuração]** &gt; Configurações **** do sistema &gt; guia **[!UICONTROL Geral]** &gt; **[!UICONTROL Sistema]**. Em **[!UICONTROL Segurança]**, você pode encontrar o token Integração.

   ![](assets/selligent-integration_token.png)
