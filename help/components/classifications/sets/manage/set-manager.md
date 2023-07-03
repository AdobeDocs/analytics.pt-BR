---
title: Gerenciador do conjunto de classificações
description: Gerenciar conjuntos de classificações no Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 5%

---

# Gerenciador do conjunto de classificações

O gerenciador de conjuntos de classificações permite criar, editar ou excluir conjuntos de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]**

Os conjuntos de classificações consistem em **Assinaturas** (combinações de conjunto de relatórios e dimensão) e **Nomes de classificação** (dimensões contendo dados de classificação). As assinaturas são configuradas em [Configurações](settings.md), enquanto os nomes de classificação são configurados em [Esquema](schema.md).

## Filtrar conjuntos de classificação

O lado esquerdo do gerenciador de conjuntos de classificações fornece configurações de filtro para localizar o conjunto de classificações desejado. Clicar no ícone de filtro alterna a visibilidade das configurações de filtro. É possível filtrar conjuntos de classificações por **[!UICONTROL Tags]**, **[!UICONTROL Conjunto de relatórios]** ou **[!UICONTROL Proprietário]**.

![Filtros de conjuntos de classificações](../../assets/classification-set-filters.png)

## Colunas do gerenciador de conjuntos de classificações

As seguintes colunas estão disponíveis no Gerenciador de conjuntos de classificações:

* **[!UICONTROL Conjunto de classificações]**: o nome do conjunto de classificações. Clicar no nome de um conjunto de classificações [edita suas configurações](settings.md).
* **[!UICONTROL Assinaturas]**: o número de assinaturas às quais esse conjunto de classificações se aplica.
* **[!UICONTROL Proprietário]**: o proprietário do conjunto de classificações.
* **[!UICONTROL Classificações]**: o número de dimensões de classificação que o conjunto de classificações contém.
* **[!UICONTROL Automatizado]**: determina se o conjunto de classificações está configurado para importar dados automaticamente de um local na nuvem. A automação pode ser configurada no do conjunto de classificações [schema](schema.md).
* **[!UICONTROL Última modificação]**: a data e a hora em que o conjunto de classificações foi modificado pela última vez.

## Criar ou editar opções

Os seguintes botões estão disponíveis no Gerenciador de conjuntos de classificações:

* **[!UICONTROL Adicionar]**: [Criar](create.md) um conjunto de classificações.
* **[!UICONTROL Pesquisar por título]**: pesquise por conjuntos de classificações por nome.
* **[!UICONTROL Carregar mais]**: inicialmente, o gerenciador de conjuntos de classificações exibe até 1000 conjuntos de classificações. Esse botão carrega mais 1000 conjuntos de classificações.
* **Mostrar/Ocultar colunas**: alternar a visibilidade de qualquer coluna além de [!UICONTROL Conjunto de classificações].

Selecione um ou mais conjuntos de classificações clicando na caixa de seleção ao lado do conjunto de classificações desejado. Selecionar um conjunto de classificações revela as seguintes opções:

* **[!UICONTROL Tag]**: adicione uma ou mais tags aos conjuntos de classificações selecionados, o que permite organizar ou agrupar conjuntos de classificações para facilitar a localização no futuro.
* **[!UICONTROL Excluir]**: exclui o conjunto de classificações. As dimensões de classificação baseadas nesse conjunto de classificações não estão mais disponíveis. Os projetos agendados que usam o conjunto de classificações excluído continuam usando dimensões dependentes até que você salve novamente o projeto agendado.
* **[!UICONTROL Consolidar]**: iniciar um novo [consolidação](../consolidations/process.md).
* **[!UICONTROL Renomear]**: renomear o conjunto de classificações selecionado.
