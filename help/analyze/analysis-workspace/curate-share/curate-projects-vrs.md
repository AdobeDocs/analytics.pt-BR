---
title: Preparar projetos e conjuntos de relatórios virtuais
description: Saiba como preparar componentes e projetos de vrs
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Preparar projetos e conjuntos de relatórios virtuais

Ao preparar projetos ou conjuntos de relatórios virtuais (VRSs), você filtra componentes para que seu público-alvo veja somente os componentes (dimensões, métricas, segmentos, intervalos de data) de projeto/VRS que você deseja que eles usem.

>[!Nnota]
>As permissões de componente são o principal mecanismo que rege quais componentes um usuário pode ver. Eles são gerenciados pelas Ferramentas administrativas. A Preparação é um filtro secundário.

Aprimoramos recentemente a experiência de preparação. A seguir encontra-se uma visão geral do que é revelado pelo botão **[!UICONTROL Mostrar tudo], além dos componentes preparados já disponibilizados, em diferentes experiências de preparação e por nível de permissão:**

| Tipo de preparação | Administradores | Proprietários de projeto que não são admistradores | Não administradores |
|---|---|---|---|
| Conjunto de relatórios virtual preparado | Todos os componentes de VRS não preparados | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado | Todos os componentes de projeto não preparados | Todos os componentes de projeto não preparados | Componentes de projeto não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado em um conjunto de relatórios virtual preparado | Todos os componentes não preparados, exibidos em Componentes **[de projeto não preparados e componentes VRS não preparados]** UICONTROL **[UICONTROL]** | Todos os componentes de projeto sem curadoria E componentes VRS sem curadoria que essa função possui ou que foram compartilhados com eles | Componentes de projeto e de VRS não preparados de propriedade desta função ou compartilhados com ela |

>[!IMPORTANT]
>A curadoria do VRS é sempre aplicada antes da curadoria do projeto, de modo que, mesmo se o projeto com curadoria incluir determinados componentes, eles serão filtrados se o VRS com curadoria não os incluir.
