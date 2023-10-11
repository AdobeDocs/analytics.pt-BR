---
description: A preparação permite limitar os componentes antes de compartilhar um projeto.
keywords: Preparação do Analysis Workspace
title: Preparar projetos do
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 68%

---

# Preparar projetos do

A preparação permite limitar os componentes (dimensões, métricas, segmentos, intervalos de datas) antes de compartilhar um projeto. Quando um recipient abrir o projeto, ele verá um conjunto limitado de componentes que você preparou para eles. A preparação é uma etapa opcional, mas recomendada, antes de compartilhar um projeto.

>[!NOTE]
> Os perfis de produto são o principal mecanismo que controla os componentes que um usuário pode ver. Eles são gerenciados por meio do Adobe Experience Cloud Admin Console. A Preparação é um filtro secundário.

Veja um vídeo sobre seleção e compartilhamento de projetos:

>[!VIDEO](https://video.tv.adobe.com/v/24711/?quality=12)

## Aplicar preparação de projeto

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
Os componentes usados no projeto serão adicionados automaticamente.
   **Observação**: se um projeto tiver vários conjuntos de relatórios, você verá um campo de preparação para cada conjunto de relatórios no projeto.
1. (Opcional) Para adicionar mais componentes, arraste os componentes que deseja compartilhar do painel esquerdo para o campo [!UICONTROL Preparar componentes].
1. Clique em **[!UICONTROL Concluído]**.

A preparação também pode ser aplicada no menu [!UICONTROL Compartilhar] clicando em **[!UICONTROL Preparar e Compartilhar]**. Essa opção organiza automaticamente o projeto para os componentes em uso no projeto. Você pode adicionar outros componentes seguindo as etapas acima.

![](assets/curation-field.png)

## Visualização de projeto preparado

Quando um recipient abrir um projeto preparado, ele verá apenas o conjunto preparado de componentes que você definiu:

![](assets/curate-project.png)

## Remover preparação do projeto

Para remover a preparação do projeto e restaurar o conjunto completo de componentes no painel esquerdo:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
1. Clique em **[!UICONTROL Remover preparação]**.
1. Clique em **[!UICONTROL Concluído]**.

## Curadoria do conjunto de relatórios virtual

Para aplicar curadoria em um nível de conjunto de relatórios, de modo que se aplique a muitos projetos ao mesmo tempo, é possível [preparar componentes em um conjunto de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=pt-BR).

>[!NOTE]
> A preparação do conjunto de relatórios virtual é sempre aplicada antes da preparação do projeto. Isso significa que, mesmo se o projeto preparado incluir determinados componentes, eles serão filtrados se o conjunto de relatórios virtuais preparado não os incluir.

## Opção Mostrar todos os componentes

Em um projeto com curadoria ou conjunto de relatórios virtual, o recipient terá a opção de **[!UICONTROL Mostrar tudo]** componentes no painel esquerdo. [!UICONTROL Mostrar tudo] revela conjuntos diferentes de componentes, dependendo do/da:

* O nível de permissão do usuário (administrador ou não)
* Função do projeto (proprietário/editor ou não)
* Tipo de preparação aplicada (conjuntos de relatórios virtuais ou projeto)
* Componentes pertencentes ao usuário ou compartilhados com ele. Os componentes pertencentes/compartilhados incluem segmentos, métricas calculadas e intervalos de datas. Eles não incluem componentes implementados, como eVars, props e eventos personalizados.

Observação: as funções de visualização que não são de administração não têm acesso ao painel esquerdo em um projeto, por isso, foram omitidas da tabela abaixo.

| Tipo de preparação | Administradores | Proprietário do projeto não administrativo ou função de edição | Função duplicada que não é de administração |
|---|---|---|---|
| Conjunto de relatórios virtuais preparado | Todos os componentes do conjunto de relatórios virtual não preparados | Componentes do conjunto de relatórios virtual não preparados dessa função ou que foram compartilhados com ela | Componentes do conjunto de relatórios virtual não preparados dessa função ou que foram compartilhados com ela |
| Projeto preparado | Todos os componentes de projeto não preparados | Todos os componentes de projeto não preparados | Componentes de projeto não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado em um conjunto de relatórios virtuais preparado | Todos os componentes não preparados, mostrados em **[!UICONTROL Componentes de projeto não preparados]** e **[!UICONTROL Componentes do conjunto de relatórios virtual não preparados]** | Todos os componentes de projeto não preparados E os componentes de conjunto de relatórios virtuais não preparados dessa função ou que foram compartilhados com ela | Componentes de projeto e de conjunto de relatórios virtuais não preparados de propriedade dessa função ou que foram compartilhados com ela |
