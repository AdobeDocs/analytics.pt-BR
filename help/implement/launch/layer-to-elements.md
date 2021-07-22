---
title: Mapear objetos de camada de dados para elementos de dados
description: Configure tags para ler a partir da camada de dados.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 60%

---

# Mapear objetos de camada de dados para elementos de dados

Depois que sua organização tiver estabelecido e implementado uma camada de dados no site, você poderá mapear objetos de camada de dados para elementos de dados nas tags.

>[!NOTE]
>A Adobe Experience Platform Launch foi reformulada como um conjunto de tecnologias de coleta de dados no Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obter uma referência consolidada das alterações de terminologia.

## Pré-requisitos

[Criar uma camada de dados](../prepare/data-layer.md): verifique se existe uma camada de dados no site. Embora você possa mapear qualquer objeto JavaScript ou extrair elementos CSS diretamente da página, a Adobe recomenda essa prática como último recurso. Se o layout do site mudar, os seletores de CSS usados nas tags param de funcionar, causando perda de dados.

## Usar tags para criar elementos de dados

[Os ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) elementos de dados são componentes na interface do usuário da Coleta de dados que você pode usar na ferramenta. Você pode atribuir valores variáveis na extensão do Adobe Analytics usando elementos de dados.

1. Vá para [experience.adobe.com](https://experience.adobe.com) e faça logon quando solicitado.
1. Selecione **[!UICONTROL Launch / Data Collection]**.
1. Clique em **[!UICONTROL Ir para Iniciar/Coleta de dados]** e selecione **[!UICONTROL Tags]**.
1. Clique na propriedade de tag desejada.
1. Clique na guia **[!UICONTROL Elementos de dados]** e, em seguida, clique em **[!UICONTROL Adicionar elemento de dados]**.

   ![criar elemento de dados](assets/createelement.png)

1. Insira um nome para o elemento de dados. Pode ser um rótulo simples que corresponde a uma variável JavaScript na camada de dados que você deseja rastrear.
1. Na lista suspensa **[!UICONTROL Extensão]**, selecione **[!UICONTROL Principal]**.
1. Na lista suspensa **[!UICONTROL Tipo de elemento de dados]**, selecione **[!UICONTROL Variável JavaScript]**. Um campo de texto é exibido à direita, permitindo que você insira a variável JavaScript para mapear para esse elemento de dados.
1. Insira a variável Javascript desejada, normalmente na camada de dados. Por exemplo, se a camada de dados da sua organização corresponder muito à prática recomendada pela Adobe, um valor pode ser `digitalData.page.pageInfo.pageName`. Você pode usar o console do navegador para validar a sintaxe e os valores da variável JavaScript.
1. Clique em **[!UICONTROL Salvar]**.

## Próximas etapas

[Mapear elementos de dados para variáveis do Analytics](elements-to-variable.md): atribua elementos de dados às variáveis do Analytics para que você possa usá-los como dimensões no Analysis Workspace.
