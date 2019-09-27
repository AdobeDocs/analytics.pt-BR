---
description: Saiba mais sobre como as visitas no seu site se tornam relatórios no Adobe Analytics.
keywords: Implementação do Analytics;coleta de dados
seo-description: Saiba mais sobre como as visitas no seu site se tornam relatórios no Adobe Analytics.
seo-title: Coleta de dados
solution: Analytics
title: Coleta de dados
topic: Desenvolvedor e implementação
uuid: d0d6098d-113e-4cf5-bb89-e435f7b6b1af
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Coleta de dados

Saiba mais sobre como as visitas no seu site se tornam relatórios no Adobe Analytics.

A coleta de dados do Analytics é realizada por uma solicitação de imagem especial aos servidores de coleta de dados da Adobe. Na maioria das implementações, um código JavaScript é colocado nas páginas da Web que estão sendo monitoradas. Quando uma página da Web com tag é carregada no navegador do visitante, o navegador executa nosso código JavaScript, realizando um processo de lógica computacional para captar informações dos visitantes e preencher as tags corretamente. A última etapa do processamento do JavaScript é uma solicitação de imagem ao servidor de coleta de dados do Analytics, que coleta os dados enviados e retorna uma pequena imagem transparente para o navegador do visitante.

Como o afunilamento típico em um processamento do navegador equivale ao tempo gasto para baixar os elementos da página (imagens etc) dos servidores da Web, o tempo necessário para que o navegador execute o código JavaScript é insignificante. No entanto, a última etapa, na qual o navegador do visitante solicita uma imagem ao servidor de coleta de dados da Adobe, não é acrescentada ao tempo total de download da página. O efeito geral no tempo de download da página depende da proximidade do visitante (geralmente em hops e não em distância geográfica) em relação aos servidores da coleta de dados da Adobe.

A Adobe criou várias maneiras de enviar dados para o Analytics. Esses métodos incluem rastrear informações em tempo real de:

* Aplicativos capazes de acessas a Internet
* Campanhas
* Aplicativos de cliente/servidor
* E-mails
* Dispositivos móveis
* Quiosques baseados na Web
* Sites

<!-- 

<p>Need to reconcile with Data Collection topics in the user guide, in this guide, and in reference. </p>

 -->

1. Quando um visitante acessa o seu site, uma solicitação é feita ao seu servidor da Web.

   ![](assets/how-data-is-collected-1.png)

1. O servidor Web do seu site envia as informações de código da página, que é exibida no navegador.

   ![](assets/how-data-is-collected-2.png)

1. A página é carregada e o código JavaScript do Analytics é executado.

   ![](assets/how-data-is-collected-3.png)

   O código JavaScript envia uma solicitação de imagem ao servidor da Adobe, passando as variáveis, métricas e os dados da página definidos na sua implementação.

   **Exemplo de código JavaScript:** o código JavaScript é colocado dentro das tags do corpo (body) de uma página:

   ![](assets/code-example-geometrixx.png)

   **Exemplo de solicitação de imagem:** um fragmento de uma solicitação de imagem com o nome da página mencionado:

   ![](assets/image-request-snippet.png)

   >[!NOTE]
   >
   >Cada solicitação de imagem contém uma string de número aleatório para impedir o armazenamento em cache do navegador e garantir que as solicitações de imagem subsequentes sejam feitas pelo navegador.

1. A Adobe retorna uma imagem pixelada transparente.

   ![](assets/how-data-is-collected-4.png)

   O código coleta detalhes adicionais automaticamente (como sistema operacional, tipo de navegador, altura e largura do navegador, endereço IP e idioma do navegador).

1. Os servidores da Adobe armazenam dados de análise da Web em *`report suites`* (seu repositório de dados).

   ![](assets/how-data-is-collected-5.png)

   Um [conjunto de relatórios](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html) define o relatório completo e independente de um site específico ou subconjuntos de páginas da Web.

1. Os dados do conjunto de relatórios preenchem os relatórios que você pode acessar por um navegador.

   ![](assets/how-data-is-collected-6.png)

   **Exemplo de relatório:**

   ![](assets/two-months-summary-project.png)

   A execução do código JavaScript ocorre rapidamente e a maneira que os tempos de carregamento de uma página são afetados não é visível. Essa abordagem permite que você conte as páginas que foram exibidas quando um visitante clicou em **[!UICONTROL Recarregar]** ou **Voltar]para acessar uma página, já que o JavaScript é executado mesmo quando a página é recuperada do cache.[!UICONTROL **

Para obter mais detalhes, consulte:

* [Coleta de dados](../../implement/js-implementation/data-collection/query-parameters.md)
* [Criar um elemento de dados](../../implement/c-implement-with-dtm/t-data-element.md#task_962EF08CE2AE49B3B739295F6E4792C2)
* [Data Warehouse](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html)
* [Ad Hoc Analysis](https://marketing.adobe.com/resources/help/en_US/dsc/c_getting_started.html)
* [Fontes de dados](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_datasources.html)
* [Data Connectors](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_genesis.html)
* [Feed de dados do Analytics](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md)

>[!MORE_LIKE_THIS]
>       
>* [Experience Cloud Debugger](/help/implement/impl-testing/debugger.md)

