---
description: Esta integração de email do Adobe® Data Connectors™ combina informações comportamentais do Analytics® com marketing de email emarsys para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.
title: Conector de dados Emarsys para Adobe Analytics
uuid: 6f2fbabc-dc6c-4975-887d-ec22eba42f9e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Emarsys Data Connector for Adobe Analytics{#emarsys-data-connector-for-adobe-analytics}

Esta integração de email do Adobe® Data Connectors™ combina informações comportamentais do Analytics® com marketing de email emarsys para criar uma ferramenta poderosa para redefinir a medição de sucesso e direcionar públicos-alvo com mensagens mais relevantes.

A entrega de mensagens de email relevantes para esses segmentos do mercado pode resultar em oportunidades de receita totalmente novas, aumentando a conversão e a receita entre campanhas de email novas e existentes. Por exemplo, a entrega de mensagens de email relevantes com base em produtos que foram visualizados durante uma visita ou em produtos que foram deixados em um carrinho de compras abandonado comprovou ter um impacto dramático na receita, com impacto mínimo no custo, pois isso simplesmente está aproveitando os visitantes que seu site já está recebendo.

Esse aumento na eficiência do marketing é um dos principais benefícios da integração [!DNL Analytics] com o emarsys. Além disso, essa integração sincronizará automaticamente as métricas de e-mail com [!DNL Analytics] os dados com a mesma frequência horária para relatórios de ciclo fechado.

## Principais benefícios{#key-benefits}

Principais benefícios desta integração.

* Consolide dados de marketing e análise de email em uma interface de relatório
* Otimizar campanhas de email por conversão e contribuição para receita e sucesso do site
* Recomercializar para visitantes principais e segmentos de mercado com base em segmentos de marketing dinâmicos

## Segmentos dinâmicos de marketing{#dynamic-marketing-segments}

Essa integração de email dos Conectores de dados oferece suporte a segmentos dinâmicos de marketing para ajudá-lo a orientar sua empresa.

Essa integração apresenta os seguintes segmentos de marketing, prontos para uso:

* **** Perfis de compra: Aumente os pedidos repetidos e o valor médio do pedido por meio de campanhas direcionadas pelos padrões de compra do visitante.
* **** Perfil comportamental de exibição de produto/conteúdo: Alcance clientes em potencial por meio de segmentos de marketing com base em exibições de produtos e criação de perfis de acesso ao conteúdo.
* **** Perfil de abandono do carrinho: Ajude os visitantes a converterem-se aos clientes por meio de campanhas ajustadas especificamente projetadas para aqueles que estão hesitantes em preencher carrinhos.
* Os clientes também podem criar e agendar segmentos de remarketing personalizados específicos às necessidades de seus usuários.

## Procedimento de integração e pré-requisitos{#integration-procedure-and-prerequisites}

Usando um assistente "plug and play", os processos intuitivos passo a passo o guiarão pelos pontos de sincronização do sistema e inicializarão a integração.

Essa integração dos Conectores de dados exige o seguinte:

### Pré-requisitos da Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Data Warehouse
* Conta da Adobe [!DNL Analytics]
* Variáveis disponíveis e configuradas, incluindo eVars e eventos personalizados. [!DNL Analytics]

### Pré-requisitos do parceiro: {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Uma conta emarsys ativa

Para obter instruções de integração passo a passo, consulte [Execução do Assistente de integração dos Conectores de dados.](/help/import/data-connectors/emarsys-overview/emarsys-wizard.md)

## Preços{#pricing}

Essa integração dos Conectores de dados inclui considerações sobre preços que você precisa conhecer.

### Considerações sobre preços da Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Pode haver taxas recorrentes e de implementação associadas a essa integração. Entre em contato com seu representante de conta da Adobe para obter detalhes sobre preços.

### Considerações sobre preços do parceiro {#section-c6afad08c34b43e3a7a3637eea3328c3}

Pode haver taxas associadas a essa integração. Entre em contato com seu gerente de relacionamento para obter informações sobre preços.

## O Que Você Deve Saber Antes De Ativar Esta Integração{#what-you-should-know-before-activating-this-integration}

Antes de ativar essa integração, analise os itens a seguir em relação às implantações do Adobe Analytics e do software de email.

Isso garantirá que as práticas recomendadas ou pré-requisitos apropriados estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem-sucedida. Analise as seguintes informações sobre a integração dos Conectores de dados conforme ela se relaciona ao emarsys:

* **** Conta emarsys válida: Para usar a integração de email dos Conectores de dados, um cliente deve ter uma conta do emarsys válida.
* **** Cliente atual do emarsys: Essa integração exige que você seja um cliente da Adobe e do emarsys. Se você não for atualmente um cliente do emarsys, não terá as informações necessárias para concluir o assistente de integração. Se você for atualmente um cliente do emarsys, precisará da sua ID da conta emarsys ou do identificador exclusivo atribuído à sua organização para concluir o assistente de integração.
* Depois de concluir o assistente dos Conectores de dados, entre em contato com seu Gerente de contas emarsys para ativar a integração em seu eMarketing Suite do emarsys.

### Adobe Analytics{#adobe-analytics}

Examine as seguintes informações sobre a integração dos Conectores de dados, conforme ela se relaciona ao Adobe Analytics:

* **** Conjunto de relatórios específico: Observe que essa integração é específica do conjunto de relatórios. Verifique se você selecionou o conjunto de relatórios desejado antes de ativar a integração.
* **** Representante autorizado: Esteja ciente de que a habilitação dessa integração pode fazer com que sua empresa incorra taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou com seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você declara que é um representante autorizado da sua empresa; e, como tal, sua empresa concorda em pagar as taxas, se houver, estabelecidas no contrato de serviço descrito acima.
* **** Data Warehouse: Essa integração exige que o Data Warehouse seja habilitado para gerar segmentos de recomercialização. Se você não tiver ativado o Data Warehouse, entre em contato com a Adobe para obter detalhes.
* **** ID do destinatário: A integração exige que capturemos e armazenemos uma "ID de visitante" em uma variável do Analytics (eVar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema emarsys. Essa "ID do destinatário" está associada ao comportamento do visitante downstream no site (abandonos de carrinho, compras etc.) que é puxada para o sistema emarsys e pode ser aproveitada para fins de recomercialização. Como parte do processo de configuração, você deve identificar uma eVar para essa finalidade quando solicitado pelo Assistente.
* **** Rastreamento externo: Se você não estiver seguindo atualmente a prática recomendada de habilitar o rastreamento externo para cada campanha de email enviada, é necessário fazê-lo para garantir uma integração bem-sucedida. Consulte a seção emarsys abaixo para obter detalhes.
* **** Conformidade com privacidade: Você deve entender que ao ativar o rastreamento de ID de destinatário ou visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade que exigem a implementação de procedimentos apropriados por sua organização, como informar e dar o consentimento aos visitantes do site.

