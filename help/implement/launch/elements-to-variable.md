---
title: Mapear elementos de dados de tag para variáveis do Analytics
description: Atribua elementos de dados às variáveis do Analytics para que você possa usá-los como dimensões no Analysis Workspace.
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 76%

---

# Mapear elementos de dados de tag para variáveis do Analytics

Depois de ter um repositório de elementos de dados de tags, você pode atribuí-los às dimensões do Analytics.

>[!NOTE]
>A Adobe Experience Platform Launch foi reformulada como um conjunto de tecnologias de coleta de dados no Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obter uma referência consolidada das alterações de terminologia.

## Pré-requisitos

[Mapear objetos de camada de dados para elementos](layer-to-elements.md) de dados: Certifique-se de entender os elementos de dados da tag e de ter vários elementos para trabalhar.

[Criar um documento de design de solução](../prepare/solution-design.md): um documento de design de solução é essencial para se manter organizado. O documento de design de solução simplifica a atribuição de elementos de dados às variáveis do Analytics.

## Atribuir elementos de dados às variáveis do Analytics

Publicar uma biblioteca de tags após seguir essas etapas permite usar dimensões personalizadas no Analysis Workspace. É possível definir as variáveis do Analytics globalmente ou em regras individuais.

### Definir variáveis globais

As variáveis globais são ideais nos casos em que você deseja definir valores variáveis em todas as páginas em que o elemento de dados existe.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique na propriedade de tag desejada.
1. Clique na [!UICONTROL guia Extensões] e, em seguida, clique em [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Clique na opção [!UICONTROL Variáveis globais], que revela a interface para atribuir variáveis globais.

### Definir variáveis em regras

As variáveis definidas em regras são ideais nos casos em que as variáveis não são definidas em cada página. Você define os critérios na regra. Consulte [Regras](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/rules.html?lang=pt-BR) no guia do usuário do Adobe Experience Platform Launch.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique na propriedade de tag desejada.
1. Clique na guia [!UICONTROL Regras] e, em seguida, clique na regra desejada (ou crie uma).
1. Clique no botão [!UICONTROL Adicionar] em [!UICONTROL Ações].
1. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como Definir variáveis.
1. Clique no ícone ![Elemento de dados](assets/data-element.png) à direita da variável do Analytics desejada. O [documento de design de solução](../prepare/solution-design.md) da sua organização determina qual variável do Analytics usar.
1. Selecione o elemento de dados desejado na janela modal. Clique em [!UICONTROL Selecionar].
1. O nome do elemento de dados é adicionado ao campo de texto rodeado por sinais `%`. Por exemplo, se você nomeasse o elemento de dados como &quot;Nome da página&quot;, veria a string `%Page name%` ao atribuir um elemento de dados a uma variável.

>[!TIP]
>
>É possível concatenar elementos de dados na mesma variável. Por exemplo, se você tiver um elemento de dados &quot;Nome do host&quot; e um elemento de dados &quot;Nome do caminho&quot;, é possível combinar ambos em uma única variável usando `%Hostname%%Pathname%`.

## Próximas etapas

[Variáveis de página](../vars/page-vars/page-variables.md): saiba quais variáveis de nível de página você pode usar na implementação para obter mais das dimensões no Analysis Workspace.

[Variáveis de configuração](../vars/config-vars/configuration-variables.md): saiba quais variáveis de configuração você pode usar na implementação para desbloquear mais recursos no Adobe Analytics.
