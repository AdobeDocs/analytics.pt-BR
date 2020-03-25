---
description: 'null'
title: Conector de dados do Selligent para Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conector de dados do Selligent para Adobe Analytics {#selligent-data-connector-for-adobe-analytics}

Essa integração inclui os seguintes benefícios principais:

* Consolidar dados de email marketing e de análise em uma interface de relatório.
* Otimizar campanhas de email por conversão e por contribuição para a receita e o sucesso do site.
* Remarketing para visitantes e segmentos de mercado importantes com base em segmentos de marketing dinâmicos.

## Segmentos de marketing dinâmicos {#section-a2216f3339304636bd5417249bd635a4}

Essa integração de email oferece suporte a segmentos de marketing dinâmicos para ajudar você a orientar sua empresa. Essa integração apresenta os seguintes segmentos de marketing, prontos para uso:

| Segmento | Descrição |
|---|---|
| **Perfil de abandono de carrinho** | Ajude a conversão de visitantes em clientes usando campanhas ajustadas especificamente projetadas para quem está hesitante em concluir a compra em carrinhos. |
| **Perfil de compras** | Aumente os pedidos repetidos e o valor médio do pedido por meio de campanhas direcionadas pelos padrões de compra do visitante. |
| **Perfil comportamental de exibição de produto/conteúdo** | Alcance clientes em potencial por meio de segmentos de marketing baseados em exibições de produtos e criação de perfis de acesso ao conteúdo. |
| **Segmentos de remarketing personalizados** | Os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades dos usuários. |

## Antes de ativar essa integração {#before-you-activate-this-integration}

Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics e do seu software de email.

Isso garantirá que as práticas recomendadas e pré-requisitos apropriados estejam em vigor antes da ativação. Isso resultará em uma integração ideal e bem-sucedida.

## Pré-requisitos para o Adobe Analytics {#prerequisites-for-adobe-analytics}

Lista as ações necessárias a serem executadas no Adobe Analytics antes de implantar a integração.

| Pré-requisito | Notas |
|---|---|
| Selecione o Conjunto de relatórios | Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração. |
| Configurar variáveis do Analytics | Essa integração exige o uso de eventos e eVars personalizadas, bem como eventos e eVars adicionais. Consulte Configuração de variáveis do Analytics para o Selligent. |
| Representante autorizado | Esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima. |
| Ativar o Adobe Data Warehouse™ | Essa integração exige que o Data Warehouse esteja habilitado para gerar segmentos de remarketing. Se você não tiver ativado o Adobe Data Warehouse, entre em contato com a Adobe para obter detalhes. |
| ID de destinatário | A integração exige a captura e o armazenamento de um “ID de visitante” em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de &quot;ID de destinatário&quot;) é uma representação codificada ou numérica de um endereço de email do sistema Selligent. Essa &quot;ID de destinatário&quot; está associada ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é devolvido ao sistema Selligent e pode ser aproveitado para fins de remarketing. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente. |
| Rastreamento externo | Se, atualmente, você não estiver seguindo a prática recomendada de ativação do rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Selligent abaixo para obter detalhes. |
| Conformidade com privacidade | Você deve entender que, ao ativar o rastreamento de ID de destinatário ou de visitante, esse recurso pode rastrear informações de identificação pessoal de visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte da sua organização, como informar os visitantes do site e dar o consentimento deles. |

## Configurar variáveis do Analytics para o Selligent {#configure-analytics-variables-for-selligent}

Essa integração exige que duas eVars sejam reservadas para cada implementação do conjunto de relatórios.

Além dessas eVars, alguns eventos podem ser reservados, a depender de quais dados do Selligent você gostaria de ver no Analytics. Essas eVars e eventos são descritos abaixo:

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
   <td colname="col2"> ID de mensagem </td> 
   <td colname="col3"> Para capturar a identificação individual da campanha de mensagem de email. </td> 
   <td colname="col4"> <p><b>Status</b>: Ativado </p> <p><b>Alocação</b>: Mais recente </p> <p><b>Expirar após</b>: "Decisão da empresa" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de destinatário </td> 
   <td colname="col3"> Para capturar a identificação anônima do cliente que clicou na campanha de email. </td> 
   <td colname="col4"> <p><b>Status</b>: Ativado </p> <p><b>Alocação</b>: Mais recente </p> <p><b>Expirar após</b>: "Decisão da empresa" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> Para armazenar o número de emails enviados por meio do Selligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Entregues </td> 
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
   <td colname="col3"> Para armazenar o número de emails que foram rejeitados. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pré-requisitos para o Selligent {#prerequisites-for-selligent}

Lista as informações necessárias da sua conta do Selligent a serem fornecidas antes de implantar a integração.

**Conta Selligent válida**

Para usar essa integração dos Data Connectors, é necessário ter uma conta Selligent válida.

**Informações da conta**

Serão necessários as seguintes informações sobre sua conta do Selligent durante a configuração dessa integração:

* **URL de serviço Adobe**:

   O URL pode ser derivado do URL usado para fazer logon na solução Selligent Marketing. Substitua a parte “/simweb/login.aspx” do url por “/automation/omniture.asmx”

   Ou seja: `http://<client-specific install url>/automation/omniture.asmx`

* **Parâmetros da string de consulta:** eles são anexados ao URL da página inicial para transmitir a ID da mensagem e a ID do destinatário (ID do visitante). São sempre MID e RID para ID de mensagem e ID de destinatário, respectivamente.

* **Token de integração** Inicie a ferramenta Gerenciador de dentro do Simweb e vá até **[!UICONTROL Configuração]** > **[!UICONTROL Configurações do sistema]** > guia **[!UICONTROL Geral]** > **[!UICONTROL Sistema]**. Em **[!UICONTROL Segurança]**, você pode encontrar o token da integração.

   ![](assets/selligent-integration_token.png)
