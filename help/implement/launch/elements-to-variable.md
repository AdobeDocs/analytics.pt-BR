---
title: Mapear elementos de dados do Launch para variáveis do Analytics
description: Atribua elementos de dados às variáveis do Analytics para que você possa usá-los como dimensões na Analysis Workspace.
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# Mapear elementos de dados do Launch para variáveis do Analytics

Depois que você tiver um repositório de elementos de dados no Adobe Experience Platform Launch, poderá atribuí-los às dimensões do Analytics.

## Pré-requisitos

[Mapear objetos de camada de dados para elementos](layer-to-elements.md)de dados: Certifique-se de compreender os elementos de dados no Launch e de que você tenha vários para trabalhar.

[Criar um documento](../prepare/solution-design.md)de design de solução: Um documento de design de solução é vital para se manter organizado. Seguir o documento de design da solução simplifica a atribuição de elementos de dados às variáveis do Analytics.

## Atribuir elementos de dados às variáveis do Analytics

Publicar uma biblioteca no Launch após seguir estas etapas permite usar dimensões personalizadas na Analysis Workspace. É possível definir as variáveis do Analytics globalmente ou em regras individuais.

### Definir variáveis globais

As variáveis globais são ideais nos casos em que você deseja definir valores variáveis em todas as páginas em que o elemento de dados existe.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique na propriedade Launch desejada.
1. Clique no [!UICONTROL Extensions tab]e, em seguida, clique [!UICONTROL Configure] na extensão do Adobe Analytics.
1. Clique no [!UICONTROL Global variables] acordeão, que revela a interface para atribuir variáveis globais.

### Definir variáveis em regras

As variáveis definidas nas regras são ideais nos casos em que as variáveis não são definidas em cada página. Você define os critérios na regra. See [Rules](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html) in the Adobe Experience Platform Launch user guide.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
1. Clique na propriedade Launch desejada.
1. Clique na [!UICONTROL Rules] guia e, em seguida, clique na regra desejada (ou crie uma).
1. Clique no [!UICONTROL Add] botão em [!UICONTROL Actions].
1. Defina o [!UICONTROL Extension] menu suspenso como Adobe Analytics e defina [!UICONTROL Action Type] Variáveis.
1. Clique no ícone do elemento [!Dde](assets/data-element.png) dados à direita da variável do Analytics desejada. O documento [de design de](../prepare/solution-design.md) solução da sua organização determina qual variável do Analytics deve ser usada.
1. Selecione o elemento de dados desejado na janela modal. Clique em [!UICONTROL Select].
1. O nome do elemento de dados é adicionado ao campo de texto rodeado por `%` sinais. Por exemplo, se você nomeasse seu elemento de dados como &quot;Nome da página&quot;, veria a string `%Page name%` ao atribuir um elemento de dados a uma variável.

> [!TIP] É possível concatenar elementos de dados na mesma variável. Por exemplo, se você tiver um elemento de dados &quot;Nome do host&quot; e um elemento de dados &quot;Nome do caminho&quot;, poderá combinar ambos em uma única variável usando `%Hostname%%Pathname%`.

## Próximas etapas

[Variáveis](../vars/page-vars/page-variables.md)de página: Saiba quais variáveis de nível de página você pode usar em sua implementação para obter mais das dimensões na Analysis Workspace.

[Variáveis](../vars/config-vars/configuration-variables.md)de configuração: Saiba quais variáveis de configuração você pode usar em sua implementação para desbloquear mais recursos no Adobe Analytics.
