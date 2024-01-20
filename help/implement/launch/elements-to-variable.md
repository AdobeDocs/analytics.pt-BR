---
title: Mapear elementos de dados de tag para variáveis do Analytics
description: Atribua elementos de dados às variáveis do Analytics para que você possa usá-los como dimensões no Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 2aef8de290399f234921b09cf094485fc06f1c24
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 96%

---


# Mapear elementos de dados de tag para variáveis do Analytics

Depois de ter um repositório de elementos de dados de tags, você pode atribuí-los às dimensões do Analytics.

## Pré-requisitos

[Mapear objetos da camada de dados para elementos de dados](layer-to-elements.md): compreenda os elementos de dados da tag e de que você tem vários com os quais trabalhar.

[Criar um documento de design de solução](../prepare/solution-design.md): um documento de design de solução é essencial para se manter organizado. O documento de design de solução simplifica a atribuição de elementos de dados às variáveis do Analytics.

## Atribuir elementos de dados às variáveis do Analytics

A publicação de uma biblioteca de tags após seguir essas etapas permite usar dimensões personalizadas no Analysis Workspace. É possível definir as variáveis do Analytics globalmente ou em regras individuais.

### Definir variáveis globais

As variáveis globais são ideais nos casos em que você deseja definir valores variáveis em todas as páginas em que o elemento de dados existe.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Clique na [!UICONTROL guia Extensões] e, em seguida, clique em [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Clique na opção [!UICONTROL Variáveis globais], que revela a interface para atribuir variáveis globais.

### Definir variáveis em regras

As variáveis definidas em regras são ideais nos casos em que as variáveis não são definidas em cada página. Você define os critérios na regra. Consulte [Regras](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=pt-BR) na documentação de tags da Adobe Experience Platform.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Clique na guia [!UICONTROL Regras] e, em seguida, clique na regra desejada (ou crie uma).
1. Clique no botão [!UICONTROL Adicionar] em [!UICONTROL Ações].
1. Defina o [!UICONTROL Extensão] para o Adobe Analytics e a caixa de diálogo [!UICONTROL Tipo de ação] para definir variáveis.
1. Clique no ícone ![Elemento de dados](assets/data-element.png) à direita da variável do Analytics desejada. O [documento de design de solução](../prepare/solution-design.md) da sua organização determina qual variável do Analytics usar.
1. Selecione o elemento de dados desejado na janela modal. Clique em [!UICONTROL Selecionar].
1. O nome do elemento de dados é adicionado ao campo de texto rodeado por sinais `%`. Por exemplo, se você nomeasse o elemento de dados como &quot;Nome da página&quot;, veria a string `%Page name%` ao atribuir um elemento de dados a uma variável.

>[!TIP]
>
>É possível concatenar elementos de dados na mesma variável. Por exemplo, se você tiver um elemento de dados &quot;Nome do host&quot; e um elemento de dados &quot;Nome do caminho&quot;, é possível combinar ambos em uma única variável usando `%Hostname%%Pathname%`.

## Próximas etapas

[Variáveis de página](../vars/page-vars/page-variables.md): saiba quais variáveis de nível de página você pode usar na implementação para obter mais das dimensões no Analysis Workspace.

[Variáveis de configuração](../vars/config-vars/configuration-variables.md): saiba quais variáveis de configuração você pode usar na implementação para desbloquear mais recursos no Adobe Analytics.
