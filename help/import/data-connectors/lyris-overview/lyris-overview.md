---
description: Descreve as eficiências de marketing obtidas por meio da integração.
title: Lyris Data Connector para Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

Descreve as eficiências de marketing obtidas por meio da integração.

A integração de e-mail Adobe® Data Connectors™ combina informações comportamentais do Adobe Analytics com marketing de e-mail do Lyris para redefinir a medição de sucesso e segmentar públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos do mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita entre campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois isso simplesmente está aproveitando os visitantes que seu site já está recebendo.

Esse aumento na eficiência do marketing é um dos principais benefícios da integração do Adobe Analytics com o Lyris. Além disso, essa integração sincronizará automaticamente as métricas de e-mail com os dados do Adobe Analytics com a frequência horária dos relatórios de ciclo fechado.

## Principais benefícios e recursos{#key-benefits-and-features}

Descreve os principais benefícios da integração dos Relatórios e análises de marketing da Lyris e da Adobe.

A integração do Lyris e do Adobe Analytics oferece os seguintes benefícios principais:

* Consolide dados de marketing e análise de email em uma interface de relatório
* Otimizar campanhas de email por conversão e contribuição para receita e sucesso do site
* Recomercializar para visitantes principais e segmentos de mercado com base em segmentos de marketing dinâmicos

### Segmentos dinâmicos de marketing

A integração de e-mail suporta segmentos dinâmicos de marketing para ajudá-lo a orientar sua empresa. Essa integração apresenta os seguintes segmentos de marketing, prontos para uso:

* **Perfil** de abandono do carrinho: Ajudar os visitantes a se converterem aos clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em preencher carrinhos
* **Perfis** de compra: Aumente os pedidos repetidos e o valor médio do pedido por meio de campanhas direcionadas pelos padrões de compra do visitante
* **Perfil** comportamental de exibição de produto/conteúdo: Alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e perfil de acesso ao conteúdo
* Os clientes também podem criar e agendar segmentos **de remarketing** personalizados específicos às necessidades dos usuários.

## Pré-requisitos de integração{#integration-prerequisites}

Descreve os pré-requisitos para uma integração bem-sucedida.

Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics e do software de email.

Isso garante que as práticas recomendadas e pré-requisitos apropriados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

### Pré-requisitos para o Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Conjunto de relatórios específico**: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração
* **Variáveis** disponíveis e configuradas do Analytics: Essa integração exige eventos personalizados e eVars personalizadas, além de eventos adicionais e eVars adicionais.

* **Representante** autorizado: Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.
* **Data warehouse** do Adobe Analytics: Essa integração exige que o data warehouse do Adobe Analytics seja habilitado para gerar segmentos de recomercialização. Se você não tiver ativado o data warehouse, entre em contato com a Adobe para obter detalhes.
* **ID** do destinatário: A integração exige que capturemos e armazenemos uma "ID de visitante" em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema Lyris. Essa "ID do destinatário" está associada ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é devolvida ao sistema Lyris e que pode ser potenciado para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Rastreamento** externo: Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Lyris abaixo para mais informações
* **Conformidade** com privacidade: Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade, exigindo a implementação de procedimentos apropriados por sua organização, como informar e dar consentimento aos visitantes do site.

### Pré-requisitos para o Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Conta** Lyris válida: Para usar essa integração do Conector de dados, é necessário ter uma conta Lyris válida.
* **Informações** da conta: Você precisará das seguintes informações sobre sua conta Lyris durante essa configuração de integração:

   * *Chave* da API Lyris: Usado para preenchimento de dados
   * *Parâmetros* da string de consulta: Eles são anexados no URL da página inicial para ID da mensagem e ID do destinatário (ID do visitante).
   * *Servidor Lyris/URL*: O valor do servidor usado no sistema Lyris
   * *ID* do site da Lyris: Também conhecido como "ID do cliente", esse é o valor exclusivo para sua instância do Lyris HQ. Isso pode ser localizado em "Informações do cliente", na seção "Página inicial da conta" do EmailLabs.

## Configurar variáveis do Adobe Analytics para o Lyris{#configure-adobe-analytics-variables-for-lyris}

Descreve as eVars e Eventos a serem reservados para cada implementação do conjunto de relatórios.

Essa integração exige que pelo menos duas eVars sejam reservadas para cada implementação do conjunto de relatórios. Além dessas eVars, alguns eventos podem ser reservados, dependendo dos dados do Lyris que você gostaria de ver no Analytics. Essas eVars e eventos são descritos na tabela abaixo:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variável </th> 
   <th colname="col2" class="entry"> Nome da variável </th> 
   <th colname="col3" class="entry"> Como a variável é usada </th> 
   <th colname="col4" class="entry"> Configurações </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID da mensagem </td> 
   <td colname="col3"> Para capturar a identificação individual da campanha de mensagem de email </td> 
   <td colname="col4"> <p>Status: Ativado </p> <p>Alocação: Mais recente </p> <p>Expirar após: "Decisão da empresa" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Para capturar a identificação anônima do cliente que clicou na campanha de email </td> 
   <td colname="col4"> <p>Status: Ativado </p> <p>Alocação: Mais recente </p> <p>Expirar após: "Decisão da empresa" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails enviados </td> 
   <td colname="col3"> Não armazenar. de emails enviados de Lyris </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails abertos </td> 
   <td colname="col3"> Não armazenar. de emails que foram abertos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails únicos abertos </td> 
   <td colname="col3"> Não armazenar. de emails exclusivos que foram abertos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Click-throughs por email </td> 
   <td colname="col3"> Não armazenar. de vezes que qualquer email foi clicado </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Rejeições de e-mail </td> 
   <td colname="col3"> Para guardar o não. de e-mails enviados </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Cancelamento de inscrição por email </td> 
   <td colname="col3"> Para guardar o não. de assinaturas de e-mail desativadas </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
 </tbody> 
</table>
