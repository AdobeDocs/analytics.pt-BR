---
description: Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® ao marketing de email do Delivra para criar uma ferramenta avançada de forma a redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.
title: Conector de dados do Delivra para Adobe Analytics
uuid: 9d56d39c-98e6-4e9b-b00d-515df02ea879
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Conector de dados do Delivra para Adobe Analytics {#delivra-data-connector-for-adobe-analytics}

Esta integração de email Adobe® Data Connectors™ combina informações comportamentais do Analytics® ao marketing de email do Delivra para criar uma ferramenta avançada de forma a redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos de mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita em campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois a questão é basicamente aproveitar os visitantes que seu site já está recebendo. Esse aumento na eficiência de marketing é um dos principais benefícios da integração do Analytics com o Delivra. Além disso, essa integração sincronizará automaticamente as métricas de email com dados do Adobe Analytics com a mesma frequência horária de relatórios de ciclo fechado.

## Principais benefícios {#key-benefits}

Essa integração inclui os seguintes benefícios principais:

* Consolidar dados de marketing por email e de análise em uma interface de relatório.
* Otimizar campanhas por email por conversão e contribuição com a receita e o sucesso do site.
* Remarketing para visitantes principais e segmentos de mercado com base em segmentos de marketing dinâmico.
* A sincronização de métricas de email em tempo real está disponível, em vez do padrão de uma vez por dia

## Segmentos de marketing dinâmicos {#dynamic-marketing-segments}

Essa integração de email do Data Connectors oferece suporte a segmentos de marketing dinâmico para ajudar você a orientar sua empresa.

Essa integração apresenta os seguintes segmentos de marketing, prontos para uso:

* **Perfis de compra:** aumente os pedidos repetidos e o valor médio de pedido por meio de campanhas direcionadas pelos padrões de compra do visitante.
* **Perfil comportamental de exibição de produto/conteúdo:** alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo.
* **Perfil de abandono do carrinho:** ajude os visitantes a converterem-se em clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em concluir os carrinhos.
* Os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades dos usuários.

## Procedimento de integração e pré-requisitos {#integration-procedure-and-prerequisites}

Usando um assistente &quot;plug and play&quot;, os processos intuitivos passo a passo guiarão você pelos pontos de sincronização do sistema e darão início à integração.

Essa integração do Data Connectors exige o seguinte:

### Pré-requisitos da Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Adobe Data Warehouse
* Conta do Adobe Analytics.
* Variáveis disponíveis e configuradas do Analytics, incluindo eVars e eventos personalizados.

### Pré-requisitos do Delivra {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Uma conta ativa de nível profissional (ou superior) do Dell com a opção &quot;Integração da Adobe&quot; ativada.

## Preços {#pricing}

Essa integração do Data Connectors inclui considerações sobre preços que você precisa saber.

As seguintes seções contêm mais informações:

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Pode haver tarifas recorrentes e de implementação associadas a essa integração. Entre em contato com o representante de conta da Adobe para obter mais informações sobre preços.

### Considerações sobre preços do Delivra {#section-c6afad08c34b43e3a7a3637eea3328c3}

Pode haver tarifas associadas a essa integração.

* Entre em contato com o representante de conta do Delivra para obter detalhes sobre preços.

## O que você deve saber antes de ativar essa integração {#what-you-should-know-before-activating-this-integration}

Antes de ativar essa integração, analise os itens a seguir comparando com as implantações do Adobe Analytics® e do seu software de email.

Isso garantirá que as práticas recomendadas ou os pré-requisitos adequados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida.

### Adobe Analytics {#adobe-analytics}

Consulte as seguintes informações sobre a integração de Data Connectors, pois ela se relaciona ao Adobe Analytics:

* **Específico do Conjunto de relatórios:** observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **Representante autorizado:** esteja ciente de que ativar essa integração pode gerar tarifas para sua empresa de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da empresa; e, como tal, a empresa concorda em pagar as tarifas, se houver, estabelecidas no contrato de serviço descrito acima.
* **Data Warehouse™:** essa integração exige que o Data Warehouse esteja habilitado para gerar segmentos de remarketing. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **ID do destinatário:** a integração exige a captura e o armazenamento de um “ID de visitante” em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de &quot;ID do destinatário&quot;) é uma representação codificada ou numérica de um endereço de email do sistema Delivra. Essa &quot;ID de destinatário&quot; está associada ao comportamento downstream de visitantes no site (abandonos de carrinho, compras etc.) que é extraída para o sistema Delivra e pode ser aproveitada para fins de remarketing. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **Rastreamento externo:** se, atualmente, você não estiver seguindo a prática recomendada de ativação do rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Delivra abaixo para obter detalhes.
* **Conformidade com privacidade:** você deve entender que, ao ativar o rastreamento de ID de destinatário ou de visitante, esse recurso pode rastrear informações de identificação pessoal de visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por parte da sua organização, como informar os visitantes do site e dar o consentimento deles.

### Integração do Delivra para Adobe Data Connectors {#delivra-for-adobe-data-connectors-integration}

Consulte as seguintes informações sobre a integração do Data Connectors, pois ela se relaciona ao Delivra:

* **Conta válida do Delivra:** para usar a integração de email do Data Connectors, um cliente deve ter uma conta válida do Datran.
* **Cliente atual do Delivra:** essa integração exige que você seja um cliente da Adobe e do Datran. Se você não for um cliente do Delivra, não terá as informações necessárias para concluir o assistente de integração. Se for um cliente do Delivra, precisará da ID da conta do Delivra ou do nome da lista atribuído à organização para concluir o assistente de integração. Será necessário fornecer ao Delivra o Nome da empresa e a ID da conta associada à integração para concluir a configuração.
