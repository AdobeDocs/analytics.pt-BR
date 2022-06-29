---
title: Criar um conjunto de classificações
description: Campos e descrições disponíveis ao criar um Conjunto de classificações.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Criar um conjunto de classificações

Você pode usar o Gerenciador do conjunto de classificações para criar um Conjunto de classificações.

>[!NOTE]
>
>Este recurso está atualmente em versão limitada. Se você quiser acessar esse recurso, entre em contato com o Atendimento ao cliente do Adobe ou com o Gerente de conta, que pode encaminhar sua solicitação para o provisionamento da equipe de Classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > **[!UICONTROL Adicionar]**

Ao criar um Conjunto de classificações, os seguintes campos ficam disponíveis.

* **[!UICONTROL Nome]**: Um campo de texto usado para identificar o Conjunto de Classificações. Este campo não pode ser editado após a criação, mas pode ser renomeado posteriormente.
* **[!UICONTROL Nome da coluna]**: O nome da dimensão de classificação que deseja criar. Esse campo é o nome da dimensão usado no Analysis Workspace e o nome da coluna ao exportar dados de classificação.
* **[!UICONTROL Tipo]**: Botões de opção que indicam o tipo de classificação. As classificações primárias são normalmente utilizadas; As classificações de pesquisa representam [Subclassificações](../c-sub-classifications.md).
* **[!UICONTROL Subscrições]** O Conjunto de relatórios e a dimensão à qual esse Conjunto de classificações se aplica. O suporte para vários conjuntos de relatórios está planejado.

![Criar um conjunto de classificações](../assets/classification-set-create.png)

Se um Conjunto de classificações existir para um determinado Conjunto de relatórios + variável, a Classificação é adicionada ao esquema.
