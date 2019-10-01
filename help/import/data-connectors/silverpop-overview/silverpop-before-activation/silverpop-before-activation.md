---
description: Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.
seo-description: Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics® e do software de email.
seo-title: Before You Activate This Integration
title: Antes de ativar esta integração
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Antes de ativar esta integração{#before-you-activate-this-integration}

Before activating this integration, review the following items against your deployments of Adobe Analytics® and your email software.

Doing so will ensure the appropriate best practices or pre-requisites are in place prior to activation, which will result in an optimal and successful integration.

## Adobe Analytics{#adobe-analytics}

Review the following information about this Data Connectors integration as it relates to Adobe Analytics:

* **Report Suite Specific:** Be advised this integration is report-suite specific. Ensure that you have selected the desired report suite prior to activating the integration.
* **** Available and configured Analytics variables: This integration requires 5 custom events and 2 custom eVars, and optionally 3 additional events and 3 additional eVars. See Analytics Integration Variables.[](../../silverpop-overview/silverpop-variables.md#concept-6c8a359719fd4794a42f5f6fb118f8b2)

* **** Authorized Representative: Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable. By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.
* **** Data Warehouse™: This integration requires the Data Warehouse to be enabled in order to generate remarketing segments. If you have not enabled the Data Warehouse, contact Adobe for details.
* **** Recipient ID: The integration requires that we capture and store a "Visitor ID" within a Analytics variable (eVar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema Silverpop. This "Recipient ID" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the Silverpop system and can be leveraged for remarketing purposes. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Rastreamento externo: Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Silverpop abaixo para obter detalhes.
* **** Conformidade com privacidade: Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por sua organização, como informar e dar o consentimento aos visitantes do site.

## Integração do Silverpop Data Connector{#silverpop-data-connector-integration}

Revise as seguintes informações sobre a integração do Conector de dados conforme ela se relaciona ao Silverpop:

* **** Conta Silverpop válida: Para usar a integração de email dos Conectores de dados, um cliente deve ter uma conta Silverpop ativa com email ativado e credenciais ativas do usuário.
* **Entre Em Contato Com Seu Representante** Silverpop. Essa integração não é ativada automaticamente pelo Silverpop. Você deve entrar em contato com seu representante Silverpop para iniciar a configuração do Silverpop antes que os dados sejam importados ou exportados do Analytics.

>[!NOTE]
>
>Essa integração funciona somente com organizações Envolvimento (não Transact).

## Preços{#pricing}

Essa integração dos Conectores de dados inclui considerações sobre preços que você precisa considerar antes da ativação.

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Pode haver taxas recorrentes e de implementação associadas a essa integração. Entre em contato com seu representante de conta da Adobe para obter detalhes sobre preços.

### Considerações sobre preços do parceiro {#section-c6afad08c34b43e3a7a3637eea3328c3}

Pode haver taxas associadas a essa integração. Entre em contato com seu gerente de relacionamento para obter informações sobre preços.