---
title: Comunicar o impacto aos usuários
description: Saiba mais sobre maneiras eficazes de comunicar o impacto de um evento em sua organização.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Event
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 4%

---

# Comunicar o impacto do evento aos usuários

Se você tiver dados [afetado por um evento](overview.md), é importante comunicar esse evento aos usuários em sua organização.

* Desenvolva um aviso de isenção de responsabilidade comum que você possa usar em comunicações para fins de consistência
* Fornecer comunicação contínua aos usuários do Analytics e principais partes interessadas durante e após o evento
* Coloque um lembrete de calendário para marcos subsequentes, como o mês ou ano seguinte. Essa comunicação no futuro ajuda a lembrar os usuários que visualizam relatórios do impacto nos relatórios mês a mês ou ano a ano.

No Adobe Analytics, as seções a seguir mostram maneiras diferentes de se comunicar com os usuários em sua organização. Também é possível usar outros métodos fora do Adobe Analytics, como email, para se comunicar com os usuários.

## Comunicar-se por meio de descrições de painel ou visualização

Se você tiver um projeto do Workspace compartilhado entre os usuários em sua organização, poderá comunicar o impacto de um evento por meio de descrições de painel ou visualização. Clique com o botão direito em um painel ou cabeçalho de visualização e selecione **[!UICONTROL Editar descrição]**.

![Descrição do painel](assets/panel_description.png)

## Comunicar-se por meio de visualizações de texto

Você também pode comunicar o impacto de um evento por meio de visualizações de texto dedicadas. Consulte [Visualizações de texto](/help/analyze/analysis-workspace/visualizations/text.md) no guia do usuário Analisar.

![Visualização de texto](assets/text_visualization.png)

## Adicionar eventos de calendário personalizados a tendências no Espaço de trabalho

Para qualquer visualização de tendência no Workspace, você pode adicionar uma série que representa o intervalo de datas afetado.

1. Crie uma métrica calculada com o segmento &quot;Dias afetados&quot; seguindo [Excluir datas específicas na análise](segments.md).
1. Adicione a métrica desejada à tela de métrica calculada.

   ![Métrica](assets/calcmetric_event.png)

1. Adicione um título e uma descrição informando os usuários sobre o impacto. Também é possível marcar essa métrica como uma anotação de calendário, se desejado.

   ![Título e descrição](assets/calcmetric_title_description.png)

1. Em uma tabela de forma livre, adicione a dimensão &quot;Dia&quot;. Adicione &quot;Visitas&quot; e sua métrica calculada como colunas lado a lado.

   ![Tabela de forma livre](assets/calcmetric_freeform.png)

1. Clique no ícone de engrenagem das configurações de coluna para a métrica calculada e ative **[!UICONTROL Interpretar o zero como valor inexistente]**.

   ![Configurações de métrica calculada](assets/calcmetric_zero_no_value.png)

1. Adicione uma visualização de Linha. Os dias afetados são representados com uma cor diferente. Os usuários também podem clicar no ícone &quot;Informações&quot; na métrica calculada para obter mais informações.

   ![Ícone de informação](assets/calcmetric_infoicon.png)

## Usar um evento de calendário no Reports &amp; Analytics

Se você usa o Reports &amp; Analytics, é possível usar um [evento de calendário](/help/components/t-calendar-event.md) para destacar os dias afetados em qualquer relatório de tendências. Esse método não se aplica ao Analysis Workspace.

1. Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Todos os componentes]** > **[!UICONTROL Eventos de calendário]**.
2. Insira o título, o intervalo de datas e o texto da nota desejados.
3. Clique em **[!UICONTROL Salvar]**.

![Evento de calendário](assets/exclude_calendar_event.png)
