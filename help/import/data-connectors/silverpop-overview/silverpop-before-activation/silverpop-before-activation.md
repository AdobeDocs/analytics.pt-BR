---
description: Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.
seo-description: Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.
seo-title: Antes de ativar esta integração
title: Antes de ativar esta integração
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Antes de ativar esta integração{#before-you-activate-this-integration}

Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.

Isso garantirá que as práticas recomendadas ou pré-requisitos apropriados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

## Adobe Analytics{#adobe-analytics}

Examine as seguintes informações sobre a integração dos Conectores de dados, conforme ela se relaciona ao Adobe Analytics:

* **** Conjunto de relatórios específico: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **** Variáveis disponíveis e configuradas do Analytics: Essa integração exige 5 eventos personalizados e 2 eVars personalizadas, além de 3 eventos adicionais e 3 eVars adicionais. Consulte Variáveis [de integração do](../../silverpop-overview/silverpop-variables.md#concept-6c8a359719fd4794a42f5f6fb118f8b2)Analytics.

* **** Representante autorizado: Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.
* **** Data Warehouse™: Essa integração exige que o Data Warehouse seja habilitado para gerar segmentos de recomercialização. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **** ID do destinatário: A integração exige que capturemos e armazenemos uma "ID de visitante" em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema Silverpop. Essa "ID do destinatário" está associada ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é puxada para o sistema Silverpop e pode ser aproveitada para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Rastreamento externo: Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Silverpop abaixo para obter detalhes.
* **** Conformidade com privacidade: Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por sua organização, como informar e dar o consentimento aos visitantes do site.

## Integração do Silverpop Data Connector{#silverpop-data-connector-integration}

Revise as seguintes informações sobre a integração do Conector de dados conforme ela se relaciona ao Silverpop:

* **** Conta Silverpop válida: Para usar a integração de email dos Conectores de dados, um cliente deve ter uma conta Silverpop ativa com email ativado e credenciais ativas do usuário.
* **Entre Em Contato Com Seu Representante** Silverpop. Essa integração não é ativada automaticamente pelo Silverpop. Você deve entrar em contato com seu representante Silverpop para iniciar a configuração do Silverpop antes que os dados sejam importados ou exportados do Analytics.

> [!NOTE] Essa integração funciona somente com organizações Envolvimento (não Transact).

## Preços{#pricing}

Essa integração dos Conectores de dados inclui considerações sobre preços que você precisa considerar antes da ativação.

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Pode haver taxas recorrentes e de implementação associadas a essa integração. Entre em contato com seu representante de conta da Adobe para obter detalhes sobre preços.

### Considerações sobre preços do parceiro {#section-c6afad08c34b43e3a7a3637eea3328c3}

Pode haver taxas associadas a essa integração. Entre em contato com seu gerente de relacionamento para obter informações sobre preços.