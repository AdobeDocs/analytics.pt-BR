---
title: Implementação do Adobe Analytics
description: Implementar o Adobe Analytics no site, propriedade ou aplicativo.
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 83%

---

# Implementação do Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

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

* **Tags Adobe Experience Platform**: O método padronizado e recomendado para implementar o Adobe Analytics. Coloque uma tag loader em cada página e use a interface do usuário da coleta de dados para determinar como cada variável é definida.
* **JavaScript herdado:** o método manual histórico para implementar o Adobe Analytics. Descreve as variáveis e as configurações usadas em uma implementação, que pode ser útil para implementações de tags usando regras com código personalizado.
* **SDK móvel**: bibliotecas dedicadas para enviar dados facilmente à Adobe a partir do aplicativo móvel.

## Artigos principais de implementação do Analytics

* [Assumir o controle de uma implementação existente do Adobe Analytics](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Criar uma propriedade de tag no Experience Platform](launch/create-analytics-property.md)
* [Atualizações do AppMeasurement](appmeasurement-updates.md)

## Mais guias do usuário do Analytics

[Guias do usuário do Analytics](/help/landing/home.md)

## Principais recursos do Analytics

* [Entre em contato com o Atendimento ao cliente](https://helpx.adobe.com/br/contact/enterprise-support.ec.html)
* [Fórum do Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Recursos do Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
