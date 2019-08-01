---
description: Descreve os pré-requisitos para uma integração bem-sucedida.
seo-description: Descreve os pré-requisitos para uma integração bem-sucedida.
seo-title: Pré-requisitos de integração
solution: Analytics
title: Pré-requisitos de integração
uuid: ac 93 bf 4 d-a 071-4 fac -9 d 42-c 4856463 cbb 6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Integration Prerequisites{#integration-prerequisites}

Descreve os pré-requisitos para uma integração bem-sucedida.

Antes de ativar essa integração, analise os seguintes itens em relação às implantações do Adobe Analytics e seu software de email.

Isso garante que as práticas recomendadas e pré-requisitos apropriadas estejam em vigor antes da ativação, o que resultará em uma integração ideal e bem sucedida.

## Prerequisites for Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Conjunto de relatórios específico**: Seja recomendável que esta integração seja específica do conjunto de relatórios. Certifique-se de ter selecionado o conjunto de relatórios desejado antes de ativar a integração
* **Variáveis do Analytics disponíveis e** configuradas: Essa integração requer eventos personalizados e evars personalizadas, e, opcionalmente, eventos adicionais e evars adicionais.

   See [Configure Analytics variables for Lyris](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **Representante autorizado**: Seja recomendável que a habilitação dessa integração faça com que sua empresa envolva taxas de acordo com seu contrato de serviço com a Adobe, Inc. ou seu contrato de serviço com um dos parceiros confiáveis da Adobe, conforme aplicável. Ao ativar essa integração, você representa que você é um representante autorizado da sua empresa; e, dessa forma, sua empresa concorda em pagar as taxas, se houver, no contrato de serviço descrito acima.
* **Data warehouse do Adobe Analytics**: Essa integração requer que o data warehouse do Adobe Analytics seja ativado para gerar segmentos de re-marketing. Se você não ativou o data warehouse, entre em contato com a Adobe para obter detalhes.
* **ID do destinatário**: A integração requer capturar e armazenar uma "ID do visitante" em uma variável do Analytics (evar). A ID do visitante (geralmente chamada de "ID do destinatário") é uma representação codificada ou numérica de um endereço de email do sistema Lyris. Essa «ID do destinatário» é associada ao comportamento de visitante descendente no site (abandonos de carrinho, compras etc.) que são retornados ao sistema Lyris e podem ser aproveitados para fins de re-marketing. Como parte do processo de configuração, você deve identificar uma evar para essa finalidade quando solicitado pelo Assistente.
* **Rastreamento externo**: Se você não estiver seguindo a melhor prática de ativar o rastreamento externo para cada campanha de email enviada, você deve fazê-lo para garantir uma integração bem-sucedida. Consulte a seção Lyris abaixo para obter detalhes
* **Conformidade de privacidade**: Você deve entender que ao ativar o rastreamento de Destinatário ou ID de visitante, esse recurso pode rastrear informações de identificação pessoal dos visitantes do site. Isso tem implicações de privacidade, exigindo a implementação dos procedimentos apropriados por sua organização, como fornecer aviso e consentimento dos visitantes do site.

## Prerequisites for Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Conta válida de Lyris**: Para usar essa integração com o Conector de dados, você deve ter uma conta Lyris válida.
* **Informações da conta**: Você exigirá as seguintes informações sobre a conta Lyris durante esta configuração de integração:

   * *Chave de API Lyris*: Usado para preenchimento de dados
   * *Parâmetros da string de consulta*: Eles são anexados no URL da página de aterrissagem para ID da mensagem e ID do destinatário (ID do visitante).
   * *Lyris Server/URL*: O valor do servidor usado no sistema Lyris
   * *ID do site Lyris*: Também conhecido como «ID do cliente», este é o valor exclusivo da sua instância de Lyris HQ. Isso pode ser localizado em «Informações do cliente» na seção «Inicial de conta» da emaillabs.

