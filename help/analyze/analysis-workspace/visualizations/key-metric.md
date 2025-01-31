---
description: Use a visualização do resumo da métrica principal para comparar o desempenho da métrica em duas linhas do tempo.
title: Resumo da métrica principal
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: b2e91c9981b328aa34e03dcd3b713438732ea6b1
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 36%

---

# Resumo da métrica principal {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Resumo da métrica principal"
>abstract="Crie uma visualização que seja uma combinação dos gráficos de linha, alteração de resumo e número de resumo. Use essa visualização para comparar a tendência das métricas importantes entre dois períodos."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a visualização do resumo da métrica principal no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte o [Resumo da métrica principal](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/key-metric) da_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** versão deste artigo._

>[!ENDSHADEBOX]


A visualização do ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** permite ver a tendência de uma métrica importante em um único período. Ela também permite comparar o desempenho da métrica em dois intervalos de tempo. Ela oferece os benefícios de várias visualizações combinadas em uma única visualização:

* A visualização de **[!UICONTROL Linha]** mostra a tendência da métrica para os intervalos de datas principal e de comparação

* **[!UICONTROL Alteração percentual do resumo]** mostra o aumento ou a diminuição da métrica entre os intervalos de datas principal e de comparação

* Valor total atual ([!UICONTROL **número do resumo**]) para a métrica

## Casos de uso

Essa visualização aborda vários casos de uso comuns, incluindo:

* Um analista tentando entender como a criação de oportunidades parecia este mês em comparação com o mesmo período do ano passado.

* Um comerciante que explora como a geração de clientes potenciais para um tipo de cliente potencial específico mudou este mês em comparação com o mês anterior.

* Um executivo querendo entender como novas reservas mudaram este trimestre em comparação com o trimestre anterior.

## Usar

1. Adicionar uma visualização de ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric]**. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configure a visualização selecionando uma **[!UICONTROL Métrica]**, um **[!UICONTROL Intervalo de datas principal]**, um **[!UICONTROL Intervalo de datas de comparação]** (opcional) e um **[!UICONTROL Filtro]** (opcional):

   ![Configuração da métrica principal mostrando as opções de métrica, intervalo de datas principal, intervalo de datas de comparação e segmento.](assets/key-metrics-config.png)

   | Opção | Descrição |
   | --- | --- |
   | **[!UICONTROL Métrica]** | Selecione a métrica que deseja examinar. Todas as métricas são compatíveis. |
   | **[!UICONTROL Intervalo de datas principal]** | O intervalo de datas atual da tabela de forma livre.<p>Escolha entre qualquer intervalo de datas disponível na visualização de dados.</p> <p>Escolha [!UICONTROL **Intervalo de datas do painel**] se desejar usar o mesmo intervalo de datas que está sendo usado no painel onde a visualização está localizada.</p> |
   | **[!UICONTROL Intervalo de datas de comparação]** | O intervalo de datas que você deseja comparar com o intervalo de datas principal. |
   | **[!UICONTROL Filtro (opcional)]** | Qualquer filtro em que você esteja interessado neste resumo. |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >Quando o campo [!UICONTROL **Intervalo de datas principal**] está definido como [!UICONTROL **Intervalo de datas do painel**], o **[!UICONTROL Intervalo de datas de comparação]** pode ser atualizado automaticamente, dependendo se a opção **[!UICONTROL Intervalo de datas de comparação]** escolhida é relativa ao intervalo de datas principal ou fixa.
   >
   >* **Relativo:** se o campo **[!UICONTROL Intervalo de datas de comparação]** estiver definido como uma opção relativa ao intervalo de datas principal (como [!UICONTROL **Dia anterior**], [!UICONTROL **Mesmo dia da semana passada**], [!UICONTROL **Mesmo dia 4 semanas antes**] e assim por diante), qualquer atualização no campo [!UICONTROL **Intervalo de datas principal**] fará com que o **[!UICONTROL Intervalo de datas de comparação]** atualize automaticamente para o período que segue imediatamente o intervalo de datas do painel.
   >* **Fixo:** se o campo [!UICONTROL **Intervalo de datas de comparação**] estiver definido como um intervalo de datas fixo (como **3 de fevereiro de 2023**), as alterações feitas no campo [!UICONTROL **Intervalo de datas principal**] ou no intervalo de datas do painel não terão efeito no [!UICONTROL **Intervalo de datas de comparação**]. No entanto, qualquer atualização no intervalo de datas do painel faz com que o [!UICONTROL **Intervalo de datas principal**] seja atualizado automaticamente.

1. Selecione **[!UICONTROL Criar]**.

A saída do resumo da métrica principal é semelhante a:

![Saída de métrica principal mostrando a métrica, a alteração de resumo, o número de resumo e os gráficos de linha.](assets/key-metrics.png)

Considere o seguinte ao visualizar a saída:

* O gráfico de linhas **[!UICONTROL Período anterior]** (sempre exibido em cinza) corresponde ao **[!UICONTROL Intervalo de datas de comparação]** na etapa de configuração.

* Se um intervalo de datas de comparação não for especificado durante a configuração ou estiver oculto nas configurações de visualização, somente o gráfico de linhas do intervalo de datas principal será exibido. A alteração do resumo está oculta.

* A partir daqui, você pode passar o mouse sobre os gráficos de linha para ver as estatísticas de dias individuais:


## Configurar

Após criar a visualização, é possível editar a configuração original.

1. Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Configurar visualização]** na parte superior da visualização.

   Você é levado de volta à caixa de diálogo de configuração original.

1. Altere as configurações como preferir. Selecione **[!UICONTROL Redefinir]** para redefinir as configurações atuais. Selecione **[!UICONTROL Build]** para recriar a visualização.

## Configurações 

Como parte das configurações de visualização, configurações específicas do resumo da métrica principal estão disponíveis.

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Enfatizar a variação percentual]** | Exibir a alteração de resumo em negrito de destaque no centro da visualização |
| **[!UICONTROL Enfatizar o valor do número]** | Exibir o número do resumo em negrito de destaque no centro da visualização |
| **[!UICONTROL Legenda visível]** | Mostrar ou ocultar a legenda na parte inferior da visualização |
| **[!UICONTROL Mostrar anotações]** | Mostrar ou ocultar anotações adicionadas por um administrador |
| **[!UICONTROL Ocultar título]** | Ocultar o título da visualização. |
| **[!UICONTROL Porcentagens]** | Exibe a visualização em uma porcentagem em vez de um número. |
| **[!UICONTROL Mostrar linhas de tendência]** | Mostrar linhas de tendência na visualização. |
| **[!UICONTROL Mostrar máximo e mínimo em linhas de tendência]** | Mostrar ou ocultar valores mínimos e máximos em gráficos de linha primários e de comparação |
| **[!UICONTROL Mostrar porcentagem de comparação e linha de tendência]** | Mostrar ou ocultar dados de comparação. Quando ocultos, o gráfico de linha de comparação e os objetos de alteração de resumo ficam ocultos da exibição. |
| **[!UICONTROL Mostrar número total]** | Mostrar ou ocultar o número do resumo |
| **[!UICONTROL Mostrar diferença bruta]** | Mostrar ou ocultar diferença bruta entre o valor total da métrica no intervalo de datas principal e o intervalo de datas secundário |
| **[!UICONTROL Abreviar valor]** | Selecione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente o valor do número. Quando selecionado, insira um número para definir a quantidade de abreviação. Por exemplo:<br/><table><tr><td>**Valor original**</td><td>**Abreviação**</td><td>**Resultado**</td></tr><tr><td>$ 12.011.141,25</td><td>Não selecionado</td><td align="right">$ 12.011.141,25</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como 1</td><td align="right">US$ 12 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como 2</td><td align="right">US$ 12,0 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como 2</td><td align="right">US$ 12,011 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionar, definir como 3</td><td align="right">US$ 12,011 milhões</td></tr></table> |

## Editar visualização

Após criar a visualização, ainda é possível editar a configuração original.

1. Clique no ícone de lápis no canto superior direito da visualização (ao lado do ícone de engrenagem de configurações).

   ![Ícone de edição de visualização](assets/edit-icon.png)

   Você será levado de volta à visualização da configuração original.

1. Altere a métrica, o intervalo de datas principal, o intervalo de datas de comparação ou o filtro, como preferir.

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)

