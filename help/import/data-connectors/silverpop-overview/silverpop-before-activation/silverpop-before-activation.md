---
description: Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics® e do seu software de email.
title: Antes de ativar essa integração
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Antes de ativar essa integração {#before-you-activate-this-integration}

Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics® e do seu software de email.

Isso garantirá que as práticas recomendadas ou os pré-requisitos adequados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

## Adobe Analytics {#adobe-analytics}

Analise as seguintes informações sobre a integração dos Data Connectors e de como ela se relaciona com o Adobe Analytics:

* **Específico do Conjunto de relatórios:** observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **Variáveis disponíveis e configuradas do Analytics:** essa integração exige o uso de cinco eventos e duas eVars personalizadas, bem como de três eventos e três eVars adicionais. Consulte [Variáveis de integração do Analytics](/help/import/data-connectors/silverpop-overview/silverpop-variables.md).

* **Representante autorizado:** esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.
* **Data Warehouse™:** essa integração exige que o Data Warehouse esteja habilitado para gerar segmentos de remarketing. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **ID de destinatário:** a integração exige a captura e o armazenamento de um “ID de visitante” em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de &quot;ID de destinatário&quot;) é uma representação codificada ou numérica de um endereço de email do sistema Silverpop. Essa &quot;ID de destinatário&quot; está associada ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é extraído para o sistema Silverpop e pode ser aproveitado para fins de remarketing. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Rastreamento externo:** se, atualmente, você não estiver seguindo a prática recomendada de ativação do rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Silverpop abaixo para obter detalhes.
* **Conformidade com privacidade:** você deve entender que, ao ativar o rastreamento de ID de destinatário ou de visitante, esse recurso pode rastrear informações de identificação pessoal de visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte da sua organização, como informar os visitantes do site e dar o consentimento deles.

## Integração do Conector de dados do Silverpop {#silverpop-data-connector-integration}

Analise as seguintes informações sobre a integração do Conector de dados e de como ela se relaciona com o Silverpop:

* **Conta Silverpop válida**: para usar a integração de email dos Data Connectors, um cliente deve ter uma conta do Silverpop ativa com email ativado e credenciais de usuário ativas.
* **Entre em contato com seu representante Silverpop**. Essa integração não é ativada automaticamente pelo Silverpop. Você deve entrar em contato com seu representante do Silverpop para iniciar a configuração do Silverpop antes que os dados sejam importados ou exportados do Analytics.

> [!NOTE] Essa integração funciona somente com empresas Engage (não Transact).

## Preços {#pricing}

Essa integração dos Data Connectors inclui considerações sobre preços das quais você considerar antes da ativação.

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Pode haver tarifas recorrentes e de implementação associadas a essa integração. Entre em contato com o representante de conta da Adobe para obter mais informações sobre preços.

### Considerações sobre preços de parceiros {#section-c6afad08c34b43e3a7a3637eea3328c3}

Pode haver tarifas associadas a essa integração. Por favor, entre em contato com seu gerente de relacionamento para obter informações sobre preços.
