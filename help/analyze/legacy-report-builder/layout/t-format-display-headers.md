---
description: Saiba como nomear seu relatório e configurar como exibir cabeçalhos de linha e coluna.
title: Como formatar cabeçalhos de exibição
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
TQID: https://experienceleague.adobe.com/n9LlAH6wZ87xQTOO7SLYSpKudcHxuqqielFv6hJXAYw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 61%

---

# Formatar cabeçalhos de exibição

{{legacy-arb}}

Você pode dar um nome ao seu relatório e configurar como exibir os cabeçalhos de linhas e colunas. O link Opções de Formato está disponível para os tipos de Layout Dinâmico e Personalizado.

1. Crie uma solicitação no [!UICONTROL Assistente de solicitações: etapa 1].
1. Clique em **[!UICONTROL Próximo]**.
1. No formulário [!UICONTROL Assistente de solicitações: etapa 2], adicione dimensões e métricas à solicitação, conforme desejado.
1. Clique em **[!UICONTROL Opções de Formato]**.
1. Configure as opções de [!UICONTROL Exibição]:

   | Elemento | Descrição |
   |--- |--- |
   | Nome do relatório | Exibe o nome do tipo de relatório selecionado na árvore no Assistente de solicitações: Etapa 1 (por exemplo, [!DNL Traffic Report]), ou o nome digitado no campo [!DNL Name this Request]. |
   | Parâmetros de filtros | Exibe os filtros de dimensão, como um filtro de pesquisa. |
   | Segmento | Exibe o parâmetro do segmento. |
   | Recenticidade dos dados | Exibe os parâmetros de recenticidade dos dados. Por exemplo: Recenticidade dos dados: Exibições de página (há 1,5 h), Saídas (há 30 minutos) Consulte [Opções](/help/analyze/legacy-report-builder/options.md) para obter informações sobre o processamento de dados atual. |

   Quanto à ordem de exibição, se a grade [!UICONTROL Rótulo de linha] (na Etapa 2) contiver um item, ela será exibida primeiro na solicitação. Caso contrário, o sistema usará o primeiro item presente na grade [!UICONTROL Rótulo da coluna]. Se não existirem itens de linha ou coluna, o primeiro item na grade [!UICONTROL Métricas] será exibido.

   **Exibir cabeçalhos de linha e coluna:** Adiciona uma linha e uma coluna para exibir estes itens.

   Na versão 3.11, você podia exibir um cabeçalho para cada item. A versão 4 exibe todos esses itens ou nenhum deles. Se você tiver criado uma solicitação na versão 3.11 e abri-la na versão 4.x, o Report Builder solicitará na Etapa 2 a atualização do intervalo por uma célula para itens cujo cabeçalho esteja faltando.

   **Alterar cabeçalhos para filtros automáticos do Excel:** Disponível somente se os cabeçalhos de linha e colunas são exibidos. Essa configuração cria um filtro automático do Excel e o anexa aos dados que o Report Builder retorna para essa solicitação.

   >[!NOTE]
   >
   >O Excel oferece suporte somente a um filtro automático por planilha. Se você criar um novo filtro automático em uma planilha que já tiver um filtro automático, o Excel não apresentará nenhum aviso de que o filtro automático existente será substituído.

   **Executar contorno automático:** Transforma a data retornada pelo Report Builder de um modo de exibição de lista em um modo de exibição de árvore.

   **Nomear esta solicitação:** Permite digitar um nome definido pelo usuário para a solicitação ou usar o nome padrão selecionado na etapa 1. Este nome aparece como o nome do [!UICONTROL Relatório] no [!UICONTROL Gerenciador de solicitações]. Consulte [Nomear uma Solicitação](/help/analyze/legacy-report-builder/layout/name-a-request.md).

1. Clique em **[!UICONTROL OK]**.
