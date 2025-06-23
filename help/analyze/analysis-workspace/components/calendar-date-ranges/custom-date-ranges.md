---
description: Crie intervalos de datas personalizados no Analysis Workspace e salve-os como Componentes de tempo.
keywords: Analysis Workspace
title: Criar intervalos de datas personalizados
feature: Date Ranges
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 100%

---

# Criar intervalos de datas personalizados

É possível criar intervalos de data personalizados no Analysis Workspace e salvá-los como componentes de tempo.

Para obter informações sobre como adicionar intervalos de datas existentes a um projeto, consulte [Visão geral do calendário e de intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).

Para criar um intervalo de datas personalizado:

1. No Adobe Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Intervalos de datas]**.

   ![Página do intervalo de datas](assets/date-ranges.png)

1. Selecione [!UICONTROL **Criar novo intervalo de datas**].

1. No criador de intervalo de datas, especifique as seguintes informações:

   | Opção | Descrição |
   |---------|----------|
   | [!UICONTROL **Título**] | O título do intervalo de datas que aparecerá quando os usuários o selecionarem no Analysis Workspace. |
   | [!UICONTROL **Descrição**] | Uma descrição para o intervalo de datas. |
   | [!UICONTROL **Tags**] | Quaisquer tags que deseja aplicar ao intervalo de datas. |
   | [!UICONTROL **Intervalo de datas**] | Permite selecionar um intervalo de datas personalizado. Por padrão, a opção “Os últimos 30 dias” está selecionada. |
   | [!UICONTROL **Predefinição**] | Escolha dentre uma lista de intervalos de datas predefinidos, como [!UICONTROL **Ontem**], [!UICONTROL **Últimos 7 dias**], [!UICONTROL **Últimos 30 dias**] e assim por diante. |
   | [!UICONTROL **Hora de início**] | A hora do dia em que o intervalo de datas começa. |
   | [!UICONTROL **Hora de término**] | A hora do dia em que o intervalo de datas termina. |
   | [!UICONTROL **Usar datas contínuas**] | Datas contínuas permitem gerar um relatório dinâmico que analisa um certo período de tempo, seja para frente ou para trás, com base na execução do relatório. Por exemplo, se você quiser relatar todos os pedidos feitos no “Mês anterior” (dependendo da Data de criação) e executar o relatório em dezembro, você verá os pedidos feitos em novembro. Se executar o mesmo relatório em janeiro, verá os pedidos feitos em dezembro.<ul><li>**[!UICONTROL Visualização de data]**: indica o período compreendido no calendário em andamento.</li><li>**[!UICONTROL Início]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li><li>**[!UICONTROL Fim]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li></ul><br>Selecionado por padrão. |

1. Selecione [!UICONTROL **Salvar**].

## Exemplo: intervalo de datas para “dois meses atrás”  {#section_C4109C57CB444BB2A79CC8082BD67294}

O intervalo de datas personalizado a seguir mostra um intervalo de datas para “dois meses atrás” com uma visualização de Alteração do resumo, que mostra a alteração direcional.

![](assets/date-range-two-months-ago.png)

O intervalo de datas personalizado é exibido na parte superior do painel do componente [!UICONTROL Intervalo de datas] no seu projeto:

![](assets/date-range-panel-two-months-ago.png)

Você pode arrastar esse intervalo de datas personalizado para uma coluna ao lado do intervalo de datas personalizado, acumulado mensalmente, usando o Último mês predefinido para uma comparação. Adicione uma visualização de Resumo de alterações e selecione os totais de cada coluna para mostrar a alteração direcional:

![](assets/date-range-two-months-table.png)

## Exemplo: usar um intervalo de datas contínuo de sete dias {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

É possível criar um intervalo de datas com uma janela contínua de sete dias que termina uma semana atrás:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* As configurações de Início seriam *`current day minus 6 days`*.

* As configurações de Fim seriam *`current day minus 7 days`*.

Esse intervalo de datas pode ser um componente que você arrasta para qualquer tabela de forma livre.
