---
title: Implementação do Adobe Analytics
description: Implementar o Adobe Analytics no site, propriedade ou aplicativo.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 79%

---

# Implementação do Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Veja um vídeo com uma visão geral do Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

A Adobe requer código no seu site ou aplicativo para enviar dados aos servidores de coleta de dados da Adobe. As etapas a seguir indicam como uma implementação típica funciona.

1. Quando um visitante acessa o seu site, uma solicitação é feita ao seu servidor da Web.
2. O servidor Web do seu site envia as informações de código da página, que é exibida no navegador.
3. A página é carregada e o código JavaScript do Analytics é executado.
4. O código JavaScript envia uma solicitação de imagem de pixel de 1x1 para os servidores de coleta de dados do Adobe. Os dados da página definidos na implementação são enviados como parte de uma cadeia de caracteres de consulta nesta solicitação de imagem.
5. A imagem solicitada retorna
6. Os servidores do Adobe analisam e armazenam dados coletados em um conjunto de relatórios.
7. Os dados do conjunto de relatórios preenchem os relatórios que você pode acessar por um navegador.


O Adobe oferece vários métodos para implementar esse código, dependendo da plataforma e das necessidades da organização.

* **Extensão do SDK da Web**: O método atual, padronizado e recomendado para implementar o Adobe Analytics. Instale a extensão SDK da Web da Coleção de dados da Adobe Experience Platform, use um tag de carregamento em cada página e envie dados para o Adobe Experience Platform Edge em um formato conveniente para sua organização. O Experience Edge encaminha os dados de entrada para o Adobe Analytics no formato correto.
* **Web SDK**: Você pode carregar manualmente as bibliotecas do SDK da Web no seu site se não quiser usar Tags. Faça referência à biblioteca do SDK da Web em cada página e envie as chamadas de rastreamento desejadas para o Adobe Experience Edge.
* **Extensão do Adobe Analytics**: instale a extensão do Adobe Analytics da Coleção de dados da Adobe Experience Platform. Insira uma tag de carregamento em cada página e use a extensão do Analytics para determinar como cada variável é definida.
* **JavaScript herdado:** o método manual histórico para implementar o Adobe Analytics. Descreve as variáveis e as configurações usadas em uma implementação, que pode ser útil para implementações usando regras com código personalizado.
* **SDK móvel**: bibliotecas dedicadas para enviar dados facilmente à Adobe a partir do aplicativo móvel.

## Artigos principais de implementação do Analytics

* [Assumir o controle de uma implementação existente do Adobe Analytics](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Criar uma propriedade de tag na Experience Platform](launch/create-analytics-property.md)
* [Atualizações do AppMeasurement](appmeasurement-updates.md)

## Mais guias do usuário do Analytics

[Guias do usuário do Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=pt-BR)

## Principais recursos do Analytics

* [Entre em contato com o Atendimento ao cliente](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=pt-BR#support)
* [Fórum do Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Recursos do Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=pt)
* [Experience League](https://experienceleague.adobe.com/?lang=pt-BR#dashboard/learning)
