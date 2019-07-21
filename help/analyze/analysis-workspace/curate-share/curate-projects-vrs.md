---
title: Preparar projetos e conjuntos de relatórios virtuais
seo-title: Preparar projetos e conjuntos de relatórios virtuais na Analysis Workspace
description: Saiba como preparar componentes e projetos vrs
seo-description: Preparar VRS e preparar projetos
translation-type: tm+mt
source-git-commit: 0b56838e966aaf4cfa5c2685dd8335adbbbf11a7

---


# Preparar projetos e conjuntos de relatórios virtuais

Ao preparar projetos ou conjuntos de relatórios virtuais (VRSs), você filtra componentes para que seu público-alvo veja somente os componentes (dimensões, métricas, segmentos, intervalos de data) de projeto/VRS que você deseja que eles usem.

>[!Note]
>As permissões de componentes são o mecanismo principal que rege os componentes que um usuário pode visualizar. Elas são gerenciadas por meio das Ferramentas administrativas. A Preparação é um filtro secundário.

Aprimoramos recentemente a experiência de preparação. A seguir encontra-se uma visão geral do que é revelado pelo botão **[!UICONTROL Mostrar tudo], além dos componentes preparados já disponibilizados, em diferentes experiências de preparação e por nível de permissão:**

| Tipo de preparação | Administradores | Proprietários de projeto que não são admistradores | Não administradores |
|---|---|---|---|
| Conjunto de relatórios virtual preparado | Todos os componentes de VRS não preparados | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado | Todos os componentes de projeto não preparados | Todos os componentes de projeto não preparados | Componentes de projeto não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado em um conjunto de relatórios virtual preparado | Todos os componentes não preparados, exibidos em **[Componentes do projeto não preparados do UICONTROL]** e **[componentes VRS não preparados do UICONTROL]** | Todos os componentes de projeto não preparados e componentes VRS não preparados que essa função possui ou que foram compartilhados com eles | Componentes de projeto e de VRS não preparados de propriedade desta função ou compartilhados com ela |

>[!IMPORTANT]
>A curadoria de VRS é sempre aplicada antes da curadoria do projeto; portanto, mesmo se o projeto preparado incluir alguns componentes, eles serão filtrados se o VRS preparado não incluí-los.
