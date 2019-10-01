---
description: Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® com o marketing de email da Delivra para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.
seo-description: Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® com o marketing de email da Delivra para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.
seo-title: Conector de dados para Adobe Analytics
title: Conector de dados para Adobe Analytics
uuid: 9d56d39c-98e6-4e9b-b00d-515df02ea879
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Delivra Data Connector for Adobe Analytics{#delivra-data-connector-for-adobe-analytics}

Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® com o marketing de email da Delivra para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos do mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita entre campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois isso simplesmente está aproveitando os visitantes que seu site já está recebendo. Esse aumento na eficiência do marketing é um dos principais benefícios da integração do Analytics com a Delivra. Além disso, essa integração sincronizará automaticamente as métricas de e-mail com os dados do Analytics com a frequência horária para relatórios de ciclo fechado.

## Principais benefícios{#key-benefits}

Essa integração inclui os seguintes benefícios principais:

* Consolide dados de marketing e análise de email em uma interface de relatório
* Optimize email campaigns by conversion and contribution to revenue and site success
* Re-market to key visitors and market segments based on dynamic marketing segments
* A sincronização de métricas de e-mail em tempo real está disponível, em vez de uma vez por dia padrão

## Dynamic Marketing Segments{#dynamic-marketing-segments}

This Data Connectors email integration supports dynamic marketing segments to help you drive your business.

This integration features the following marketing segments, out of the box:

* **** Purchase Profiles: Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns.
* **** Product/Content View Behavioral Profile: Reach prospective customers through marketing segments based on product views and content access profiling.
* **** Cart Abandonment Profile: Help visitors convert to customers through fine-tuned campaigns specifically designed for those who are hesitant to complete carts.
* Customers can also create and schedule custom remarketing segments specific to the needs of their users.

## Integration Procedure and Prerequisites{#integration-procedure-and-prerequisites}

Using a “plug and play” wizard, intuitive step-by-step processes will walk you through points of system synchronization and initialize the integration.

Essa integração dos Conectores de dados exige o seguinte:

### Pré-requisitos da Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Adobe Data Warehouse
* Conta do Adobe Analytics
* Variáveis disponíveis e configuradas do Analytics, incluindo eVars e eventos personalizados.

### Delivra Pré-requisitos: {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Uma conta ativa de nível profissional do Dell (ou superior) com a opção "Integração da Adobe" ativada.

## Preços{#pricing}

Essa integração dos Conectores de dados inclui considerações sobre preços que você precisa conhecer.

As seguintes seções contêm mais informações:

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Pode haver taxas recorrentes e de implementação associadas a essa integração. Please contact your Adobe Account Representative for pricing details.

### Considerações sobre Preços do Delivra {#section-c6afad08c34b43e3a7a3637eea3328c3}

Pode haver taxas associadas a essa integração.

* Entre em contato com seu representante de conta do Delivra para obter detalhes sobre preços.

## O Que Você Deve Saber Antes De Ativar Esta Integração{#what-you-should-know-before-activating-this-integration}

Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.

Isso garantirá que as práticas recomendadas ou pré-requisitos apropriados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

### Adobe Analytics{#adobe-analytics}

Examine as seguintes informações sobre a integração dos Conectores de dados, conforme ela se relaciona ao Adobe Analytics:

* **** Conjunto de relatórios específico: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **** Representante autorizado: Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.
* **** Data Warehouse™: Essa integração exige que o Data Warehouse seja habilitado para gerar segmentos de recomercialização. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **** ID do destinatário: A integração exige que capturemos e armazenemos uma "ID de visitante" em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema Delivra. Essa "ID do destinatário" está associada ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é puxada para o sistema Delivra e pode ser potenciada para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Rastreamento externo: Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Delivra abaixo para obter detalhes.
* **** Privacy Compliance: You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

### Delivra for Adobe Data Connectors Integration{#delivra-for-adobe-data-connectors-integration}

Review the following information about this Data Connectors integration as it relates to Delivra:

* **** Valid Delivra Account: In order to use the Data Connectors email integration, a client must have a valid Delivra account.
* **** Current Customer of Delivra: This integration requires you to be a customer of both Adobe and Delivra. Se você não for atualmente um cliente da Delivra, não terá as informações necessárias para concluir o assistente de integração. Se você for um cliente do Delivra, precisará da ID da conta do Delivra ou do nome da lista atribuído à sua organização para concluir o assistente de integração. Você precisará fornecer ao Delivra o Nome da empresa e a ID da conta associada à integração para concluir a configuração.