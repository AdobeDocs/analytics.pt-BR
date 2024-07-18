---
title: Gerenciador de conjuntos de classificação
description: Gerenciar conjuntos de classificações no Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: 2b81c0df0e2bb68a73f9d24888758a433c6f5423
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 7%

---

# Gerenciador de conjuntos de classificação

O gerenciador de conjuntos de classificações permite criar, editar ou excluir conjuntos de classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]**

Os conjuntos de classificações consistem em **Assinaturas** (combinações de conjunto de relatórios e dimensão) e **Nomes de classificação** (dimensões contendo dados de classificação). As assinaturas estão configuradas em [Configurações](settings.md), enquanto os nomes de classificação estão configurados em [Esquema](schema.md).

## Filtrar conjuntos de classificação

O lado esquerdo do gerenciador de conjuntos de classificações fornece configurações de filtro para localizar o conjunto de classificações desejado. Clicar no ícone de filtro alterna a visibilidade das configurações de filtro. Você pode filtrar conjuntos de classificações por **[!UICONTROL Marcas]** ou **[!UICONTROL Conjunto de relatórios]**.

![Filtros de conjuntos de classificações](../../assets/classification-set-filters.png)

## Colunas do gerenciador de conjuntos de classificações

As seguintes colunas estão disponíveis no Gerenciador de conjuntos de classificações:

* **[!UICONTROL Conjunto de classificações]**: o nome do conjunto de classificações. Clicar em um nome de conjunto de classificações [edita suas configurações](settings.md).
* **[!UICONTROL Assinaturas]**: o número de assinaturas às quais este conjunto de classificações se aplica.
* **[!UICONTROL Classificações]**: o número de dimensões de classificação que o conjunto de classificações contém.
* **[!UICONTROL Automatizado]**: determina se o conjunto de classificações está configurado para importar dados automaticamente de um local na nuvem. A automação pode ser configurada no [esquema](schema.md) do conjunto de classificações.
* **[!UICONTROL Última modificação]**: a data e a hora em que o conjunto de classificações foi modificado pela última vez.

## Criar ou editar opções

Os seguintes botões estão disponíveis no Gerenciador de conjuntos de classificações:

* **[!UICONTROL Adicionar]**: [Criar](create.md) um conjunto de classificações.
* **[!UICONTROL Pesquisar por título]**: pesquisar conjuntos de classificações por nome.
* **[!UICONTROL Carregar mais]**: inicialmente, o gerenciador de conjuntos de classificações exibe até 1000 conjuntos de classificações. Esse botão carrega mais 1000 conjuntos de classificações.
* **Mostrar/Ocultar colunas**: alternar a visibilidade de qualquer coluna além do [!UICONTROL Conjunto de classificações].

Selecione um ou mais conjuntos de classificações clicando na caixa de seleção ao lado do conjunto de classificações desejado. Selecionar um conjunto de classificações revela as seguintes opções:

* **[!UICONTROL Marca]**: adicione uma ou mais marcas aos conjuntos de classificações selecionados, o que permite organizar ou agrupar conjuntos de classificações para facilitar a localização no futuro.
* **[!UICONTROL Excluir]**: exclui o conjunto de classificações. As dimensões de classificação baseadas nesse conjunto de classificações não estão mais disponíveis. Os projetos agendados que usam o conjunto de classificações excluído continuam usando dimensões dependentes até que você salve novamente o projeto agendado.
* **[!UICONTROL Consolidar]**: iniciar uma nova [consolidação](../consolidations/process.md).
* **[!UICONTROL Renomear]**: renomear o conjunto de classificações selecionado.
