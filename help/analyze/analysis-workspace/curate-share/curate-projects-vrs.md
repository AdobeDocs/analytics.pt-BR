---
title: Preparação de projetos e conjuntos de relatórios virtuais (VRS)
description: Saiba como preparar componentes e projetos de conjuntos de relatórios virtuais (VRS)
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# Preparação de projetos e conjuntos de relatórios virtuais (VRS)

Ao preparar projetos ou conjuntos de relatórios virtuais (VRSs), você filtra componentes para que seu público-alvo veja somente os componentes (dimensões, métricas, segmentos, intervalos de data) de projeto/VRS que você deseja que eles usem.

>[!NOTE]
>
>Os perfis de produto são o principal mecanismo que rege quais componentes um usuário pode ver. They are managed through the [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). A Preparação é um filtro secundário.

Aprimoramos recentemente a experiência de preparação. Veja a seguir uma visão geral do que é revelado pelo botão **[!UICONTROL Mostrar tudo]**, além dos componentes preparados já disponibilizados, em diferentes experiências de preparação e por nível de permissão:

| Tipo de preparação | Administradores | Proprietários de projeto que não são admistradores | Não administradores |
|---|---|---|---|
| Conjunto de relatórios virtual preparado | Todos os componentes de VRS não preparados | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado | Todos os componentes de projeto não preparados | Todos os componentes de projeto não preparados | Componentes de projeto não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado em um conjunto de relatórios virtual preparado | Todos os componentes não preparados, exibidos em  **[!UICONTROL Non-Curated Project Components]**and**[!UICONTROL  Non-Curated VRS Components]** | Todos os componentes de projeto não preparados e os componentes de VRS não preparados dessa função ou que foram compartilhados com ela | Componentes de projeto e de VRS não preparados de propriedade dessa função ou compartilhados com ela |

>[!IMPORTANT]
>
>A curadoria do VRS é sempre aplicada antes da curadoria do projeto. Isso significa que, mesmo se o projeto com curadoria incluir determinados componentes, eles serão filtrados se o VRS com curadoria não os incluir.
