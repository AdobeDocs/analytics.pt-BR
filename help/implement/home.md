---
title: Implementação do Adobe Analytics
description: Implementar o Adobe Analytics no site, propriedade ou aplicativo.
feature: Implementation Basics
source-git-commit: ad0099e41315b5e61cd62747e68f578266b47054
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 40%

---

# Implementação do Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

A Adobe requer código no seu site ou aplicativo para enviar dados aos servidores de coleta de dados da Adobe. As etapas a seguir indicam como uma implementação típica funciona.

1. Quando um visitante acessa o seu site, uma solicitação é feita ao seu servidor da Web.
2. O servidor Web do seu site envia as informações de código da página, que é exibida no navegador.
3. A página é carregada e o código JavaScript do Analytics é executado.
O código JavaScript envia uma solicitação de imagem para os servidores de coleta de dados do Adobe. Os dados da página definidos na implementação são enviados como parte de uma cadeia de caracteres de consulta nesta solicitação de imagem.

4. A Adobe retorna uma imagem pixelada transparente.
5. Os servidores do Adobe armazenam dados coletados em um ou mais *conjuntos de relatórios*.
6. Os dados do conjunto de relatórios preenchem os relatórios que você pode acessar por um navegador.

A execução do código JavaScript ocorre rapidamente e a maneira que os tempos de carregamento de uma página são afetados não é visível. Essa abordagem permite que você conte as páginas que foram exibidas quando um visitante clicou em **[!UICONTROL Recarregar]** ou **[!UICONTROL Voltar]** para acessar uma página, já que o JavaScript é executado mesmo quando a página é recuperada do cache.

O Adobe Analytics requer código em seu site, aplicativo móvel ou outro aplicativo para enviar dados aos servidores de coleta de dados. Há vários métodos para implementar esse código, dependendo da plataforma e das necessidades da organização.

## Métodos de implementação do site

Para seu **site**, os seguintes métodos de implementação estão disponíveis:

* **Extensão do SDK da Web**: O método padronizado e recomendado para implementar o Adobe Analytics para novos clientes. Instale o **Extensão do AEP Web SDK** na coleta de dados do Adobe Experience Platform **Tags**, use uma tag loader em cada página e envie dados para o Adobe Experience Platform **Rede Edge** em um formato conveniente para a organização. A Rede de borda encaminha os dados recebidos para o Adobe Analytics no formato correto.
   ![Extensão do SDK da Web](./assets/websdk-extension-implementation.png)
Consulte [Implementar o Adobe Analytics usando a extensão Adobe Experience Platform Web SDK](./aep-edge/overview.md) para obter mais informações.

* **SDK da Web**: você pode carregar manualmente as bibliotecas do SDK da Web no seu site se não quiser usar a Coleção de dados da Adobe Experience Platform. Referência à biblioteca do SDK da Web (`alloy.js`) em cada página e envie as chamadas de rastreamento desejadas para a Adobe Experience Platform **Rede Edge** em um formato conveniente para a organização. A Rede de borda encaminha os dados recebidos para o Adobe Analytics no formato correto.
   ![Web SDK](./assets/websdk-implementation.png)
Consulte [Implementar o Adobe Analytics usando o Adobe Experience Platform Web SDK](./aep-edge/overview.md) para obter mais informações.


* **Extensão do Analytics**: Instale o **Extensão do Adobe Analytics** na coleta de dados do Adobe Experience Platform **Tags**. Coloque uma tag loader em cada página e use a extensão Adobe Analytics para determinar como cada variável é definida. Use esse método de implementação se desejar a conveniência das Tags, mas não quiser usar a infraestrutura da Edge Network.
   ![Extensão do Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulte [Implementar o Adobe Analytics usando a extensão Analytics](launch/overview.md) para obter mais informações.

* **JavaScript herdado:** o método manual histórico para implementar o Adobe Analytics. Referência à biblioteca do AppMeasurement (`AppMeasurement.js`) em cada página e, em seguida, descreva as variáveis e configurações usadas em uma implementação.
   ![JavaScript herdado](./assets/appmeasurement-implementation.png)
Esse método de implementação pode ser útil para implementações que usam código personalizado e ainda é recomendado quando você (deseja) usar:

   * [dados do activity map em nível de clique](../analyze/activity-map/activity-map.md),

   * [medição de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=pt-BR),

   * [API do livestream ou acionadores do livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [Rastreamento de página do AMP](./other/amp.md)
   Consulte [Implementar o Adobe Analytics com o AppMeasurement para JavaScript](js/overview.md) para obter mais informações.

O seguinte fluxo de decisão pode ajudar você a selecionar um método de implementação:

![Árvore de decisão](./assets/decision-tree.png)


>[!TIP]
>
>Entre em contato com o Adobe para obter conselhos e práticas recomendadas sobre qual implementação escolher, com base na sua situação atual. >

## Métodos de implementação do aplicativo móvel

Para seu **aplicativo móvel**, os seguintes métodos de implementação estão disponíveis:

* **Extensão do SDK móvel**: O método padronizado e recomendado para implementar o Adobe Analytics no aplicativo móvel. Use bibliotecas dedicadas para enviar dados facilmente ao Adobe a partir do aplicativo móvel. Instale o **Extensão do Adobe Experience Platform Mobile SDK** na coleta de dados do Adobe Experience Platform **Tags** e implemente o código correto no aplicativo para importar bibliotecas, registrar extensões e carregar a configuração da tag. Isso envia dados para o Adobe Experience Platform **Rede Edge** em um formato conveniente para a organização. O Experience Edge encaminha os dados de entrada para o Adobe Analytics no formato correto.
   ![Extensão do SDK móvel](./assets/mobilesdk-extension.png)

   Consulte [Implementar o Adobe Analytics usando o Adobe Experience Platform Mobile SDK](../implement/aep-edge/mobile-sdk/overview.md) para obter mais informações.

* **Extensão do Analytics**: Instale o **Extensão do Adobe Analytics** na coleta de dados do Adobe Experience Platform **Tags**e implemente o código correto no aplicativo para importar bibliotecas, registrar extensões e carregar a configuração da tag. Use a extensão Analytics para determinar como cada variável é definida. Use esse método se desejar a conveniência da Coleta de dados do Adobe Experience Platform, mas não quiser usar a infraestrutura de rede Experience Platform, Adobe Edge.
   ![Extensão do Analytics](./assets/mobilesdk-analytics-extension.png)

   Consulte [Implementar o Adobe Analytics usando a extensão Analytics](../implement/aep-edge/mobile-sdk/overview.md) para obter mais informações.


>[!CAUTION]
>
>O suporte à versão 4 dos SDKs móveis terminou em 31 de agosto de 2021. Consulte [Perguntas frequentes sobre o fim de suporte aos SDKs móveis da versão 4](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/) para obter mais informações.

## Artigos principais de implementação do Analytics

* [Assumir o controle de uma implementação existente do Adobe Analytics](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Criar uma propriedade de tag na Experience Platform](launch/create-analytics-property.md)
* [Atualizações do AppMeasurement](appmeasurement-updates.md)

## Mais guias do usuário do Analytics

[Guias do usuário do Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=pt-BR)

## Principais recursos do Analytics

* [Entre em contato com o Atendimento ao cliente](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=pt-BR#support)
* [Fórum do Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=pt)
* [Recursos do Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
