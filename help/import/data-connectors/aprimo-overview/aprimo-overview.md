---
description: Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Adobe Analytics® com marketing de email para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.
seo-description: Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Adobe Analytics® com marketing de email para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.
seo-title: Conector de dados aprimorado para Adobe Analytics
title: Conector de dados aprimorado para Adobe Analytics
uuid: 590ded4b-b250-43b4-9cec-68508b853e00
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Aprimo Data Connector for Adobe Analytics{#aprimo-data-connector-for-adobe-analytics}

Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Adobe Analytics® com marketing de email para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos do mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita entre campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois isso simplesmente está aproveitando os visitantes que seu site já está recebendo.

Esse aumento na eficiência de marketing é um dos principais benefícios da integração [!DNL Adobe Analytics] com o abril. Além disso, essa integração sincronizará automaticamente as métricas de e-mail com [!DNL Adobe Analytics] os dados com a mesma frequência horária para relatórios de ciclo fechado.

## Principais benefícios e recursos{#key-benefits-and-features}

Essa integração inclui os seguintes benefícios principais:

* Consolide os dados de marketing e análise de email em uma interface de relatório.
* Otimize campanhas de email por conversão e contribuição para a receita e o sucesso do site.
* Recomercialize para visitantes principais e segmentos de mercado com base em segmentos de marketing dinâmicos.

## Segmentos dinâmicos de marketing{#dynamic-marketing-segments}

Essa integração apresenta os seguintes segmentos de marketing dinâmicos:

* **** Perfis de compra: Aumente os pedidos repetidos e o valor médio do pedido por meio de campanhas direcionadas pelos padrões de compra do visitante.
* **** Perfil comportamental de exibição de produto/conteúdo: Alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo.
* **** Perfil de abandono do carrinho: Ajude os visitantes a converterem-se aos clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em preencher carrinhos.
* Os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades de seus usuários.

## Antes de ativar{#before-you-activate}

Antes de iniciar a integração dos Conectores de dados para , preencha os seguintes requisitos:

### Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** Conjunto de relatórios específico: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **** Variáveis disponíveis e configuradas do Adobe Analytics: Essa integração exige eventos personalizados e eVars personalizadas, além de eventos adicionais e eVars adicionais.
* **** Representante autorizado: Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.
* **** Data Warehouse™: Essa integração exige que o Data Warehouse seja habilitado para gerar segmentos de recomercialização. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **Parceiro~**: A integração exige que capturemos e armazenemos um " [!DNL ~parceiro~]" em uma variável do Adobe Analytics (eVar). Essa ID é uma representação codificada ou numérica de um endereço de email do sistema [!DNL ~Parceiro~] . Este " [!DNL ~Parceiro~]" está associado ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é extraída para o sistema [!DNL ~Partner~] e pode ser aproveitada para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Rastreamento externo: Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção [!DNL ~Parceiro~] abaixo para obter detalhes.
* **** Conformidade com privacidade: Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por sua organização, como informar e dar o consentimento aos visitantes do site.

## Preços{#pricing}

 Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável.

Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.

### Considerações sobre preços da Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Pode haver taxas recorrentes e de implementação associadas a essa integração, incluindo o custo para um número maior de chamadas de servidor incorridas por meio dessa integração. Entre em contato com seu representante de conta da Adobe para obter detalhes sobre preços.

### ~Considerações sobre preços do parceiro~{#section-f8ca71df32224412a5101efb6e356529}

Pode haver taxas recorrentes e de implementação associadas a essa integração. Entre em contato com o [!DNL ~parceiro~] para obter detalhes sobre preços.

## Variáveis do Adobe Analytics{#adobe-analytics-variables}

Essa integração requer variáveis do Adobe Analytics para rastrear métricas.

Depois de identificar o evento e as eVars a serem usadas com essa integração, elas devem ser ativadas no Admin Console do Adobe Analytics (consulte [Report Suites](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) para obter instruções).