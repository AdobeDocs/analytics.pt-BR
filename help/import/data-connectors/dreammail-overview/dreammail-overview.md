---
description: Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® com marketing por email para criar uma poderosa ferramenta que redefine a medição de sucesso e direciona públicos-alvo com mensagens mais relevantes.
title: Conector de dados do DreamMail para Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conector de dados do DreamMail para Adobe Analytics {#dreammail-data-connector-for-adobe-analytics}

Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® com marketing por email para criar uma poderosa ferramenta que redefine a medição de sucesso e direciona públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos de mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita em campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois a questão é basicamente aproveitar os visitantes que seu site já está recebendo.

Esse aumento na eficiência do marketing é um dos principais benefícios da integração do [!DNL Analytics] com o [!DNL ~Partner~]. Além disso, essa integração sincronizará automaticamente as métricas de email com dados do [!DNL Analytics] com a mesma frequência horária de relatórios de ciclo fechado.

## Principais benefícios e recursos {#key-benefits-and-features}

Essa integração inclui os seguintes benefícios principais:

* Consolidar dados de marketing por email e de análise em uma interface de relatório.
* Otimizar campanhas de email por conversão e por contribuição para a receita e o sucesso do site.
* Remarketing para visitantes e segmentos de mercado importantes com base em segmentos de marketing dinâmicos.

## Segmentos de marketing dinâmicos {#dynamic-marketing-segments}

Essa integração apresenta os seguintes segmentos de marketing dinâmicos:

* **Perfis de compra:** aumente os pedidos repetidos e o valor médio de pedido por meio de campanhas direcionadas pelos padrões de compra do visitante.
* **Perfil comportamental de exibição de produto/conteúdo:** alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo.
* **Perfil de abandono do carrinho:** ajude os visitantes a converterem-se em clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em concluir os carrinhos.
* Os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades dos usuários.

## Antes de ativar {#before-you-activate}

Antes de iniciar a integração dos Data Connectors para , atenda aos seguintes requisitos:

## Requisitos do Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Específico do Conjunto de relatórios:** observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **Variáveis disponíveis e configuradas do Analytics:** essa integração exige o uso de eventos e eVars personalizadas, bem como de eventos e eVars adicionais.

* **Representante autorizado:** esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.
* **Data Warehouse™:** essa integração exige que o Data Warehouse esteja habilitado para gerar segmentos de remarketing. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **[!DNL ~Partner~]:** a integração exige a captura e o armazenamento de um endereço de email em uma variável do Analytics (eVar). O &quot;[!DNL ~Partner~]&quot; está associado ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é extraído para o sistema[!DNL ~Partner~]e pode ser aproveitado para fins de remarketing. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Rastreamento externo:** se, atualmente, você não estiver seguindo a prática recomendada de ativação do rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção [!DNL ~Parceiro~] abaixo para obter detalhes.
* **Conformidade com privacidade:** você deve entender que, ao ativar o rastreamento de ID de destinatário ou de visitante, esse recurso pode rastrear informações de identificação pessoal de visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte da sua organização, como informar os visitantes do site e dar o consentimento deles.

## Preços {#pricing}

Esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável.

Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.

### Considerações sobre preços da Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Pode haver tarifas recorrentes e de implementação associadas à integração, incluindo o custo por um número maior de chamadas de servidor resultantes dessa integração. Entre em contato com o representante de conta da Adobe para obter mais informações sobre preços.

### Considerações sobre preços de ~parceiros~ {#section-f8ca71df32224412a5101efb6e356529}

Pode haver tarifas recorrentes e de implementação associadas a essa integração. Entre em contato com [!DNL DreamMail] para obter detalhes sobre preços.

## Variáveis de integração do Analytics {#analytics-integration-variables}

Essa integração requer variáveis do Analytics para rastrear métricas.

Após identificar o evento e as eVars a serem usadas na integração, eles devem ser ativados no Admin Console do Analytics (consulte [Conjuntos de relatórios](https://docs.adobe.com/content/help/pt-BR/analytics/admin/manage-report-suites/report-suites-admin.html) para obter instruções).
