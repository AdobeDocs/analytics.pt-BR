---
title: Implementação do Adobe Analytics
description: Implementar o Adobe Analytics no site, propriedade ou aplicativo.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# Implementação do Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Veja um vídeo com uma visão geral do Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

A Adobe requer código no seu site ou aplicativo para enviar dados aos servidores de coleta de dados da Adobe. As etapas a seguir indicam como uma implementação típica funciona.

1. Quando um visitante acessa o seu site, uma solicitação é feita ao seu servidor da Web.
2. O servidor Web do seu site envia as informações de código da página, que é exibida no navegador.
3. A página é carregada e o código JavaScript do Analytics é executado.
O código JavaScript envia uma solicitação de imagem para os servidores de coleta de dados da Adobe. Os dados da página definidos na implementação são enviados como parte de uma cadeia de caracteres de consulta nesta solicitação de imagem.

4. A Adobe retorna uma imagem pixelada transparente.
5. Os servidores do Adobe armazenam dados coletados em um ou mais *conjuntos de relatórios*.
6. Os dados do conjunto de relatórios preenchem os relatórios que você pode acessar por um navegador.

   A execução do código JavaScript ocorre rapidamente e a maneira que os tempos de carregamento de uma página são afetados não é visível. Essa abordagem permite que você conte as páginas que foram exibidas quando um visitante clicou em **[!UICONTROL Recarregar]** ou **[!UICONTROL Voltar]** para acessar uma página, já que o JavaScript é executado mesmo quando a página é recuperada do cache.

O Adobe Analytics requer código em seu site, aplicativo móvel ou outro aplicativo para enviar dados aos servidores de coleta de dados. Há vários métodos para implementar esse código, dependendo da plataforma e das necessidades da organização.

* **SDK da Web**: o método padronizado e recomendado para implementar o Adobe Analytics. Instale a extensão SDK da Web da Coleção de dados da Adobe Experience Platform, use um tag de carregamento em cada página e envie dados para o Adobe Experience Platform Edge em um formato conveniente para sua organização. O Experience Edge encaminha os dados de entrada para o Adobe Analytics no formato correto.
* **Extensão do Adobe Analytics**: instale a extensão do Adobe Analytics da Coleção de dados da Adobe Experience Platform. Insira uma tag de carregamento em cada página e use a extensão do Analytics para determinar como cada variável é definida.
* **JavaScript herdado:** o método manual histórico para implementar o Adobe Analytics. Descreve as variáveis e as configurações usadas em uma implementação, que pode ser útil para implementações de tag usando regras com código personalizado.
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
* [Experience League](https://experienceleague.adobe.com/?lang=pt-BR#home)
