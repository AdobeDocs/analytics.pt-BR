---
description: Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitações e podem ser importados como solicitações do Report Builder.
title: Importar relatórios marcados e reportlets de painel
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 33%

---

# Importar relatórios marcados e reportlets de painel

{{legacy-arb}}

Todos os relatórios marcados e relatórios de painel agora são listados como dimensões na Etapa 1 do assistente de solicitações e podem ser importados como solicitações do Report Builder.

Ao selecionar um relatório marcado, o Assistente de solicitação preenche todas as dimensões e métricas que definem esse relatório marcado. O intervalo de datas, a granularidade e o segmento selecionado também são atualizados com base no marcador selecionado.

É assim que a Etapa 1 do assistente de solicitações mostra um painel e seus reportlets:

![Captura de tela mostrando a Etapa 1 de 2 do Assistente de solicitações, destacando Recuperar seus Painéis e Recuperar seus Marcadores.](assets/import_dashboard_reportlet.png)

Ao clicar em **[!UICONTROL Recuperar seus Painéis]** ou **[!UICONTROL Recuperar seus Marcadores]**, os dados existentes do painel e/ou do marcador são recuperados e colados na planilha.

>[!NOTE]
>
>Somente dados são importados, portanto, se o marcador contiver um gráfico, ou se o reportlet do painel consistir de apenas um gráfico, somente os dados utilizados para preencher o gráfico serão importados.

Depois de criar uma solicitação importando um reportlet de painel (ou um marcador), a solicitação será associada à dimensão principal do reportlet (ou do marcador). Como resultado, se você editar a solicitação, a exibição em árvore não selecionará mais o nó de exibição em árvore do reportlet do painel (ou o nó de marcador). Em vez disso, ela selecionará sua dimensão principal.

