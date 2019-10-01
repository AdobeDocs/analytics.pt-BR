---
description: Essa integração combina o poder do sistema de feedback integrado do software de marketing por email e os relatórios comportamentais do Adobe Analytics para criar oportunidades poderosas de análise e otimização para sua organização.
seo-description: Essa integração combina o poder do sistema de feedback integrado do software de marketing por email e os relatórios comportamentais do Adobe Analytics para criar oportunidades poderosas de análise e otimização para sua organização.
seo-title: optivo® Broadmail Data Connector para Adobe Analytics
title: optivo® Broadmail Data Connector para Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# optivo® Broadmail Data Connector para Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

Essa integração combina o poder do sistema de feedback integrado do software de marketing por email e os relatórios comportamentais do Adobe Analytics para criar oportunidades poderosas de análise e otimização para sua organização.

[!DNL ~O parceiro~] é um software profissional de marketing por email. Sua principal função é criar, enviar e avaliar campanhas por e-mail e boletins informativos. `[~Partner~]` está disponível como um serviço em nuvem (software como um serviço).

A `[~Partner~]` integração oferece remarketing automatizado e sincronização de dados, resultando em mais conversões e receita. A integração permite que os profissionais de marketing sincronizem segmentos automaticamente para seus clientes, com base em sua interação de email e comportamento do site. A troca automatizada de dados de segmentos personalizáveis ajuda a criar campanhas de email altamente direcionadas que impulsionam as vendas, como abandono de carrinhos de compras e remarketing pós-compra para produtos cruzados, atualizados e revendidos.

Essa integração também troca métricas de campanhas de email de sucesso do Adobe Analytics `[~Partner~]` para o Adobe Analytics. Os dados cruciais são exibidos centralmente na visão geral de sua campanha por email.

## Programa Laboratório de Conectores de Dados {#section-51f9864851b64d96873127b9ac9c9a2b}

Este programa é um método rápido para parceiros de plataformas de terceiros da Adobe criarem integrações e fornecê-las ao nosso mercado conjunto. As integrações são totalmente desenvolvidas pelos nossos parceiros e disponibilizadas na Adobe Experience Cloud, seguindo as metodologias da comunidade. Eles são disponibilizados sem custos adicionais para os clientes Adobe do Adobe Analytics e de outras soluções e são fornecidos no estado em que se encontram, sem garantias implícitas da Adobe devido à natureza de terceiros das integrações.

Em caso de dúvidas relacionadas ao serviço, garantia ou licenciamento atual, entre em contato com seu Gerente de contas da Adobe.

## Principais benefícios e recursos{#key-benefits-and-features}

Essa integração inclui os seguintes benefícios principais:

* Recuperar compradores que navegam e abandonam
* Aumente as vendas com venda cruzada e remarketing de venda agregada direcionados
* Campanhas automáticas baseadas em segmentos
* Campanhas otimizadas em andamento
* Segmentos no [!DNL ~parceiro~] para recomercialização direcionada
* Atualizações constantes de métricas de campanha
* Acionadores de conversação automatizados

## Segmentos dinâmicos de marketing{#dynamic-marketing-segments}

Essa integração apresenta os seguintes segmentos de marketing dinâmicos:

* **** Perfis de compra: Aumente os pedidos repetidos e o valor médio do pedido por meio de campanhas direcionadas pelos padrões de compra do visitante.
* **** Perfil comportamental de exibição de produto/conteúdo: Alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo.
* **** Perfil de abandono do carrinho: Ajude os visitantes a converterem-se aos clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em preencher carrinhos.
* **** Recomercialização Efetiva:Os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades de seus usuários.

## Antes de ativar{#before-you-activate}

Antes de iniciar a integração dos Conectores de dados para , preencha os seguintes requisitos:

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** Conjunto de relatórios específico: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **** Variáveis disponíveis e configuradas do Adobe Analytics: Essa integração exige eventos personalizados e eVars personalizadas.

* **** Representante autorizado: Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.
* **** ID da mensagem: A integração exige que capturemos e armazenemos uma "ID da mensagem" em uma variável do Adobe Analytics (eVar). Essas IDs são necessárias para identificar as correspondências enviadas. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Parceiro: A integração exige que capturemos e armazenemos um [!UICONTROL ~parceiro~] em uma variável do Adobe Analytics (eVar). Essa ID é uma representação codificada ou numérica de um endereço de email do sistema [!UICONTROL ~Parceiro~] . Este [!UICONTROL ~Parceiro~] está associado ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é extraída para o sistema [!UICONTROL ~Partner~] e pode ser aproveitada para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Tempo de clique da postagem: Como parte do processo de configuração, essa integração exige uma atribuição a uma eVar que corresponda ao tempo de uma ação de clique posterior. Isso é necessário para transmitir informações sobre uma ação do destinatário ao [!UICONTROL ~Parceiro~] depois que o destinatário clicou em um link em uma correspondência.

* **** Produto de pós-clique: Como parte do processo de configuração, essa integração exige uma atribuição a uma eVar que corresponda ao produto oferecido associado a uma ação de pós-clique. Isso é necessário para transmitir informações sobre uma ação do destinatário ao [!UICONTROL ~Parceiro~] depois que o destinatário clicou em um link em uma correspondência.

* **** Tipo de ação de cliques da postagem: Como parte do processo de configuração, essa integração exige uma atribuição a uma eVar que corresponda ao tipo de ação de pós-clique. Isso é necessário para transmitir informações sobre uma ação do destinatário ao [!UICONTROL ~Parceiro~] depois que o destinatário clicou em um link em uma correspondência.

* **** Conformidade com privacidade: Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por sua organização, como informar e dar o consentimento aos visitantes do site.

## Preços{#pricing}

 Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável.

Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.

### Considerações sobre preços da Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Os clientes atuais da solução Adobe Analytics não têm custo adicional associado ao uso desta integração dos Conectores de dados. Os clientes que ainda não mudaram para o novo produto Adobe Analytics devem entrar em contato com o representante de conta da Adobe para obter mais detalhes.

### Considerações sobre preços do parceiro {#section-f8ca71df32224412a5101efb6e356529}

Essa integração está disponível para clientes [!DNL ~Parceiros~] , no entanto, taxas adicionais de integração serão aplicadas. Entre em contato com sales@optivo.com para obter detalhes sobre preços. Entre em contato com o [!DNL ~parceiro~] para obter detalhes sobre preços.

## Variáveis do Adobe Analytics{#adobe-analytics-variables}

Essa integração requer variáveis do Adobe Analytics para rastrear métricas.

Após identificar o evento e as eVars a serem usadas com essa integração, elas devem ser ativadas no Admin Console do Analytics (consulte Conjuntos [de](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) relatórios para obter instruções).