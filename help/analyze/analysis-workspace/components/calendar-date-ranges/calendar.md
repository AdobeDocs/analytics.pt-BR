---
description: No calendário, você pode especificar datas e intervalos de datas ou selecionar uma predefinição.
title: Visão geral do calendário e do intervalos de datas
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: feb6942a54f61850ce11e08008b5694c53436e6d
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 45%

---

# Visão geral do calendário e do intervalos de datas

No calendário, você pode especificar datas e intervalos de datas ou selecionar uma predefinição.

Veja um vídeo sobre o uso de intervalos de datas e calendários no Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23973/?quality=12)

As seleções do calendário se aplicam a nível de painel, mas existe a opção de aplicá-las a todos os painéis. Ao clicar em um intervalo de datas no Espaço de trabalho, a interface exibe o mês atual do calendário e o mês anterior. Você pode ajustar esses dois calendários clicando nas setas para a direita e para a esquerda em cada canto superior respectivo.

![Calendário](assets/aw_calendar2.png){width="60%"}

## Selecionar e aplicar intervalos de datas {#select-apply}

O primeiro clique em um calendário inicia uma seleção de intervalo de datas. O segundo clique conclui uma seleção de intervalo de datas, que é realçada. Se a tecla `Shift` for pressionada (ou se o clique com o botão direito do mouse for usado), ela será anexada ao intervalo selecionado no momento.

Você também pode arrastar datas (e dimensões de tempo) em um projeto do Espaço de trabalho. É possível selecionar dias, semanas, meses e anos específicos ou uma data do acumulado.

[Usando intervalos de data e calendário na Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=pt-BR) (4:07)

| Configuração | Descrição |
|--- |--- |
| Dias selecionados | Dias/semanas/meses/anos selecionados. |
| Tornar os componentes do intervalo de datas relativos ao calendário do painel | Mantenha as datas com base no intervalo de datas do painel consistente. |
| Usar datas do acumulado | Datas do acumulado permitem gerar um relatório dinâmico que analisa antes e depois de um período de tempo com base na execução do relatório. Por exemplo, se você quiser relatar todos os pedidos feitos no “Mês anterior” (dependendo da Data de criação) e executar o relatório em dezembro, você verá os pedidos feitos em novembro. Se executar o mesmo relatório em janeiro, verá os pedidos feitos em dezembro.<ul><li>**[!UICONTROL Visualização de data]**: indica o período compreendido no calendário em andamento.</li><li>**[!UICONTROL Início]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li><li>**[!UICONTROL Fim]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li></ul>Para ver um exemplo, consulte [Intervalos de datas personalizados](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Selecionado por padrão. |
| Intervalo de datas | Permite selecionar um intervalo de datas predefinido. Últimos 30 dias é padrão. **[!UICONTROL Essa semana/mês/trimestre/ano (exceto hoje)]** permite escolher entre intervalos de datas que não incluem dados parciais do dia de hoje. |
| Aplicar a todos os painéis | Permite alterar o intervalo de datas selecionado para o painel atual e também para todos os outros painéis do projeto. |
| Aplicar | Aplica o intervalo de datas somente a este painel. |

## Sobre intervalos de datas relativos do painel {#relative-panel-dates}

Se estiver trabalhando no Workspace, é possível fazer os componentes do intervalo de datas relativos ao calendário do painel.
Três casos de uso comuns em que você verá datas relativas do painel entrarem em vigor são gráficos de Combinação, resumo de métricas principais e intervalos de datas da tabela de Forma livre.

Para usar intervalos de datas do painel relativo

1. Selecione o **Workspace** guia .
1. Selecione **Projeto em branco**.
1. Adicione dimensões, métricas e segmentos no painel esquerdo.
1. Clique no campo de intervalo de datas do painel para alternar a configuração de intervalo de datas do painel relativo.
1. Selecionar **Fazer componentes do intervalo de datas em relação ao calendário do painel**.
   * Selecione a opção para tornar os componentes do intervalo de datas relativos ao calendário do painel.
Se as datas relativas forem selecionadas, as datas do acumulado serão baseadas na data de início do calendário do painel e não na data de hoje.
   * Se essa opção não estiver selecionada, as datas do acumulado serão baseadas na data de hoje.

   ![datas relativas ao painel](assets/relative-date-selected.png){width="60%"}

1. Clique em **Aplicar**.
As datas relativas são mostradas no canto superior direito.

   ![datas relativas em forma livre ](assets/relative-date-range1.png)

## Diretrizes para os intervalos de datas relativos do painel {#guidelines}

Lembre-se das diretrizes a seguir ao usar intervalos de datas relativos do painel.

### Fórmulas e intervalos de datas relativos {#formula-relative-dates}

Se você tiver datas relativas selecionadas, todas as fórmulas de datas usarão a data de início do painel como ponto de partida.

### Calendários personalizados e intervalos de datas relativos {#custom-calendar-formulas}

Ao usar um calendário personalizado com base na semana e adicionar meses ou anos, a fórmula calcula o deslocamento do dia no período especificado. A data real pode ser diferente devido ao deslocamento. A fórmula escolhe o dia de aterrissagem no mesmo local do calendário personalizado. Por exemplo, a terceira sexta-feira da terceira semana em um calendário personalizado.

### Sobre segmentos que usam datas do acumulado e intervalos de datas relativos do painel {#segments-relative-dates}

Se você criar um segmento ou usar um segmento com uma data do acumulado, por exemplo, os Últimos 7 dias ou as Últimas 2 semanas, e clicar na visualização do segmento, a data do acumulado será iniciada a partir de *Hoje* em vez da data de início do painel. Como resultado, a visualização do segmento não corresponderá quando você realmente usar o segmento na tabela. A visualização é afetada, não o segmento propriamente dito.

## Diretrizes para intervalos de datas e visualizações do painel {#guidelines-panel-dates}

* A partir da versão de fevereiro, as visualizações de componentes e dados serão baseadas no intervalo de datas do painel e não nos últimos 90 dias.
* Todos os componentes listados no painel esquerdo estarão disponíveis com base no intervalo de datas do painel.
* Todas as visualizações de data no segmento e construtores de métrica calculada serão baseadas no intervalo de datas do painel (a menos que sejam acessadas pelos gerentes de componente, que não têm um painel associado, elas ainda serão baseadas nos últimos 90 dias).
* Quaisquer visualizações de dados exibirão dados ou componentes com base no intervalo de datas do painel.