---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Editar entradas no Dicionário de dados
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 631f84794203cb0a1154d68149c9d64d7247ecd3
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 70%

---

# Editar entradas de componente no dicionário de dados

Os administradores do Analytics podem editar entradas de componentes no Dicionário de dados de um determinado Conjunto de relatórios. Todas as alterações feitas ficam visíveis para todos os usuários do Conjunto de relatórios.

Para editar um componente no Dicionário de dados:

1. Vá para o projeto do Analysis Workspace que contém o componente que deseja editar.

1. Clique no ícone do **Dicionário de dados** no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Visualização do administrador do Dicionário de dados](assets/data-dictionary-admin.png)

1. Verifique se o conjunto de relatórios correto está selecionado no menu suspenso. Por padrão, o conjunto de relatórios em que você já está é exibido.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja editar.

   O tipo de componente pode ser identificado por cor e ícone. **Dimension** ![Ícone Dimension](assets/dimension-icon.png) são laranja, **Segmentos** ![Ícone Segmento](assets/segment-icon.png) são azuis, **Intervalos de datas** ![Ícone de intervalo de datas](assets/date-range-icon.png) são roxas e **Métricas** ![Ícone Métrica](assets/default-metric-icon.png) são verdes. O ícone Adobe ![Ícone Adobe](assets/default-calc-metric-icon.png) indica um modelo de métrica calculada ou um modelo de segmento, e o ícone da calculadora ![Ícone Calculadora](assets/calculated-metric-icon-created.png) indica uma métrica calculada criada por um administrador do Analytics em sua organização.

{{dd-filter-criteria}}

1. (Opcional) Selecione o **Classificar** ícone ![Ícone Classificar componentes](assets/component-sort-icon.png)e selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   {{components-sort-options}}

1. Na lista de componentes, selecione o componente que deseja editar.

1. Clique no ícone de **Editar** ![ícone de Editar Dicionário de dados](assets/data-dictionary-edit-icon.png) ao lado do nome do componente.

1. Edite qualquer uma das seguintes informações sobre o componente:

   {{dd-component-information}}

1. Clique no ícone de **Salvar** ![ícone de Salvar Dicionário de dados](assets/data-dictionary-save-icon.png) para salvar as alterações.
