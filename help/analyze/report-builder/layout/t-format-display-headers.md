---
description: Você pode dar um nome ao seu relatório e configurar como exibir os cabeçalhos de linhas e colunas. O link Opções de formato está disponível para os tipos de layout dinâmico e personalizado.
seo-description: Você pode dar um nome ao seu relatório e configurar como exibir os cabeçalhos de linhas e colunas. O link Opções de formato está disponível para os tipos de layout dinâmico e personalizado.
seo-title: Formatar cabeçalhos de exibição
solution: Analytics
title: Formatar cabeçalhos de exibição
topic: Construtor de relatórios
uuid: cd 0 e 167 b -9463-43 fd -87 b 2-724 d 1 c 79 de 68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Formatar cabeçalhos de exibição

Você pode dar um nome ao seu relatório e configurar como exibir os cabeçalhos de linhas e colunas. O link Opções de formato está disponível para os tipos de layout dinâmico e personalizado.

1. Crie uma solicitação no [!UICONTROL Assistente de solicitações: etapa 1].
1. Click **[!UICONTROL Next]**.
1. No formulário [!UICONTROL Assistente de solicitações: etapa 2], adicione dimensões e métricas à solicitação, conforme desejado.
1. Click **[!UICONTROL Format Options]**.
1. Configure as opções de [!UICONTROL Exibição]:

   | Elemento | Descrição |
   |--- |--- |
   | Nome do Relatório | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | Parâmetros de filtros | Exibe os filtros de dimensão, como um filtro de pesquisa. |
   | Segmento | Exibe o parâmetro do segmento. |
   | Recenticidade dos dados | Exibe os parâmetros de recenticidade dos dados. Por exemplo:    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   Quanto à ordem de exibição, se a grade [!UICONTROL Rótulo de linha] (na Etapa 2) contiver um item, ela será exibida primeiro na solicitação. Caso contrário, o sistema usará o primeiro item presente na grade [!UICONTROL Rótulo da coluna]. Se não existir nenhum item de linha ou coluna, o primeiro item na grade [!UICONTROL Métricas] será exibido.

   **Exibir cabeçalhos de linha e coluna:** Adiciona uma linha e uma coluna para exibir estes itens.

   Na versão 3.11, você poderia exibir um cabeçalho para cada item. A versão 4 exibe todos esses itens ou nenhum deles. Se você tiver criado uma solicitação na versão 3.11 e abri-la na versão 4.x, o construtor de relatórios solicitará na Etapa 2 a atualização do intervalo adicionando uma célula para itens cujo cabeçalho esteja faltando.

   **Alterar cabeçalhos para filtros automáticos do Excel:** Disponível somente se os cabeçalhos de linha e colunas são exibidos. Esta configuração cria um filtro automático do Excel e o anexa aos dados que o construtor de relatórios retorna para essa solicitação.

   >[!NOTE]
   >
   >O Excel suporta apenas um filtro automático por planilha. Se você criar um novo filtro automático em uma planilha que já tiver um filtro automático, o Excel não apresentará nenhum aviso de que o filtro automático existente será substituído.

   **Executar contorno automático:** Transforma a data retornada pelo construtor de relatórios a partir de uma exibição em lista para uma exibição em árvore.

   **Nomear esta solicitação:** Permite digitar um nome definido pelo usuário para a solicitação ou usar o nome padrão selecionado na etapa 1. Este nome aparece como o nome do [!UICONTROL Relatório] no [!UICONTROL Gerenciador de solicitações]. Consulte [Nomear uma solicitação](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D).

1. Clique em **[!UICONTROL OK]**.
