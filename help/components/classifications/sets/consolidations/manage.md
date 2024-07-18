---
title: Gerenciador de consolidação do conjunto de classificação
description: Consolidar um ou mais conjuntos de classificações em um único conjunto de classificações.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# Gerenciador de consolidações do conjunto de classificação

Se você tiver vários conjuntos de classificações que contenham dados semelhantes, é possível consolidá-los em um único conjunto de classificações. Ao consolidar dois ou mais conjuntos de classificações, o Adobe gera um novo conjunto de classificações que contém todos os dados de classificação de cada conjunto de classificações individual. As consolidações são úteis quando você carrega dados em vários conjuntos de relatórios ou dimensões que contêm os mesmos dados de classificação e deseja mesclá-los em um único fluxo de trabalho. É necessário ter acesso de administrador de produto para que o Adobe Analytics veja o gerenciador de consolidação do conjunto de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Consolidações]**

Depois que uma consolidação é executada, os conjuntos de classificações originais são removidos e o conjunto de classificações consolidadas ocupa seu lugar. Clique em **[!UICONTROL Adicionar]** a [Criar uma consolidação](process.md).

## Filtrar conjuntos de classificação

O lado esquerdo do gerenciador de consolidação do conjunto de classificações fornece configurações de filtro para localizar a consolidação desejada. Clicar no ícone de filtro alterna a visibilidade das configurações de filtro. Você pode filtrar consolidações por **[!UICONTROL Status]**, **[!UICONTROL Hora de conclusão]** ou **[!UICONTROL Hora de criação]**.

![Filtros de consolidação do conjunto de classificações](../../assets/classification-set-consolidation-filters.png)

Opções de filtro adicionais estão disponíveis acima das colunas do gerenciador de consolidação do conjunto de classificações:

* **[!UICONTROL Pesquisar por título]**: pesquisar consolidações por nome.
* **Mostrar/Ocultar colunas**: alternar visibilidade de qualquer coluna além de [!UICONTROL Nome].

## Colunas do gerenciador de consolidação do conjunto de classificações

As seguintes colunas estão disponíveis no gerenciador de consolidação do conjunto de classificações:

* **[!UICONTROL Nome]**: o nome da consolidação.
* **[!UICONTROL Trabalho atual]**: o trabalho atual. <!-- todo: better description -->
* **[!UICONTROL Status]**: o status da consolidação. <!-- todo: get list of possible statuses -->
* **[!UICONTROL Data de criação]**: a data e a hora em que a consolidação foi criada.
* **[!UICONTROL Data de conclusão]**: a data e a hora em que a consolidação foi concluída (ou falhou).
