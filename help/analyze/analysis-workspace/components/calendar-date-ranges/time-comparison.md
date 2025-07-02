---
description: 'A comparação de datas no Analysis Workspace permite usar qualquer coluna que contenha um intervalo de datas e criar uma comparação de datas comum, como: ano a ano, trimestre a trimestre, mês a mês, etc.'
title: Comparação de datas
feature: Date Ranges
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: ht
source-wordcount: '747'
ht-degree: 100%

---

# Comparação de datas

A comparação de datas no Analysis Workspace permite pegar qualquer coluna contendo um intervalo de data e criar uma comparação de data comum, como: ano sobre ano, trimestres sobre trimestres, mês sobre mês, etc.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparação de dados](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]



## Comparar períodos {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Comparar períodos] utiliza métricas calculadas avançadas. Como resultado, ele está disponível somente para clientes com SKUs do Analytics Select, Prime e Ultimate.

A análise demanda contexto, o qual normalmente é fornecido por um período anterior. Por exemplo, a pergunta: “Quão melhor ou pior estamos agora em relação a esse mesmo período no ano passado?” é fundamental para entender seus negócios. A comparação de datas inclui automaticamente uma coluna &quot;diferença&quot;, que mostra a porcentagem de mudança comparada a um período de tempo específico.

1. Crie uma tabela de forma livre, com qualquer dimensão e métrica que desejar comparar em um período.
1. Clique com o botão direito em uma linha da tabela e selecione **[!UICONTROL Comparar períodos]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >A opção de clicar com o botão direito está desativada para linhas de métrica, linhas de intervalo de datas e linhas de dimensão.

1. Dependendo de como configurou o intervalo de data da tabela, você tem as opções a seguir para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Semana/mês/trimestre/ano anterior a esse intervalo de datas]** | Compara com a semana/mês/etc. imediatamente antes desse intervalo de data. |
   | **[!UICONTROL Esta semana, mês ou trimestre do ano passado, ou o ano passado inteiro até este intervalo de datas]** | Compara com o mesmo intervalo de datas no ano passado. |
   | **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]** | Permite selecionar um intervalo de datas personalizado. |

   >[!NOTE]
   >
   >Ao selecionar um número de dias personalizado, por exemplo, de 7 a 20 de outubro (intervalo de 14 dias), você terá apenas duas opções: **[!UICONTROL Os 14 dias anteriores a esse intervalo de datas]** e **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]**.

1. O resultado da comparação aparece assim:

   ![](assets/compare-time-result.png)

   As linhas na coluna de Alteração na porcentagem aparecem em vermelho para valores negativos e em verde para positivos.

1. (Opcional) Como em qualquer projeto do Espaço de trabalho, é possível criar visualizações baseadas nestas comparações de tempo. Por exemplo, aqui está um gráfico de barras:

   ![](assets/compare-time-barchart.png)

   Observe que para mostrar a mudança de porcentagem no gráfico de barras, você deve ter a configuração [!UICONTROL Porcentagens] selecionada nas [!UICONTROL Configurações de visualização].

## Adicionar uma coluna de período de tempo para comparação {#section_93CC2B4F48504125BEC104046A32EB93}

A partir de agora, é possível adicionar um período de tempo a cada coluna de uma tabela, permitindo que você adicione períodos diferentes daqueles definidos no seu calendário. Essa é mais uma forma de comparar datas.

1. Clique com o botão direito do mouse em uma coluna na tabela e selecione **[!UICONTROL Adicionar coluna de período]**.

   ![](assets/add-time-period-column.png)

1. Dependendo de como configurou o intervalo de data da tabela, você tem as opções a seguir para comparação:

   | Opção | Descrição |
   |---|---|
   | **[!UICONTROL Semana/mês/trimestre/ano anterior a esse intervalo de datas]** | Adiciona uma coluna com semana/mês/etc. imediatamente antes desse intervalo de data. |
   | **[!UICONTROL Esta semana, mês ou trimestre do ano passado, ou o ano passado inteiro até este intervalo de datas]** | Adiciona o mesmo intervalo de data no ano passado. |
   | **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]** | Permite selecionar um intervalo de datas personalizado. |

   >[!NOTE]
   >
   >Ao selecionar um número de dias personalizado, por exemplo, de 7 a 20 de outubro (intervalo de 14 dias), você terá apenas duas opções: **[!UICONTROL Os 14 dias anteriores a esse intervalo de datas]** e **[!UICONTROL Intervalo de datas personalizado até este intervalo de datas]**.

1. O período de tempo será inserido no topo da coluna selecionada:

   ![](assets/add-time-period-column2.png)

1. É possível adicionar quantas colunas desejar, assim como misturar e correlacionar diferentes intervalos de data:

   ![](assets/add-time-period-column4.png)

1. Além disso, é possível classificar em cada coluna, o que alterará a ordem de dias dependendo da coluna que for classificada.

## Alinhar as datas das colunas para que comecem na mesma linha {#section_5085E200082048CB899C3F355062A733}

É possível alinhar as datas de cada coluna para que todas iniciem na mesma linha. 

Por exemplo, ao escolher alinhar as datas, se você fizer uma comparação mês a mês entre outubro e setembro de 2016, a coluna da esquerda iniciará em 1° de outubro e a coluna da direita em 1° de setembro:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Considere o seguinte ao usar essa opção:
>
>* Essa configuração é habilitada por padrão para todos os novos projetos.
>
>* Essa configuração se aplica a toda a tabela. Por exemplo, se você alterar essa definição para um detalhamento na tabela, ela alterará a configuração da tabela inteira.
>

Para habilitar essa configuração, se ela ainda não estiver habilitada:

1. Na tabela onde deseja alinhar as datas da coluna, selecione o ícone **Configurações** no cabeçalho.

1. Na guia [!UICONTROL **Configurações**], selecione **[!UICONTROL Alinhar as datas de cada coluna para que todas iniciem na mesma linha (aplica-se a toda a tabela)]**.

![](assets/date-comparison-setting.png)


