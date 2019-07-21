---
description: A comparação de datas na Analysis Workspace permite pegar qualquer coluna contendo um intervalo de datas e criar uma comparação de datas comum, como ano sobre ano, trimestres sobre trimestres, mês sobre mês, etc.
seo-description: A comparação de datas na Analysis Workspace permite pegar qualquer coluna contendo um intervalo de datas e criar uma comparação de datas comum, como ano sobre ano, trimestres sobre trimestres, mês sobre mês, etc.
seo-title: Comparação de datas
title: Comparação de datas
uuid: ef 18 f 9 d 9-b 6 ad -4859-b 7 c 9-9750 ca 0 df 519
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comparação de datas

A comparação de datas na Analysis Workspace permite pegar qualquer coluna contendo um intervalo de data e criar uma comparação de data comum, como: ano sobre ano, trimestres sobre trimestres, mês sobre mês, etc.

## Comparar períodos de tempo {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

A análise demanda contexto, e esse contexto é normalmente fornecido por um período de tempo anterior. Por exemplo, a pergunta "Estamos melhor ou pior que nesse mesmo período de tempo no ano passado?" é fundamental para entender seus negócios. A comparação de data inclui automaticamente uma coluna "diferença", que mostra a porcentagem de mudança comparada a um período de tempo específico.

1. Crie uma tabela de forma livre, com qualquer dimensão e métrica que desejar comparar em um período de tempo.
1. Clique com o botão direito na linha da tabela e selecione **[!UICONTROL Comparar períodos de tempo]**.

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >Essa opção de clique com o botão direito do mouse é desativada para linhas de métricas, linhas de intervalo de datas e linhas de dimensão de tempo.

1. Dependendo de como configurou o intervalo de data da tabela, você tem as opções a seguir para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Semana/mês/trimestre/ano anterior a esse intervalo de data]** | Compara com a semana/mês/etc. imediatamente antes desse intervalo de data. |
   | **[!UICONTROL Esta semana/mês/trimestre/ano no ano passado]** | Compara com o mesmo intervalo de data no ano passado. |
   | **[!UICONTROL Selecionar intervalo]** | Permite selecionar um intervalo de data personalizado. |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Select range]**.

1. O resultado da comparação aparece assim:

   ![](assets/compare-time-result.png)

   As linhas na coluna de Alteração na porcentagem aparecem em vermelho para valores negativos e em verde para positivos.

1. (Opcional) Como em qualquer projeto da Workspace, é possível criar visualizações baseadas nestas comparações de tempo. Por exemplo, aqui está um gráfico de barras:

   ![](assets/compare-time-barchart.png)

   Observe que para mostrar a mudança de porcentagem no gráfico de barras, você deve ter a configuração [!UICONTROL Porcentagens] selecionada nas [!UICONTROL Configurações de visualização].

## Add a time period column for comparison {#section_93CC2B4F48504125BEC104046A32EB93}

A partir de agora, é possível adicionar um período de tempo a cada coluna de uma tabela, permitindo que você adicione períodos diferentes daqueles definidos no seu calendário. Essa é mais uma forma de comparar datas.

1. Clique com o botão direito na tabela e selecione **[!UICONTROL Adicionar coluna de período de tempo]** ![](assets/add-time-period-column.png)

1. Dependendo de como configurou o intervalo de data da tabela, você tem as opções a seguir para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Semana/mês/trimestre/ano anterior a esse intervalo de data]** | Adiciona uma coluna com semana/mês/etc. imediatamente antes desse intervalo de data. |
   | **[!UICONTROL Esta semana/mês/trimestre/ano no ano passado]** | Adiciona o mesmo intervalo de data no ano passado. |
   | **[!UICONTROL Selecionar intervalo]** | Permite selecionar um intervalo de data personalizado. |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Select range]**.

1. O período de tempo será inserido no topo da coluna selecionada:

   ![](assets/add-time-period-column2.png)

1. É possível adicionar quantas colunas desejar, assim como misturar e correlacionar diferentes intervalos de data:

   ![](assets/add-time-period-column4.png)

1. Além disso, é possível classificar em cada coluna, o que alterará a ordem de dias dependendo da coluna que for classificada.

## Align column dates to start on same row {#section_5085E200082048CB899C3F355062A733}

Uma nova configuração das tabelas permite **[!UICONTROL Alinhar datas de cada coluna para iniciarem na mesma linha (se aplica a toda a tabela)]**. O "se aplica a toda a tabela" significa que se você fizer, por exemplo, um detalhamento na tabela, e alterar essa configuração para o detalhamento, modificará a configuração de toda a tabela.

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>This setting is **disabled** (unchecked) for all existing projects and **enabled** (checked) for all new projects.

Exemplo: ao escolher alinhar das datas, em uma comparação de mês por mês entre outubro e setembro de 2016, a coluna da esquerda iniciará em 1° de outubro e a coluna da direita em 1° de setembro:

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

