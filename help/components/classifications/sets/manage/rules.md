---
title: Regras do conjunto de classificações
description: Exiba e edite regras para um conjunto de classificações individual.
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Regras do conjunto de classificações

As regras do conjunto de classificações permitem classificar automaticamente valores com base no valor com o qual a variável está definida. Essas regras se aplicam a todos os valores de variável de entrada para todas as assinaturas do conjunto de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > Clique no nome do conjunto de classificações desejado > **[!UICONTROL Regras]**

## Configurações de regra

Configurações que se aplicam a todo o conjunto de regras.

* **[!UICONTROL Substituição de regras]**: determina o comportamento de todas as regras nos casos em que um valor de classificação existe.
   * **[!UICONTROL Aplicar a todos os valores]**: se uma regra corresponder, sempre substitua o valor de classificação.
   * **[!UICONTROL Aplicar somente a valores não definidos]**: se uma regra corresponder, somente escreva o valor de classificação se ele estiver em branco. Se existir um valor de classificação, nada será feito.
* **[!UICONTROL Janela de pesquisa]**: quando essa regra é ativada, todas as regras são executadas em relação a todos os valores únicos vistos na janela de lookback definida aqui.

## Regras

Uma lista de regras que são executadas para cada valor único.

* **[!UICONTROL Pesquisar]**: uma caixa de pesquisa que permite filtrar regras por critérios de correspondência.
* **[!UICONTROL Adicionar regra]**: adiciona uma linha em branco à tabela de regras.
* **[!UICONTROL Testar conjunto de regras]**: traz uma interface de teste que permite validar suas regras. À esquerda, você pode digitar manualmente os valores principais ou arrastar e soltar um arquivo de classificação para importar muitos valores para testar. À direita, há uma tabela que mostra os resultados preliminares de como os valores classificados seriam se o conjunto de regras estivesse ativado. Como essa interface é apenas para validação, nenhum valor é classificado.

Selecione uma ou mais regras clicando na caixa de seleção ao lado da regra desejada. A seleção de uma regra revela as seguintes opções:

* **[!UICONTROL Excluir]**: exclui a linha da tabela de regras.
* **[!UICONTROL Duplicar]**: copia as linhas selecionadas para novas linhas na tabela de regras.

## Tabela de regras

A tabela de regras é separada verticalmente em duas partes principais: condição de correspondência e ação de classificação. Cada linha (uma regra individual) contém uma condição correspondente e uma ação de classificação.

* **Número da regra**: As regras são executadas na mesma ordem em que você configura a tabela de regras. Se [!UICONTROL Substituição de regras] está definida como [!UICONTROL Aplicar a todos os valores], a última regra correspondente substitui todas as regras anteriores para a mesma dimensão de classificação. Se [!UICONTROL Substituição de regras] está definida como [!UICONTROL Aplicar somente a valores não definidos], a primeira regra que define um valor de classificação se aplica.
* **[!UICONTROL Selecionar tipo de regra]**: os critérios da regra. As opções incluem [!UICONTROL Contém], [!UICONTROL Termina com], [!UICONTROL Expressão regular], [!UICONTROL Expressão regular], e [!UICONTROL Começa com].
* **[!UICONTROL Inserir critérios de correspondência]**: a cadeia de caracteres de texto a ser correspondida. Se você selecionar [!UICONTROL Expressão regular] como tipo de regra, é exibida uma sobreposição que permite inserir o valor, testar a expressão regular e fornecer sintaxe de exemplo.
* **[!UICONTROL Definir classificação]**: uma lista suspensa que define a dimensão de classificação à qual você deseja atribuir um valor. As opções válidas incluem elementos na [schema](schema.md).
* **[!UICONTROL Para]**: a cadeia de texto para a qual definir o valor classificado. Se o tipo de regra for [!UICONTROL Expressão regular], você pode incluir uma combinação de texto e grupos de correspondência.
