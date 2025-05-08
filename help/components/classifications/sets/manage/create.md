---
title: Criar um conjunto de classificação
description: Campos e descrições disponíveis ao criar um conjunto de classificações.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 8%

---

# Criar um conjunto de classificação

Você pode usar o Gerenciador de conjuntos de classificações para criar um conjunto de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > **[!UICONTROL Adicionar]**

Ao criar um conjunto de classificações, os seguintes campos estarão disponíveis.

* **[!UICONTROL Nome]**: um campo de texto usado para identificar o conjunto de classificações. Este campo não pode ser editado após a criação, mas pode ser renomeado posteriormente.
* **[!UICONTROL Nome da coluna]**: o nome da primeira dimensão de classificação que você deseja criar. Esse campo é o nome da dimensão usado no Analysis Workspace e o nome da coluna ao exportar os dados de classificação. Você pode adicionar mais nomes de coluna após a criação do conjunto de classificações.
* **[!UICONTROL Tipo]**: botões de opção que indicam o tipo de classificação.
   * **[!UICONTROL Primário]**: aplicar às dimensões coletadas no Analytics. São uma maneira de agrupar (classificar) valores de dimensão granulares em níveis de dados mais significativos. Por exemplo, talvez você queira agrupar palavras-chave de pesquisa interna em categorias de pesquisa interna, para entender melhor os temas em seus dados de pesquisa.
   * **[!UICONTROL Pesquisa]**: comumente chamada de filho ou subclassificações, uma tabela de pesquisa é uma classificação de uma classificação primária. São metadados sobre um valor de classificação, em vez da dimensão original. Por exemplo, a variável Product pode ter uma classificação principal de &#39;Código de cor&#39;. Uma tabela de pesquisa de &quot;Nome da cor&quot; pode ser anexada a &quot;Código de cor&quot; para explicar melhor o que cada código significa.
* **[!UICONTROL Assinaturas]** os conjuntos de relatórios e as dimensões aos quais este conjunto de classificações se aplica. É possível adicionar várias combinações de conjunto de relatórios e dimensões a um conjunto de classificações.

![Criar um conjunto de Classificações](../../assets/classification-set-create.png)

Se um conjunto de classificações existir para um determinado conjunto de relatórios + variável, a classificação é adicionada ao esquema. Uma determinada combinação de conjunto de relatórios + variável não pode pertencer a vários conjuntos de classificação.
