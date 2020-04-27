---
description: Você pode dar um nome ao seu relatório e configurar como exibir os cabeçalhos de linhas e colunas. O link Opções de formato está disponível para os tipos de layout dinâmico e personalizado.
title: Formatar cabeçalhos de exibição
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Formatar cabeçalhos de exibição

Você pode dar um nome ao seu relatório e configurar como exibir os cabeçalhos de linhas e colunas. O link Opções de formato está disponível para os tipos de layout dinâmico e personalizado.

1. Crie uma solicitação no [!UICONTROL Request Wizard: Step 1].
1. Clique em **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. Clique em **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | Elemento | Descrição |
   |--- |--- |
   | Nome do relatório | Exibe o nome do tipo de relatório selecionado na árvore no Assistente de solicitações: Etapa 1 (por exemplo, [!DNL Traffic Report]), ou o nome digitado no campo [!DNL Name this Request]. |
   | Parâmetros de filtros | Exibe os filtros de dimensão, como um filtro de pesquisa. |
   | Segmento | Exibe o parâmetro do segmento. |
   | Recenticidade dos dados | Exibe os parâmetros de recenticidade dos dados. Por exemplo:    Recenticidade dos dados: Exibições de página (há 1,5 h), Saídas (há 30 minutos) Consulte [Opções](/help/analyze/report-builder/options.md) para obter informações sobre o processamento de dados atual. |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **Exibir cabeçalhos de linha e coluna:** Adiciona uma linha e uma coluna para exibir estes itens.

   Na versão 3.11, você poderia exibir um cabeçalho para cada item. A versão 4 exibe todos esses itens ou nenhum deles. Se você tiver criado uma solicitação na versão 3.11 e abri-la na versão 4.x, o Report Builder solicitará na Etapa 2 a atualização do intervalo adicionando uma célula para itens cujo cabeçalho esteja faltando.

   **Alterar cabeçalhos para filtros automáticos do Excel:** Disponível somente se os cabeçalhos de linha e colunas são exibidos. Esta configuração cria um filtro automático do Excel e o anexa aos dados que o Report Builder retorna para essa solicitação.

   >[!NOTE]
   >
   >O Excel oferece suporte somente a um filtro automático por planilha. Se você criar um novo filtro automático em uma planilha que já tiver um filtro automático, o Excel não apresentará nenhum aviso de que o filtro automático existente será substituído.

   **Executar contorno automático:** Transforma a data retornada pelo Report Builder a partir de uma exibição em lista para uma exibição em árvore.

   **Nomear esta solicitação:** Permite digitar um nome definido pelo usuário para a solicitação ou usar o nome padrão selecionado na etapa 1. Esse nome aparece como o [!UICONTROL Report] nome no [!UICONTROL Request Manager]. See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. Clique em **[!UICONTROL OK]**.
