---
title: Implementação do Adobe Analytics
description: Implemente o Adobe Analytics em seu site, propriedade ou aplicativo.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Implementação do Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

A Adobe requer código no seu site ou aplicativo para enviar dados aos servidores de coleta de dados da Adobe. As etapas a seguir indicam como uma implementação típica funciona.

1. Quando um visitante acessa o seu site, uma solicitação é feita ao seu servidor da Web.
2. O servidor Web do seu site envia as informações de código da página, que é exibida no navegador.
3. A página é carregada e o código JavaScript do Analytics é executado.
O código JavaScript envia uma solicitação de imagem para os servidores de coleta de dados da Adobe. Os dados da página que você definiu em sua implementação são enviados como parte de uma string de consulta nesta solicitação de imagem.

4. A Adobe retorna uma imagem pixelada transparente.
5. Os servidores da Adobe armazenam dados coletados em um conjunto *de* relatórios.
6. Os dados do conjunto de relatórios preenchem os relatórios que você pode acessar por um navegador.

   A execução do código JavaScript ocorre rapidamente e a maneira que os tempos de carregamento de uma página são afetados não é visível. Essa abordagem permite que você conte as páginas que foram exibidas quando um visitante clicou em **[!UICONTROL Recarregar]**ou**[!UICONTROL  Voltar]** para acessar uma página, já que o JavaScript é executado mesmo quando a página é recuperada do cache.

O Adobe Analytics requer código em seu site, aplicativo móvel ou outro aplicativo para enviar dados aos servidores de coleta de dados. Existem vários métodos para implementar esse código, dependendo da plataforma e das necessidades de sua organização.

* **Adobe Experience Platform Launch**: O método padronizado e recomendado para implementar o Adobe Analytics. Coloque uma tag de carregamento em cada página e use a interface do Launch para determinar como cada variável é definida.
* **Gerenciamento** dinâmico de tags: O antecessor do Launch. O DTM usa uma interface semelhante para implementar o Analytics, mas não é mais atualizada e não é tão flexível. A Adobe recomenda usar o Launch para implementar o Adobe Analytics.
* **JavaScript** herdado: O método manual histórico para implementar o Adobe Analytics. Descreve as variáveis e as configurações usadas em uma implementação, que pode ser útil para implementações do Launch usando regras com código personalizado.
* **SDK** móvel: Bibliotecas dedicadas para enviar dados facilmente para a Adobe a partir do aplicativo móvel.

## Artigos principais de implementação do Analytics

* [Adobe Debugger](validate/debugger.md)
* [Criar uma propriedade na Experience Platform Launch](launch/create-analytics-property.md)
* [Atualizações do AppMeasurement](appmeasurement-updates.md)

## Mais guias do usuário do Analytics

[Guias do usuário do Analytics](/help/landing/home.md)

## Principais recursos do Analytics

* [Entre em contato com o Atendimento ao cliente](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Fórum do Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Recursos do Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
