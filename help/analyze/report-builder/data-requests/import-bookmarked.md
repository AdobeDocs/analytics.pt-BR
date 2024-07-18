---
description: Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitações e podem ser importados como solicitações Report Builder.
title: Importar relatórios marcados e reportlets de painel
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 72%

---

# Importar relatórios marcados e reportlets de painel

Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitações e podem ser importados como solicitações Report Builder.

Ao selecionar um relatório marcado, o Assistente de solicitação preenche todas as dimensões e métricas que definem esse relatório marcado. O intervalo de datas, a granularidade e o segmento selecionado também são atualizados com base no marcador selecionado.

Esta é a forma como a Etapa 1 do Assistente de solicitações mostra um painel e seus reportlets.

![Captura de tela mostrando a Etapa 1 de 2 do Assistente de solicitações, destacando Recuperar seus Painéis e Recuperar seus Marcadores.](assets/import_dashboard_reportlet.png)

Ao clicar em **[!UICONTROL Recuperar seus painéis]** ou **[!UICONTROL Recuperar seus marcadores]**, o painel atual e/ou os dados do marcador são recuperados e colados na planilha.

>[!NOTE]
>
>Somente dados são importados, portanto, se o marcador contiver um gráfico, ou se o reportlet do painel consistir de apenas um gráfico, somente os dados utilizados para preencher o gráfico serão importados.

Depois de criar uma solicitação ao importar um reportlet de painel (ou um marcador), a solicitação será associada à dimensão principal do reportlet (ou do marcador). Como resultado, se você editar a solicitação, a visualização de árvore não selecionar mais o nó da visualização de árvore do reportlet de painel (ou o nó do marcador): em vez disso, seleciona a dimensão principal.

