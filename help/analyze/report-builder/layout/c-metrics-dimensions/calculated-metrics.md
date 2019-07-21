---
description: 'O Construtor de relatórios 5.2 é compatível com as métricas calculadas unificadas do Adobe Analytics. Entre outra inovações, todas as métricas calculadas agora contam com uma ID global: elas não ficam mais restritas a um único conjunto de relatórios.'
seo-description: 'O Construtor de relatórios 5.2 é compatível com as métricas calculadas unificadas do Adobe Analytics. Entre outra inovações, todas as métricas calculadas agora contam com uma ID global: elas não ficam mais restritas a um único conjunto de relatórios.'
seo-title: Métricas calculadas
title: Métricas calculadas
uuid: c 9814894-cda 6-40 ff -8 ec 4-3 ab 2 c 1908 ebc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métricas calculadas

O Construtor de relatórios 5.2 é compatível com as métricas calculadas unificadas do Adobe Analytics. Entre outra inovações, todas as métricas calculadas agora contam com uma ID global: elas não ficam mais restritas a um único conjunto de relatórios.

>[!NOTE]
>
>Pastas de trabalho existentes podem apontar para solicitações com IDs de métricas herdadas. Ao usar o Construtor de relatórios 5.2, essas IDs da métrica herdada serão convertidas para a nova ID global. Se você compartilhar essa pasta de trabalho com um usuário do Construtor de relatórios v5.1 ou anterior, ele não conseguirá visualizar as métricas calculadas.

Para saber mais sobre como criar e gerenciar métricas calculadas com o novo Construtor e gerenciador de métricas calculadas, consulte o Guia de [Métricas Calculadas](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics).

Na etapa 2 do Assistente de solicitação, você pode filtrar e aplicar as métricas calculadas.

## Filtrar métricas calculadas {#section_376E986D3E684999A7CDB08E53854159}

Para **filtrar** as métricas calculadas, clique no ícone Filtrar:  ![](assets/segment_filter.png)

. A caixa de diálogo Filtros avançados é preenchida com as métricas padrão e calculadas.

Os filtros disponíveis incluem:

![](assets/advanced_filters_(2).png)

| Nome do filtro | Descrição |
|---|---|
| Tags | Permite aplicar os filtros nas métricas calculadas com tags específicas. Observe que os filtros de tags usam o operador E. Caso você verifique as duas tags, o painel direito mostrará as métricas que foram marcadas com **ambas** as tags. |
| Conjuntos de relatórios | If you apply the "Only *report suite name*" filter in the Calculated Metric Builder in [!DNL Reports & Analytics], and then display the Advanced Filter in [!DNL Report Builder], the Advanced filter will display the calculated metrics for the selected report suite only. |
| Proprietários | Permite que filtrar métricas por proprietário. Observe que os filtros Proprietários usam o operador OU. Se você marcar dois proprietários, o painel direito exibe as métricas de propriedade de **qualquer** proprietário. |
| Outros filtros &gt; Aprovado | Mostra todos os segmentos métricas aprovadas. |
| Outros filtros &gt; Favoritos | Mostra todas as métricas que você marcou como Favoritos. |
| Outros filtros &gt; Meu | Mostra todas as suas métricas. |
| Outros filtros &gt; Compartilhado comigo | Mostra todas as métricas que outras pessoas compartilharam com você. |

## Aplicação de métricas calculadas {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Após selecionar os filtros, clique em **[!UICONTROL Aplicar]para aplicá-las à solicitação.** As métricas selecionadas serão adicionadas ao layout do relatório.

![](assets/filtering_for_metric.png)

