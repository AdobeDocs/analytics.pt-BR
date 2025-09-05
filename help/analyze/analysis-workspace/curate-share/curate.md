---
description: Saiba como preparar projetos no Analysis Workspace. A preparação limita o acesso a componentes antes de você compartilhar um projeto.
keywords: Preparação do Analysis Workspace
title: Preparar projetos
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 80%

---

# Preparar projetos do

A preparação permite limitar os componentes (dimensões, métricas, segmentos, intervalos de datas) antes de compartilhar um projeto. Ao abrir o projeto, o destinatário verá um conjunto limitado de componentes que você preparou. A preparação é uma etapa opcional, mas recomendada, antes de compartilhar um projeto.

>[!NOTE]
> Os perfis de produto são o principal mecanismo que controla os componentes que um usuário pode ver. Eles são gerenciados por meio do Adobe Experience Cloud Admin Console. A Preparação é um filtro secundário.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Preparar projetos](https://video.tv.adobe.com/v/24711?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Aplicar preparação de projeto

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
Os componentes usados no projeto serão adicionados automaticamente.
Se um projeto tiver vários conjuntos de relatórios, você verá um destino de preparação para cada conjunto de relatórios no projeto.
1. (Opcional) Para adicionar outros componentes, arraste os que deseja compartilhar do painel esquerdo até a zona de destino **[!UICONTROL Preparar componentes]** da visualização de dados.
1. Selecione **[!UICONTROL Concluído]**. 


![](assets/curation-field.png)

Ao abrir um projeto preparado, o destinatário verá apenas o conjunto preparado de componentes que você definiu:


## Remover preparação do projeto

Para remover a preparação do projeto e restaurar o conjunto completo de componentes no painel esquerdo:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
1. Clique em **[!UICONTROL Remover preparação]**.
1. Selecione **[!UICONTROL Concluído]**. 

## Preparação de conjunto de relatórios virtuais

Para fazer a preparação no nível do conjunto de relatórios, de modo que ela se aplique a vários projetos de uma vez, você pode [preparar os componentes em um conjunto de relatórios virtuais](/help/components/vrs/vrs-components.md).

>[!NOTE]
>
> A preparação do conjunto de relatórios virtuais é sempre aplicada antes da preparação do projeto. Mesmo que seu projeto preparado inclua determinados componentes, eles serão filtrados se o conjunto de relatórios virtuais preparado não incluir esses componentes.
> 

## Opções de preparação de componentes

Em um projeto com curadoria ou conjunto de relatórios virtual, o recipient tem a opção de **[!UICONTROL Mostrar todos]** componentes no painel esquerdo. [!UICONTROL Mostrar tudo] revela conjuntos diferentes de componentes, dependendo dos seguintes fatores:

* O nível de permissão do usuário (administrador ou não)
* Função do projeto (proprietário/editor ou não)
* Tipo de preparação aplicada (conjuntos de relatórios virtuais ou projeto)
* Componentes pertencentes ao usuário ou compartilhados com ele. Os componentes pertencentes/compartilhados incluem segmentos, métricas calculadas e intervalos de datas. Eles não incluem componentes implementados, como eVars, props e eventos personalizados.

Observação: as funções de visualização que não são de administração não têm acesso ao painel esquerdo em um projeto, por isso, foram omitidas da tabela abaixo.

| Tipo de preparação | Administradores | Proprietário do projeto não administrativo ou função de edição | Função duplicada que não é de administração |
|---|---|---|---|
| **Conjunto de relatórios virtuais preparado** | Todos os componentes do conjunto de relatórios virtual não preparado | Componentes do conjunto de relatórios virtuais não preparado que esta função possui ou que foram compartilhados com ela | Componentes do conjunto de relatórios virtuais não preparado que esta função possui ou que foram compartilhados com ela |
| **Projeto preparado** | Todos os componentes de projeto não preparados | Todos os componentes de projeto não preparados | Componentes de projeto não preparados de propriedade desta função ou compartilhados com ela |
| **Projeto preparado em um conjunto de relatórios virtuais preparado** | Todos os componentes não preparados, mostrados em **[!UICONTROL Componentes de projetos não preparados]** e **[!UICONTROL Componentes de conjuntos de relatórios virtuais não preparados]** | Todos os componentes de projetos não preparados E componentes do conjunto de relatórios virtuais não preparado que esta função possui ou que foram compartilhados com ela | Conjunto de relatórios virtuais e componentes de projetos não preparados que esta função possui ou que foram compartilhados com ela |
