---
description: Essa integração combina o poder do sistema de feedback integrado do software de marketing por email e os relatórios comportamentais do Adobe Analytics para criar análises poderosas e oportunidades de otimização para sua organização.
title: Conector de dados optivo® broadmail para Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conector de dados optivo® broadmail para Adobe Analytics {#optivo-broadmail-data-connector-for-adobe-analytics}

Essa integração combina o poder do sistema de feedback integrado do software de marketing por email e os relatórios comportamentais do Adobe Analytics para criar análises poderosas e oportunidades de otimização para sua organização.

O [!DNL ~Partner~] é um software profissional de marketing por email. Sua principal função é criar, enviar e avaliar campanhas por e-mail e informativos. O `[~Partner~]` está disponível como um cloud service (software como um serviço).

A integração do `[~Partner~]` oferece remarketing automatizado e sincronização de dados, resultando em mais conversões e receita. A integração permite que os profissionais de marketing sincronizem segmentos automaticamente para seus clientes com base na interação deles com o email e no comportamento deles no site. A troca automatizada de dados de segmentos personalizáveis ajuda a criar campanhas de email altamente direcionadas que impulsionam as vendas, como as campanhas de abandono de carrinhos de compras e de remarketing pós-compra para venda cruzada, venda de produto atualizado e revenda.

Essa integração também intercambia métricas de campanhas de email bem-sucedidas do `[~Partner~]` com o Adobe Analytics. Os dados cruciais são exibidos centralmente na visão geral de sua campanha de email.

## Programa laboratório de Data Connectors {#section-51f9864851b64d96873127b9ac9c9a2b}

Este programa é um método rápido para parceiros de plataformas de terceiros da Adobe criarem integrações e fornecê-las ao nosso mercado conjunto. As integrações são totalmente desenvolvidas pelos nossos parceiros e disponibilizadas na Adobe Experience Cloud, seguindo as metodologias da comunidade. Elas são disponibilizadas sem custos adicionais para os clientes do Adobe Analytics e de outras soluções e são fornecidas no estado em que se encontram, sem garantias implícitas da Adobe porque as integrações foram produzidas por terceiros.

Em caso de dúvidas relacionadas ao seu atual serviço, garantia ou licenciamento, entre em contato com seu Gerente de contas da Adobe.

## Principais benefícios e recursos {#key-benefits-and-features}

Essa integração inclui os seguintes benefícios principais:

* Recuperação de compradores que navegam e abandonam
* Aumento das vendas com venda cruzada direcionada e remarketing direcionado de venda de produtos atualizados
* Campanhas automáticas baseadas em segmentos
* Campanhas otimizadas em andamento
* Segmentos no [!DNL ~Partner~] para remarketing direcionado
* Atualizações constantes de métricas de campanha
* Acionadores de conversação automatizados

## Segmentos de marketing dinâmicos {#dynamic-marketing-segments}

Essa integração apresenta os seguintes segmentos de marketing dinâmicos:

* **Perfis de compra** aumente os pedidos repetidos e o valor médio de pedido por meio de campanhas direcionadas pelos padrões de compra do visitante.
* **Perfil comportamental de exibição de produto/conteúdo:** alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo.
* **Perfil de abandono do carrinho:** ajude os visitantes a converterem-se em clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em concluir os carrinhos.
* **Remarketing eficiente:** os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades dos usuários.

## Antes de ativar {#before-you-activate}

Antes de iniciar a integração dos Data Connectors para , atenda aos seguintes requisitos:

## Requisitos do Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Específico do Conjunto de relatórios:** observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **Variáveis disponíveis e configuradas do Adobe Analytics:** essa integração requer o uso de eventos personalizados e eVars personalizadas.

* **Representante autorizado:** esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.
* **ID de mensagem:** a integração exige que capturemos e armazenemos uma &quot;ID de mensagem&quot; em uma variável do Adobe Analytics (eVar). Essas IDs são necessárias para identificar as correspondências enviadas. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Partner:** a integração exige a captura e o armazenamento de um [!UICONTROL ~Partner~] em uma variável do Adobe Analytics (eVar). Essa ID é uma representação codificada ou numérica de um endereço de email do sistema [!UICONTROL ~Partner~]. Esse [!UICONTROL ~Partner~] está associado ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é extraído para o sistema [!UICONTROL ~Partner~] e pode ser aproveitado para fins de remarketing. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Tempo de clique da postagem:** como parte do processo de configuração, essa integração exige uma atribuição a uma eVar que corresponda ao tempo de uma ação pós-clique. Isso é necessário para transmitir informações sobre uma ação do destinatário ao [!UICONTROL ~Partner~] depois que o destinatário clicou em um link em um email.

* **Produto pós-clique:** como parte do processo de configuração, essa integração exige uma atribuição a uma eVar que corresponda ao produto oferecido associado a uma ação pós-clique. Isso é necessário para transmitir informações sobre uma ação do destinatário ao [!UICONTROL ~Partner~] depois que o destinatário clicou em um link em um email.

* **Tipo de ação pós-clique:** como parte do processo de configuração, essa integração exige uma atribuição a uma eVar que corresponda ao tipo de ação pós-clique. Isso é necessário para transmitir informações sobre uma ação do destinatário ao [!UICONTROL ~Partner~] depois que o destinatário clicou em um link em um email.

* **Conformidade com privacidade:** você deve entender que, ao ativar o rastreamento de ID de destinatário ou de visitante, esse recurso pode rastrear informações de identificação pessoal de visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte da sua organização, como informar os visitantes do site e dar o consentimento deles.

## Preços {#pricing}

Esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável.

Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.

### Considerações sobre preços da Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Os clientes atuais da solução Adobe Analytics não têm custo adicional associado ao uso da integração dos Data Connectors. Os clientes que ainda não migraram para o novo Adobe Analytics devem entrar em contato com o representante de conta da Adobe para obter mais detalhes.

### Considerações sobre preços de parceiros {#section-f8ca71df32224412a5101efb6e356529}

Essa integração está disponível para clientes do [!DNL ~Partner~], no entanto, tarifas adicionais de integração serão aplicadas. Entre em contato com sales@optivo.com para obter detalhes sobre preços. Entre em contato com o [!DNL ~parceiro~] para obter detalhes sobre preços.

## Variáveis do Adobe Analytics {#adobe-analytics-variables}

Essa integração requer variáveis do Adobe Analytics para rastrear métricas.

Após identificar o evento e as eVars a serem usadas na integração, eles devem ser ativados no Admin Console do Analytics (consulte [Conjuntos de relatórios](https://docs.adobe.com/content/help/pt-BR/analytics/admin/manage-report-suites/report-suites-admin.html) para obter instruções).
