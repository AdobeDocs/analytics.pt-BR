---
description: Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitação e podem ser importados como solicitações do Report Builder.
title: Importar relatórios marcados e reportlets de painel
topic: Report builder
uuid: 0fdbdb2e-5db7-4f64-b571-23482ba3606d
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 100%

---


# Importar relatórios marcados e reportlets de painel

Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitação e podem ser importados como solicitações do Report Builder.

Ao selecionar um relatório marcado, o Assistente de solicitação preenche todas as dimensões e métricas que definem esse relatório marcado. O intervalo de datas, a granularidade e o segmento selecionado também são atualizados com base no marcador selecionado.

Esta é a forma como a Etapa 1 do Assistente de solicitações mostra um painel e seus reportlets.

![](assets/import_dashboard_reportlet.png)

Ao clicar em **[!UICONTROL Recuperar seus painéis]** ou **[!UICONTROL Recuperar seus marcadores]**, o painel atual e/ou os dados do marcador são recuperados e colados na planilha.

>[!NOTE]
>
>No Report Builder, a lista de painéis e marcadores disponíveis está limitada ao usuário, mas também aos que se aplicam ao conjunto de relatórios selecionado na Etapa 1 do assistente. Por outro lado, nos relatórios e análises de marketing, você recebe acesso aos marcadores e painéis acessíveis, independentemente dos conjuntos de relatórios que o painel e os marcadores usam.

>[!NOTE]
>
>Somente dados são importados, portanto, se o marcador contiver um gráfico, ou se o reportlet do painel consistir em apenas um gráfico, somente os dados utilizados para preencher o gráfico serão importados.

Depois de criar uma solicitação ao importar um reportlet de painel (ou um marcador), a solicitação será associada à dimensão principal do reportlet (ou do marcador). Como resultado, se você editar a solicitação, a visualização de árvore não selecionar mais o nó da visualização de árvore do reportlet de painel (ou o nó do marcador): em vez disso, seleciona a dimensão principal.

O miniaplicativo importado definirá apropriadamente o conjunto de relatórios, o segmento selecionado, a dimensão e as métricas selecionadas com os mesmos parâmetros expostos no marcador de Reports &amp; Analytics.

>[!IMPORTANT]
>
>O intervalo de datas será definido como estático; mesmo se esse intervalo de datas for cumulativo no marcador de Reports &amp; Analytics.

