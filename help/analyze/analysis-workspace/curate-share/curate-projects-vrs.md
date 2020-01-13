---
title: Preparação de projetos e conjuntos de relatórios virtuais (VRS)
description: Saiba como preparar componentes e projetos de conjuntos de relatórios virtuais (VRS)
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Preparação de projetos e conjuntos de relatórios virtuais (VRS)

Ao preparar projetos ou conjuntos de relatórios virtuais (VRSs), você filtra componentes para que seu público-alvo veja somente os componentes (dimensões, métricas, segmentos, intervalos de data) de projeto/VRS que você deseja que eles usem.

>[!Note]
>As permissões de componentes são o principal mecanismo que controla os componentes que um usuário pode ver. São gerenciadas por meio das Ferramentas administrativas. A Preparação é um filtro secundário.

Aprimoramos recentemente a experiência de preparação. Veja a seguir uma visão geral do que é revelado pelo botão **[!UICONTROL Mostrar tudo]**, além dos componentes preparados já disponibilizados, em diferentes experiências de preparação e por nível de permissão:

| Tipo de preparação | Administradores | Proprietários de projeto que não são admistradores | Não administradores |
|---|---|---|---|
| Conjunto de relatórios virtual preparado | Todos os componentes de VRS não preparados | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela | Componentes de VRS não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado | Todos os componentes de projeto não preparados | Todos os componentes de projeto não preparados | Componentes de projeto não preparados de propriedade desta função ou compartilhados com ela |
| Projeto preparado em um conjunto de relatórios virtual preparado | Todos os componentes não preparados, exibidos em  **[UICONTROL Componentes de projeto não preparados]** e **[UICONTROL Componentes de VRS não preparados]** | Todos os componentes de projeto não preparados e os componentes de VRS não preparados dessa função ou que foram compartilhados com ela | Componentes de projeto e de VRS não preparados de propriedade dessa função ou compartilhados com ela |

>[!IMPORTANT]
>A preparação dos conjuntos de relatórios virtuais (VRS) sempre ocorre antes da preparação do projeto. Portanto, mesmo se seu projeto preparado incluir certos componentes, eles serão excluídos caso não estejam incluídos no VRS preparado.
