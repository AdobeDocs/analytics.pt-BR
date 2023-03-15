---
description: 'O Report Builder 5.2 é compatível com as métricas calculadas unificadas do Adobe Analytics. Entre outra inovações, todas as métricas calculadas agora contam com uma ID global: elas não ficam mais restritas a um único conjunto de relatórios.'
title: Métricas calculadas
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 100%

---

# Métricas calculadas

O Report Builder 5.2 é compatível com as métricas calculadas unificadas do Adobe Analytics. Entre outra inovações, todas as métricas calculadas agora contam com uma ID global: elas não ficam mais restritas a um único conjunto de relatórios.

>[!NOTE]
>
>As pastas de trabalho atuais talvez indiquem solicitações com as IDs da métrica herdada. Ao usar o Report Builder 5.2, essas IDs da métrica herdada serão convertidas para a nova ID global. Se você compartilhar essa pasta de trabalho com um usuário do Report Builder v5.1 ou anterior, ele não conseguirá visualizar as métricas calculadas.

Para saber mais sobre como criar e gerenciar métricas calculadas com o novo Construtor e gerenciador de métricas calculadas, consulte o Guia de [Métricas Calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=pt-BR).

Na etapa 2 do Assistente de solicitação, você pode filtrar e aplicar as métricas calculadas.

## Filtrar métricas calculadas {#section_376E986D3E684999A7CDB08E53854159}

Para **filtrar** as métricas calculadas, clique no ícone Filtrar:  ![](/help/admin/admin/assets/filter.png)

. A caixa de diálogo Filtros avançados é preenchida com as métricas padrão e calculadas.

Os filtros disponíveis incluem:

![](assets/advanced_filters.png)

| Nome do filtro | Descrição |
|---|---|
| Tags | Permite aplicar os filtros nas métricas calculadas com tags específicas. Observe que os filtros de tags usam o operador AND. Caso você verifique as duas tags, o painel direito mostrará as métricas que foram marcadas com **ambas** as tags. |
| Conjuntos de relatórios | Se você aplicar o filtro &quot;Somente o *nome do conjunto de relatórios*&quot; no Construtor de métricas calculadas em [!DNL Reports & Analytics] e, em seguida, exibir o filtro Avançado no [!DNL Report Builder], o filtro Avançado exibirá as métricas calculadas somente para o conjunto de relatórios selecionados. |
| Proprietários | Permite que filtrar métricas por proprietário. Observe que os filtros Proprietários usam o operador OR. Se você marcar dois proprietários, o painel direito exibe as métricas de propriedade de **qualquer** proprietário. |
| Outros filtros > Aprovado | Mostra todos os segmentos  métricas aprovadas. |
| Outros filtros > Favoritos | Mostra todas as métricas que você marcou como Favoritos. |
| Outros filtros > Meus | Mostra todas as suas métricas. |
| Outros filtros > Compartilhados comigo | Mostra todas as métricas que outras pessoas compartilharam com você. |

## Aplicação de métricas calculadas {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Após selecionar os filtros, clique em **[!UICONTROL Aplicar]** para aplicá-las à solicitação. As métricas selecionadas serão adicionadas ao layout do relatório.

![](assets/filtering_for_metric.png)
