---
title: Regras do conjunto de classificação
description: Exiba e edite regras para um conjunto de classificações individual.
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
source-git-commit: de12253f6db798f49d0cae34bf9cb6b7a3de17db
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 1%

---

# Regras do conjunto de classificação

As regras do conjunto de classificações permitem classificar automaticamente valores com base no valor com o qual a variável está definida. Essas regras se aplicam a todos os valores de variável de entrada para todas as assinaturas do conjunto de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > Clique no nome do conjunto de classificações desejado > **[!UICONTROL Regras]**

![interface do usuário de regras do conjunto de classificações](../../assets/csets-rules.png)

## Configurações de regra

Configurações que se aplicam a todo o conjunto de regras.

* **[!UICONTROL Substituição de regras]**: determina o comportamento de todas as regras nos casos em que existe um valor de classificação.
   * **[!UICONTROL Aplicar a todos os valores]**: se uma regra corresponder, sempre substitua o valor de classificação.
   * **[!UICONTROL Aplicar apenas a valores não definidos]**: se uma regra corresponder, gravar apenas o valor de classificação se ele estiver em branco. Se existir um valor de classificação, nada será feito.
* **[!UICONTROL Janela de retrospectiva]**: quando esta regra é ativada, todas as regras são executadas em relação a todos os valores únicos vistos na janela de retrospectiva definida aqui.

## Regras

Uma lista de regras que são executadas para cada valor único.

* **[!UICONTROL Pesquisa]**: uma caixa de pesquisa que permite filtrar regras por critérios de correspondência.
* **[!UICONTROL Adicionar regra]**: adiciona uma linha em branco à tabela de regras.
* **[!UICONTROL Conjunto de regras de teste]**: traz uma interface de teste que permite validar suas regras. À esquerda, você pode digitar manualmente os valores principais ou arrastar e soltar um arquivo de classificação para importar muitos valores para testar. À direita, há uma tabela que mostra os resultados preliminares de como os valores classificados seriam se o conjunto de regras estivesse ativado. Como essa interface é apenas para validação, nenhum valor é classificado.

Selecione uma ou mais regras clicando na caixa de seleção ao lado da regra desejada. A seleção de uma regra revela as seguintes opções:

* **[!UICONTROL Excluir]**: exclui a linha da tabela de regras.
* **[!UICONTROL Duplicar]**: copia as linhas selecionadas para as novas linhas na tabela de regras.

## Tabela de regras

A tabela de regras é separada verticalmente em duas partes principais: condição de correspondência e ação de classificação. Cada linha (uma regra individual) contém uma condição correspondente e uma ação de classificação.

* **Número da regra**: as regras são executadas na mesma ordem em que você configura a tabela de regras. Se [!UICONTROL Substituição de regras] estiver definido como [!UICONTROL Aplicar a todos os valores], a última regra correspondente substituirá todas as regras anteriores para a mesma dimensão de classificação. Se [!UICONTROL Substituição de regras] estiver definido como [!UICONTROL Aplicar somente a valores não definidos], a primeira regra que define um valor de classificação será aplicada.
* **[!UICONTROL Selecionar tipo de regra]**: os critérios da regra. As opções incluem [!UICONTROL Contém], [!UICONTROL Termina com], [!UICONTROL Expressão regular], [!UICONTROL Expressão regular] e [!UICONTROL Começa com].
* **[!UICONTROL Insira os critérios de correspondência]**: a cadeia de texto a ser correspondida. Se você selecionar [!UICONTROL Expressão regular] como o tipo de regra, uma sobreposição será exibida para permitir que você insira o valor, teste a expressão regular e forneça uma sintaxe de exemplo.
* **[!UICONTROL Definir classificação]**: uma lista suspensa que define a dimensão de classificação à qual você deseja atribuir um valor. As opções válidas incluem elementos no [esquema](schema.md).
* **[!UICONTROL Para]**: a cadeia de texto para a qual definir o valor classificado. Se o tipo de regra for [!UICONTROL Expressão regular], você poderá incluir uma combinação de texto e grupos de correspondência.
