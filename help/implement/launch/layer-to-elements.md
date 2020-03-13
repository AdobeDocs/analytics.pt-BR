---
title: Mapear objetos de camada de dados para elementos de dados
description: Configure o Launch para ler a partir da camada de dados.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Mapear objetos de camada de dados para elementos de dados

Depois que sua organização tiver estabelecido e implementado uma camada de dados no site, você poderá mapear objetos de camada de dados para elementos de dados no Launch.

## Pré-requisitos

[Criar uma camada](../prepare/data-layer.md)de dados: Verifique se existe uma camada de dados no site. Embora você possa mapear qualquer objeto JavaScript ou raspar elementos CSS diretamente da página, a Adobe recomenda essa prática como um último recurso. Se o layout do site mudar, os seletores de CSS usados no Launch param de funcionar, causando perda de dados.

## Usar o Adobe Experience Platform Launch para criar elementos de dados

[Os elementos](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) de dados são componentes no Launch que podem ser usados na ferramenta. Você pode atribuir valores variáveis na extensão do Adobe Analytics usando elementos de dados.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique na propriedade Launch desejada.
1. Click the [!UICONTROL Data Elements] tab, then click [!UICONTROL Add Data Element].

   ![criar elemento de dados](assets/createelement.png)

1. Insira um nome para seu elemento de dados. Pode ser um rótulo simples que corresponde a uma variável JavaScript na camada de dados que você deseja rastrear.
1. Na lista [!UICONTROL Extension] suspensa, selecione [!UICONTROL Core].
1. Na lista [!UICONTROL Data Element Type] suspensa, selecione [!UICONTROL JavaScript Variable]. Um campo de texto é exibido à direita, permitindo que você insira a variável JavaScript para mapear para esse elemento de dados.
1. Insira a variável do Javascript desejada, normalmente em sua camada de dados. Por exemplo, se a camada de dados de sua organização corresponder muito à prática recomendada pela Adobe, um valor pode ser `digitalData.page.pageInfo.pageName`. Você pode usar o console do navegador para validar a sintaxe e os valores da variável JavaScript.
1. Clique em [!UICONTROL Save].

## Próximas etapas

[Mapeie elementos de dados para variáveis](elements-to-variable.md)do Analytics: Atribua elementos de dados às variáveis do Analytics para que você possa usá-los como dimensões na Analysis Workspace.
