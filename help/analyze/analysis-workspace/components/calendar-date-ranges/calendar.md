---
description: No calendário, você pode especificar datas e intervalos de datas ou selecionar uma predefinição.
title: Visão geral do calendário e do intervalos de datas
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: b08200266204bc01c943194ea2b0b002c2bfa878
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 67%

---

# Visão geral do calendário e do intervalos de datas

No calendário, você pode especificar datas e intervalos de datas ou selecionar uma predefinição.

Veja um vídeo sobre o uso de intervalos de datas e calendários no Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23973/?quality=12)

As seleções do calendário se aplicam a nível de painel, mas existe a opção de aplicá-las a todos os painéis. Ao clicar em um intervalo de datas no Espaço de trabalho, a interface exibe o mês atual do calendário e o mês anterior. Você pode ajustar esses dois calendários clicando nas setas para a direita e para a esquerda em cada canto superior respectivo.

![Calendário](assets/aw_calendar1.png)

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

Se estiver trabalhando no Workspace, é possível fazer os componentes do intervalo de datas relativos ao calendário do painel, de modo que os dados visualizados no painel à esquerda (ou dentro de componentes) sejam baseados no intervalo de datas do painel. Três casos de uso comuns em que você verá datas relativas do painel entrarem em vigor são gráficos de combinação, resumo das métricas principais e intervalos de datas da tabela de forma livre.

Para usar intervalos de datas do painel relativo

1. Selecione o **Workspace** guia .
1. Selecionar **Projeto em branco**.
1. Adicione dimensões, métricas e segmentos no painel esquerdo.
1. Clique no campo de intervalo de datas do painel para alternar a configuração de intervalo de datas do painel relativo.
1. Selecionar ou desmarcar **Fazer componentes do intervalo de datas em relação ao calendário do painel**.
   * Selecione a opção para tornar os componentes do intervalo de datas relativos ao calendário do painel.
   * Desmarcar essa opção significa que os intervalos de datas no painel (Resumo da métrica-chave, Gráficos de combinação ou Pílulas de data violeta) não serão atualizados se o intervalo de datas do painel for alterado. Esse é o padrão.

   ![datas relativas ao painel](assets/relative-date-snippet.png)

1. Clique em **Aplicar**.
As datas relativas são mostradas no canto superior direito.

   ![datas relativas em forma livre ](assets/relative-date-range1.png)