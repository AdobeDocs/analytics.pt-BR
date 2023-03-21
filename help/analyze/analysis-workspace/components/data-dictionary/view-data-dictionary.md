---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Exibir o dicionário de dados
feature: Components
role: User, Admin
source-git-commit: 5d83d2621ee5eee7dbbc2af3793a9e1d3de0f97b
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 58%

---

# Exibir informações de componente no dicionário de dados

{{release-limited-testing}}

O Dicionário de dados permite visualizar informações sobre um componente, incluindo a descrição do componente, componentes semelhantes, outros componentes com os quais um componente é usado com frequência e muito mais.

Para exibir informações sobre um componente no Dicionário de dados:

1. Acesse o projeto do Analysis Workspace que contém o componente que deseja visualizar.

1. Clique no ícone do [!UICONTROL **Dicionário de dados**] no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Verifique se o Conjunto de relatórios que contém o componente que você deseja visualizar está selecionado no menu suspenso. Por padrão, o conjunto de relatórios em que você já está é exibido.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja visualizar.

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

1. Na lista de componentes, selecione o componente que deseja visualizar.

   As seguintes informações sobre o componente são exibidas:

   {{dd-component-information}}

1. (Opcional) Arraste um componente do Dicionário de dados para o Analysis Workspace.