---
description: Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitação e podem ser importados como solicitações do construtor de relatórios.
title: Importar relatórios marcados e reportlets de painel
topic: Report builder
uuid: 0fdbdb2e-5db7-4f64-b571-23482ba3606d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importar relatórios marcados e reportlets de painel

Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitação e podem ser importados como solicitações do construtor de relatórios.

Ao selecionar um relatório marcado, o Assistente de solicitação preenche todas as dimensões e métricas que definem esse relatório marcado. O intervalo de datas, a granularidade e o segmento selecionado também são atualizados com base no marcador selecionado.

Esta é a forma como a Etapa 1 do Assistente de solicitações mostra um painel e seus reportlets.

![](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

> [!NOTE] No Construtor de relatórios, a lista de painéis e marcadores disponíveis está limitada ao usuário, mas também àqueles que se aplicam ao conjunto de relatórios selecionado na Etapa 1 do assistente. Por outro lado, nos relatórios e análises de marketing, você recebe acesso aos marcadores e painéis acessíveis, independentemente dos conjuntos de relatórios que o painel e os marcadores usam.

> [!NOTE] Somente os dados são importados, portanto, se o marcador contiver um gráfico, ou se o reportlet do painel consistir em apenas um gráfico, somente os dados usados para preencher o gráfico serão importados.

Depois de criar uma solicitação ao importar um reportlet de painel (ou um marcador), a solicitação será associada à dimensão principal do reportlet (ou do marcador). Como resultado, se você editar a solicitação, a visualização de árvore não selecionar mais o nó da visualização de árvore do reportlet de painel (ou o nó do marcador): em vez disso, seleciona a dimensão principal.

O miniaplicativo importado definirá apropriadamente o conjunto de relatórios, o segmento selecionado, a dimensão e as métricas selecionadas com os mesmos parâmetros expostos no marcador de Relatórios e análises.

>[!IMPORTANT]
>
>O intervalo de datas será definido para o mesmo intervalo de datas, mas como um intervalo de datas estático - mesmo se esse intervalo de datas for um intervalo de datas acumulado no marcador de Relatórios e análises.

