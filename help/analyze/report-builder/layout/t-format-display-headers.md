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

1. Crie uma solicitação no [!UICONTROL Assistente de solicitações: etapa 1].
1. Clique em **[!UICONTROL Próximo]**.
1. No formulário [!UICONTROL Assistente de solicitações: etapa 2], adicione dimensões e métricas à solicitação, conforme desejado.
1. Click **[!UICONTROL Format Options]**.
1. Configure as opções de [!UICONTROL Exibição]:

   | Elemento | Descrição |
   |--- |--- |
   | Nome do relatório | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | Parâmetros de filtros | Exibe os filtros de dimensão, como um filtro de pesquisa. |
   | Segmento | Exibe o parâmetro do segmento. |
   | Recenticidade dos dados | Exibe os parâmetros de recenticidade dos dados. Por exemplo:    Idade dos dados: Exibições de página (há 1,5 h), Saídas (há 30 minutos) Consulte [Opções](/help/analyze/report-builder/options.md) para obter informações sobre o processamento de dados atual. |

   Quanto à ordem de exibição, se a grade [!UICONTROL Rótulo de linha] (na Etapa 2) contiver um item, ela será exibida primeiro na solicitação. Caso contrário, o sistema usará o primeiro item presente na grade [!UICONTROL Rótulo da coluna]. Se não existir nenhum item de linha ou coluna, o primeiro item na grade [!UICONTROL Métricas] será exibido.

   **Exibir cabeçalhos de linha e coluna:** Adiciona uma linha e uma coluna para exibir estes itens.

   Na versão 3.11, você poderia exibir um cabeçalho para cada item. A versão 4 exibe todos esses itens ou nenhum deles. Se você tiver criado uma solicitação na versão 3.11 e abri-la na versão 4.x, o construtor de relatórios solicitará na Etapa 2 a atualização do intervalo adicionando uma célula para itens cujo cabeçalho esteja faltando.

   **Alterar cabeçalhos para filtros automáticos do Excel:** Disponível somente se os cabeçalhos de linha e colunas são exibidos. Esta configuração cria um filtro automático do Excel e o anexa aos dados que o construtor de relatórios retorna para essa solicitação.

   >[!NOTE]
   >
   >O Excel suporta apenas um filtro automático por planilha. Se você criar um novo filtro automático em uma planilha que já tiver um filtro automático, o Excel não apresentará nenhum aviso de que o filtro automático existente será substituído.

   **Executar contorno automático:** Transforma a data retornada pelo construtor de relatórios a partir de uma exibição em lista para uma exibição em árvore.

   **Nomear esta solicitação:** Permite digitar um nome definido pelo usuário para a solicitação ou usar o nome padrão selecionado na etapa 1. Este nome aparece como o nome do [!UICONTROL Relatório] no [!UICONTROL Gerenciador de solicitações]. Consulte [Nomear uma solicitação](/help/analyze/report-builder/layout/name-a-request.md).

1. Clique em **[!UICONTROL OK]**.
