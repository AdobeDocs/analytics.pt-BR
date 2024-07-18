---
description: Detalhes sobre o modelo do Analysis Workspace e relatórios no Report Builder.
title: Relatório sobre dados de publicidade no Adobe Analytics
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 49%

---

# Relatório sobre dados de publicidade

Este artigo fornece detalhes sobre o relatório do Analysis Workspace e os relatórios no Report Builder.

>[!NOTE]
>
>É necessário esperar pelo menos 24 horas até que os dados do mecanismo de pesquisa comecem a preencher os relatórios do Analytics. Observe também que os relatórios do Analytics não retornam dados para granularidade por hora, pois os dados do Advertising Cloud não são compatíveis com granularidade por hora.

## Relatório de pesquisa paga {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

Este relatório permite que qualquer pessoa que implemente a integração de mecanismo de pesquisa tenha acesso aos dados do mecanismo de pesquisa no Analytics. Você pode acessá-lo via **[!UICONTROL Workspace]** > **[!UICONTROL Relatórios]** > **[!UICONTROL Aquisição]** > **[!UICONTROL Advertising Analytics: pesquisa paga]**

>[!NOTE]
>
>O relatório Pesquisa paga está visível a todos os clientes, mesmo se você não tiver implementado nenhuma Conta da Advertising. Se você tentar abrir o Relatório de pesquisa paga para uma empresa que não foi provisionada, uma mensagem de erro explicará que você não configurou nenhuma conta de mecanismo de pesquisa. Selecione **[!UICONTROL Configurar Agora]**, para acessar a tela [Configuração de Conta do Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| Tabela/Visualização | Descrição |
|--- |--- |
| Tendências de publicidade | Visão geral de tendência diária das Impressões do AMO, Cliques do AMO e Custo do AMO. |
| Plataformas de publicidade | Gráfico de rosca do custo das 2 plataformas principais (Google, Bing). |
| Totais de plataforma de publicidade | Tabela de forma livre das plataformas principais detalhadas por Impressões do AMO, Cliques do AMO, Custos do AMO, Posição média do AMO e Pontuação de qualidade do AMO. |
| Contas | Área de custo empilhada |
| Totais de conta | Tabela de forma livre das contas principais detalhadas pelas métricas associadas. |
| Campanhas | Gráfico de barras do custo de campanha. |
| Totais da campanha | Tabela de forma livre das campanhas principais detalhadas pelas métricas associadas. |
| Grupos | Mapa de árvore de custo |
| Totais de grupo | Tabela de forma livre dos grupos de anúncios principais detalhadas pelas métricas associadas. |
| Anúncios | Gráfico de barras horizontais de impressões, cliques e custo. |
| Totais de publicidade | Tabela em forma livre das publicidades principais detalhadas pelas métricas associadas. |
| Palavras-chave | Gráfico de dispersão de impressões, cliques e custo de todas as combinações de palavra-chave/tipo de correspondência. |
| Totais de palavra-chave | Tabela em forma livre das combinações de palavra-chave/tipo de correspondência principais detalhadas pelas métricas associadas. |

## Report Builder {#section_8E0371CF81144C33990D909685D1726E}

Assim que tiver configurado uma conta do Advertising Analytics, o relatório do Advertising Analytics será disponibilizado.
