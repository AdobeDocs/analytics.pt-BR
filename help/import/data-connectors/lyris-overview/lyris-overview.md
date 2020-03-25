---
description: Descreve as eficiências de marketing obtidas por meio da integração.
title: Conector de dados do Lyris para Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conector de dados do Lyris para Adobe Analytics {#lyris-data-connector-for-adobe-analytics}

Descreve as eficiências de marketing obtidas por meio da integração.

A integração de e-mail Adobe® Data Connectors™ combina informações comportamentais do Adobe Analytics com marketing de e-mail do Lyris para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos de mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita em campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois a questão é basicamente aproveitar os visitantes que seu site já está recebendo.

Esse aumento na eficiência do marketing é um dos principais benefícios da integração do Adobe Analytics com o Lyris. Além disso, essa integração sincronizará automaticamente as métricas de email com dados do Adobe Analytics com a mesma frequência horária de relatórios de ciclo fechado.

## Principais benefícios e recursos {#key-benefits-and-features}

Descreve os principais benefícios da integração do Lyris com o Adobe Marketing Reports and Analytics.

A integração do Lyris e do Adobe Analytics oferece os seguintes benefícios principais:

* Consolidar dados de marketing por email e de análise em uma interface de relatório.
* Otimizar campanhas por email por conversão e contribuição com a receita e o sucesso do site.
* Remarketing para visitantes principais e segmentos de mercado com base em segmentos de marketing dinâmico.

### Segmentos de marketing dinâmicos

A integração de email oferece suporte a segmentos de marketing dinâmicos para ajudar você a orientar sua empresa. Essa integração apresenta os seguintes segmentos de marketing, prontos para uso:

* **Perfil de abandono do carrinho**: ajude a conversão de visitantes em clientes usando campanhas ajustadas especificamente projetadas para quem está hesitante em concluir a compra em carrinhos
* **Perfis de compra**: aumente os pedidos repetidos e o valor médio de pedido por meio de campanhas direcionadas pelos padrões de compra do visitante
* **Perfil comportamental de exibição de produto/conteúdo**: alcance clientes em potencial por meio de segmentos de marketing baseados em exibições de produtos e criação de perfis de acesso ao conteúdo
* Os clientes também podem criar e agendar **segmentos de remarketing personalizados** específicos às necessidades dos usuários.

## Pré-requisitos de integração {#integration-prerequisites}

Descreve os pré-requisitos para uma integração bem-sucedida.

Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics e do seu software de email.

Isso garante que as práticas recomendadas ou os pré-requisitos adequados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

### Pré-requisitos para o Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Específico do Conjunto de relatórios**: observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração
* **Variáveis disponíveis e configuradas do Analytics**: essa integração exige o uso de eventos e eVars personalizadas, bem como de eventos e eVars adicionais.

* **Representante autorizado**: esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.
* **Adobe Analytics data warehouse**: essa integração exige que o data warehouse do Adobe Analytics esteja habilitado para gerar segmentos de remarketing. Se você não tiver ativado o data warehouse, entre em contato com a Adobe para obter detalhes.
* **Recipient ID (ID de destinatário):** a integração exige a captura e o armazenamento de um “ID de visitante” em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de &quot;ID de destinatário&quot;) é uma representação codificada ou numérica de um endereço de email do sistema Lyris. Essa &quot;ID de destinatário&quot; está associada ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é devolvido ao sistema Lyris e pode ser aproveitado para fins de remarketing. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Rastreamento externo**: se, atualmente, você não estiver seguindo a prática recomendada de ativação do rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Lyris abaixo para obter detalhes
* **Conformidade com privacidade**: você deve entender que, ao ativar o rastreamento de ID de destinatário ou de visitante, esse recurso pode rastrear informações de identificação pessoal de visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte de sua organização, como informar os visitantes do site e conseguir o consentimento deles.

### Pré-requisitos para o Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Conta Lyris válida**: para usar essa integração do Conector de dados, é necessário ter uma conta Lyris válida.
* **Informações da conta**: você precisará das seguintes informações sobre sua conta Lyris durante essa configuração de integração:

   * *Chave da API Lyris*: usada no preenchimento de dados
   * *Parâmetros da string de consulta*: eles são anexados ao URL da página inicial para transmitir a ID da mensagem e a ID do destinatário (ID do visitante).
   * *Servidor Lyris/URL*: o valor do servidor usado no sistema Lyris
   * *ID do site da Lyris*: Também conhecido como &quot;ID do cliente&quot;, esse é o valor exclusivo para sua instância do Lyris HQ. Pode ser localizado em &quot;Informações do cliente&quot;, na seção &quot;Página inicial da conta&quot; do EmailLabs.

## Configurar variáveis do Adobe Analytics para o Lyris {#configure-adobe-analytics-variables-for-lyris}

Descreve as eVars e Eventos a serem reservados para cada implementação do conjunto de relatórios.

Essa integração exige que pelo menos duas eVars sejam reservadas para cada implementação do conjunto de relatórios. Além dessas eVars, alguns eventos podem ser reservados, a depender de quais dados do Lyris você gostaria de ver no Analytics. Essas eVars e eventos são descritos na tabela abaixo:

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
   <td colname="col2"> ID de mensagem </td> 
   <td colname="col3"> Para capturar a identificação individual da campanha de mensagem de email </td> 
   <td colname="col4"> <p>Status: Ativado </p> <p>Alocação: Mais recente </p> <p>Expirar após: “Decisão da empresa” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de destinatário de email </td> 
   <td colname="col3"> Para capturar a identificação anônima do cliente que clicou na campanha de email </td> 
   <td colname="col4"> <p>Status: Ativado </p> <p>Alocação: Mais recente </p> <p>Expirar após: “Decisão da empresa” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails enviados </td> 
   <td colname="col3"> Para armazenar o nº de emails enviados via Lyris </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails abertos </td> 
   <td colname="col3"> Para armazenar o nº de emails que foram abertos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails exclusivos abertos </td> 
   <td colname="col3"> Para armazenar o nº de emails exclusivos que foram abertos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Click-throughs por email </td> 
   <td colname="col3"> Para armazenar o nº de vezes que clicaram em qualquer email </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Rejeições de email </td> 
   <td colname="col3"> Para guardar o nº de emails enviados </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Cancelamento de inscrição por email </td> 
   <td colname="col3"> Para guardar o nº de inscrições por email desativadas </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
 </tbody> 
</table>
