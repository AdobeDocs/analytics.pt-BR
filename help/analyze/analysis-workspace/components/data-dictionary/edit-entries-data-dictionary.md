---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Editar entradas no Dicionário de dados
feature: Components
role: Admin
source-git-commit: 7e105b4cd22187411dedd663080703e6daec91f5
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Editar entradas de componente no dicionário de dados

{{release-limited-testing}}

Os administradores do Analytics podem editar entradas de componentes no Dicionário de dados de um determinado Conjunto de relatórios. Todas as alterações feitas ficam visíveis para todos os usuários do Conjunto de relatórios.

Para editar um componente no Dicionário de dados:

1. Vá para o projeto do Analysis Workspace que contém o componente que deseja editar.

1. Clique no ícone do **Dicionário de dados** no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Visualização do administrador do Dicionário de dados](assets/data-dictionary-admin.png)

1. Verifique se o conjunto de relatórios correto está selecionado no menu suspenso. Por padrão, o conjunto de relatórios em que você já está é exibido.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja editar.

   Os ícones são exibidos ao lado dos nomes dos componentes para indicar o tipo de componente:

   | Ícone | Significado |
   |---------|----------|
   | ![Ícone Dimension](assets/dimension-icon.png) | Indica um **dimension**. Dimension são fornecidas por Adobe. As dimensões existentes não podem ser modificadas e não é possível criar novas dimensões. |
   | ![Ícone Métrica](assets/default-metric-icon.png) | Indica um **métrica padrão** (não calculado). As métricas padrão são fornecidas pelo Adobe e não podem ser modificadas. |
   | ![Ícone Adobe](assets/default-calc-metric-icon.png) | Indica um **modelo de métrica calculada** ou **modelo de segmento**. Esses componentes são fornecidos pelo Adobe e não podem ser modificados. |
   | ![Ícone Calculadora](assets/calculated-metric-icon-created.png) | Indica um **métrica calculada** criado por um administrador do Analytics em sua organização. |
   | ![Ícone de segmento](assets/segment-icon.png) | Indica um **segmento**. Esses podem ser segmentos fornecidos pelo Adobe ou criados por um administrador do Analytics em sua organização. |
   | ![Ícone de intervalo de datas](assets/date-range-icon.png) | Indica um **intervalo de datas**. Podem ser intervalos de datas fornecidos pelo Adobe ou criados por um administrador do Analytics em sua organização. |

{{dd-filter-criteria}}

1. Na lista de componentes, selecione o componente que deseja editar.

1. Clique no ícone de **Editar** ![ícone de Editar Dicionário de dados](assets/data-dictionary-edit-icon.png) ao lado do nome do componente.

1. Edite qualquer uma das seguintes informações sobre o componente:

   {{dd-component-information}}

1. Clique no ícone de **Salvar** ![ícone de Salvar Dicionário de dados](assets/data-dictionary-save-icon.png) para salvar as alterações.
