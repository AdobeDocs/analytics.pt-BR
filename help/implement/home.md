---
title: Implementação do Adobe Analytics
description: Implementar o Adobe Analytics no site, propriedade ou aplicativo.
feature: Implementation Basics
source-git-commit: eae2b75d47a044b36ff9e5bbb311d1a2906faf91
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 97%

---

# Implementação do Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

A Adobe requer código no seu site ou aplicativo para enviar dados aos servidores de coleta de dados da Adobe. As etapas a seguir indicam como uma implementação típica funciona.

1. Quando um visitante acessa o seu site, uma solicitação é feita ao seu servidor da Web.
2. O servidor Web do seu site envia as informações de código da página, que é exibida no navegador.
3. A página é carregada e o código JavaScript do Analytics é executado.
O código JavaScript envia uma solicitação de imagem para os servidores de coleção de dados da Adobe. Os dados da página definidos na implementação são enviados como parte de uma cadeia de caracteres de consulta nesta solicitação de imagem.

4. A Adobe retorna uma imagem pixelada transparente.
5. Os servidores do Adobe armazenam dados coletados em um ou mais *conjuntos de relatórios*.
6. Os dados do conjunto de relatórios preenchem os relatórios que você pode acessar por um navegador.

A execução do código JavaScript ocorre rapidamente e a maneira que os tempos de carregamento de uma página são afetados não é visível. Essa abordagem permite que você conte as páginas que foram exibidas quando um visitante clicou em **[!UICONTROL Recarregar]** ou **[!UICONTROL Voltar]** para acessar uma página, já que o JavaScript é executado mesmo quando a página é recuperada do cache.

O Adobe Analytics requer código em seu site, aplicativo móvel ou outro aplicativo para enviar dados aos servidores de coleta de dados. Há vários métodos para implementar esse código, dependendo da plataforma e das necessidades da organização.

## Métodos de implementação de site

Os seguintes métodos de implementação estão disponíveis para seu **site**:

* **Extensão do SDK da web**: o método padronizado e recomendado para implementar o Adobe Analytics para novos clientes. Instale a **extensão do SDK da web da AEP** nas **Tags** da coleção de dados da Adobe Experience Platform, use uma tag de carregamento em cada página e envie os dados para a **rede de borda** da Adobe Experience Platform em um formato conveniente para sua organização. A rede de borda encaminha os dados de entrada para o Adobe Analytics no formato correto.
   ![Extensão do SDK da Web](./assets/websdk-extension-implementation.png)
Consulte [Implementar o Adobe Analytics usando a extensão do SDK da web da Adobe Experience Platform](./aep-edge/overview.md) para obter mais informações.

* **SDK da Web**: você pode carregar manualmente as bibliotecas do SDK da web no seu site se não quiser usar a coleção de dados da Adobe Experience Platform. Referencie à biblioteca do SDK da web (`alloy.js`) em cada página e envie as chamadas de rastreamento desejadas para a **rede de borda** da Adobe Experience Platform em um formato conveniente para a sua organização. A rede de borda encaminha os dados de entrada para o Adobe Analytics no formato correto.
   ![SDK da Web](./assets/websdk-implementation.png)
Consulte [Implementar o Adobe Analytics usando o SDK da web da Adobe Experience Platform](./aep-edge/overview.md) para obter mais informações.


* **Extensão do Analytics**: instale a **extensão do Adobe Analytics** nas **Tags** da coleção de dados da Adobe Experience Platform. Insira uma tag de carregamento em cada página e use a extensão do Adobe Analytics para determinar como cada variável é definida. Use esse método de implementação se desejar a praticidade das tags, mas não quiser usar a infraestrutura da rede de borda.
   ![Extensão do Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulte [Implementar o Adobe Analytics usando a extensão do Analytics](launch/overview.md) para obter mais informações.

* **JavaScript herdado:** o método manual histórico para implementar o Adobe Analytics. Referencie a biblioteca do AppMeasurement (`AppMeasurement.js`) em cada página e, em seguida, descreva as variáveis e configurações usadas em uma implementação.
   ![JavaScript herdado](./assets/appmeasurement-implementation.png)
Esse método de implementação pode ser útil para implementações que usam código personalizado e ainda é recomendado quando você (deseja) usar:

   * [dados do activity map](../analyze/activity-map/activity-map.md),

      >[!INFO]
      >
      >Usando o SDK da Web mais recente, o Activity Map é compatível. Consulte [Ativar o Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) para obter mais informações.

   * [medição de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=pt-BR),

   * [APIs de transmissão ao vivo ou acionadores de transmissão ao vivo](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [Rastreamento de páginas do AMP](./other/amp.md)
   Consulte [Implementar o Adobe Analytics com o AppMeasurement para JavaScript](js/overview.md) para obter mais informações.

O seguinte fluxo de decisão pode ajudar você a selecionar um método de implementação:

![Árvore de decisão](./assets/decision-tree.png)


>[!TIP]
>
>Entre em contato com a Adobe para obter orientações e práticas recomendadas sobre qual implementação escolher, com base na sua situação atual.

## Métodos de implementação para aplicativos móveis

Os seguintes métodos de implementação estão disponíveis para seu **aplicativo móvel**:

* **Extensão do SDK móvel**: o método padronizado e recomendado para implementar o Adobe Analytics no aplicativo móvel. Use bibliotecas dedicadas para enviar dados facilmente à Adobe a partir de seu aplicativo móvel. Instale a **extensão do SDK móvel da Adobe Experience Platform** nas **Tags** da coleção de dados da Adobe Experience Platform e implemente o código correto no aplicativo para importar bibliotecas, registrar extensões e carregar a configuração da tag. Isso envia dados para a **rede de borda** da Adobe Experience Platform em um formato conveniente para a sua organização. O Experience Edge encaminha os dados de entrada para o Adobe Analytics no formato correto.
   ![Extensão do SDK móvel](./assets/mobilesdk-extension.png)

   Consulte [Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform](../implement/aep-edge/mobile-sdk/overview.md) para obter mais informações.

* **Extensão do Analytics**: instale a **extensão do Adobe Analytics** nas **Tags** da coleção de dados da Adobe Experience Platform e implemente o código correto no aplicativo para importar bibliotecas, registrar extensões e carregar a configuração da tag. Use a extensão do Analytics para determinar como cada variável é definida. Use este método de implementação se desejar a praticidade da coleção de dados da Adobe Experience Platform, mas não quiser usar a infraestrutura de rede de borda da Adobe Experience Platform.
   ![Extensão do Analytics](./assets/mobilesdk-analytics-extension.png)

   Consulte [Implementar o Adobe Analytics usando a extensão do Analytics](../implement/aep-edge/mobile-sdk/overview.md) para obter mais informações.


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
* [Recursos do Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=pt)
