---
title: Criar um conjunto de classificações
description: Campos e descrições disponíveis ao criar um conjunto de classificações.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 100%

---

# Criar um conjunto de classificações

Você pode usar o Gerenciador de conjuntos de classificações para criar um conjunto de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > **[!UICONTROL Adicionar]**

Ao criar um conjunto de classificações, os seguintes campos estarão disponíveis.

* **[!UICONTROL Nome]**: um campo de texto usado para identificar o conjunto de Classificações. Este campo não pode ser editado após a criação, mas pode ser renomeado posteriormente.
* **[!UICONTROL Nome da coluna]**: o nome da dimensão de classificação que você deseja criar. Esse campo é o nome da dimensão usado no Analysis Workspace e o nome da coluna ao exportar os dados de classificação.
* **[!UICONTROL Tipo]**: botões de opção que indicam o tipo de classificação. As classificações primárias são normalmente utilizadas; as classificações de pesquisa representam [Subclassificações](../c-sub-classifications.md).
* **[!UICONTROL Assinaturas]**: o conjunto de relatórios e a dimensão à qual esse conjunto de classificações se aplica. A compatibilidade com vários conjuntos de relatórios está planejada.

![Criar um conjunto de classificações](../assets/classification-set-create.png).

Se um conjunto de classificações existir para um determinado conjunto de relatórios + variável, a classificação é adicionada ao esquema.
