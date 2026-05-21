---
description: 'O Report Builder 5.2 é compatível com as métricas calculadas unificadas do Adobe Analytics. Entre outra inovações, todas as métricas calculadas agora contam com uma ID global: elas não ficam mais restritas a um único conjunto de relatórios.'
title: Métricas calculadas
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
TQID: https://experienceleague.adobe.com/Ae-k-aIMg3n3kXYWFngOzYihtlexLCoD5CmnEN3afhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 40%

---

# Métricas calculadas

{{legacy-arb}}

O Report Builder 5.2 e superior oferece suporte às métricas calculadas do Adobe Analytics. Todas as métricas calculadas agora têm uma ID global: elas não estão mais restritas a um conjunto de relatórios.

>[!NOTE]
>
>As pastas de trabalho atuais talvez indiquem solicitações com as IDs da métrica herdada. Ao usar o Report Builder 5.2, essas IDs da métrica herdada serão convertidas para a nova ID global. Se você compartilhar essa pasta de trabalho com um usuário do Report Builder v5.1 ou anterior, ele não conseguirá visualizar as métricas calculadas.

Para saber mais sobre como criar e gerenciar métricas calculadas com o novo Construtor e Gerenciador de Métricas Calculadas, consulte o Guia de [Métricas Calculadas](/help/components/calculated-metrics/cm-overview.md).

Na Etapa 2 do Assistente de solicitações, você pode filtrar e aplicar métricas calculadas.

## Filtrar métricas calculadas {#section_376E986D3E684999A7CDB08E53854159}

**Filtre** métricas calculadas clicando no ícone Filtrar: ![Captura de tela das opções de Filtro mostrando os campos Aplicativo, Usuário, Projeto.](/help/admin/tools/assets/filter.png)

A caixa de diálogo Filtros avançados é preenchida com métricas padrão e calculadas.

Os filtros disponíveis são:

![Captura de tela mostrando as opções de Filtros Avançados descritas na tabela a seguir.](assets/advanced_filters.png)

| Nome do filtro | Descrição |
|---|---|
| Tags | Permite filtrar métricas calculadas com tags específicas. Observe que os filtros de tags usam o operador AND. Se você marcar duas marcas, o painel direito mostrará métricas que foram marcadas com **ambas** marcas. |
| Conjuntos de relatórios | Se você aplicar o filtro &quot;Somente o *nome do conjunto de relatórios*&quot; no Construtor de métricas calculadas em [!DNL Adobe Analytics] e, em seguida, exibir o filtro Avançado no [!DNL Report Builder], o filtro Avançado exibirá as métricas calculadas somente para o conjunto de relatórios selecionados. |
| Proprietários | Permite filtrar as métricas por proprietário. Observe que os filtros Proprietários usam o operador OR. Se você marcar dois proprietários, o painel direito mostrará as métricas pertencentes ao proprietário **qualquer**. |
| Outros filtros > Aprovado | Mostra todas as métricas aprovadas oficialmente. |
| Outros filtros > Favoritos | Mostra todas as métricas que você marcou como Favoritos. |
| Outros filtros > Meus | Mostra todas as métricas que você possui. |
| Outros filtros > Compartilhados comigo | Mostra todas as métricas que outras pessoas compartilharam com você. |

## Aplicar métricas calculadas {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Após selecionar os filtros, clique em **[!UICONTROL Aplicar]** para aplicá-los à sua solicitação. As métricas selecionadas agora são adicionadas ao layout do relatório.

![Captura de tela mostrando a Etapa 2 do Assistente de solicitações - Totais do site apontando para a janela Filtros avançados e métricas de relatório aplicadas.](assets/filtering_for_metric.png)
