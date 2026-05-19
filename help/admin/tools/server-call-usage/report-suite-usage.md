---
description: A guia de Uso de conjuntos de relatórios proporciona dados de uso do servidor referentes a cada conjunto de relatórios em todas as empresas de Logon vinculadas à sua empresa de Faturamento, para o período de uso atual.
title: Visualizar uso do conjunto de relatórios
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
role: Admin
TQID: https://experienceleague.adobe.com/reCYMlZM7HH2H1ewI6tN6x6Bn4ghaKKyrkXGUzC64-g
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 44%

---

# Visualizar uso do conjunto de relatórios

A guia de Uso de conjuntos de relatórios proporciona dados de uso do servidor referentes a cada conjunto de relatórios em todas as empresas de Logon vinculadas à sua empresa de Faturamento, para o período de uso atual.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Uso de chamadas do servidor]** > **[!UICONTROL Uso de conjuntos de relatórios]**

>[!IMPORTANT]
>
>Se um conjunto de relatórios não estiver vinculado a uma organização da CX Enterprise, os respectivos dados de uso não serão refletidos neste painel. Além disso, uma ID de cobrança pode estar vinculada a várias organizações CX Enterprise; nem sempre há uma relação 1:1 entre uma organização e uma ID de cobrança.

O painel de Uso do conjunto de relatórios

* Mostra o uso de chamadas do servidor do período de uso atual (Todas as chamadas, Primárias, Secundárias, Primárias móveis, Secundárias móveis) para cada conjunto de relatórios na sua organização CX Enterprise.
* Mostra o percentual de uso geral por categoria de chamada de servidor.
* É atualizado diariamente.
* É baixável.
* Permite acessar a interface **[!UICONTROL Gerenciar alertas]**.

![](/help/admin/tools/server-call-usage/assets/report-suite-usage.png)

## Configurações do painel {#settings}

| Coluna | Definição |
|--- |--- |
| Nome do conjunto de relatórios | Nome amigável do conjunto de relatórios |
| Todas as chamadas (% do total) | Todas as chamadas do servidor efetuadas no período de uso atual. |
| Chamadas Primárias (%) | Todas as chamadas do servidor primário (e sua porcentagem do total) ocorreram no período de uso atual. |
| Chamadas Secundárias (%) | Todas as chamadas do servidor secundárias (e sua porcentagem do total) ocorreram no período de uso atual. |
| Principal móvel (%) | Todas as chamadas do servidor primário móvel (e sua porcentagem do total) incorridas no período de uso atual. |
| Secundário móvel (%) | Todas as chamadas do servidor secundário móvel (e sua porcentagem do total) incorridas no período de uso atual. |

{style="table-layout:auto"}

## Baixar relatório de dados {#download}

Essa opção permite baixar dados de uso atuais e dados de períodos anteriores ao período de uso atual (desde janeiro de 2015). O relatório é baixado como um arquivo .csv.

1. Selecione pelo menos um conjunto de relatórios.
1. Clique em **[!UICONTROL Baixar relatório]**.

   ![](/help/admin/tools/server-call-usage/assets/download_report.png)

| Elemento do relatório | Descrição |
|--- |--- |
| Nome do arquivo | Nome codificado: Relatório de uso `day and time of report creation.csv` |
| Conjuntos de relatórios incluídos | Todos os conjuntos de relatórios selecionados na página Uso do servidor de relatórios são incluídos nessa lista. |
| Tipos de chamada incluídos | Especifique qualquer combinação destes: Todas as chamadas (padrão), Primárias, Secundárias, Primárias móveis, Secundárias móveis. |
| Intervalo de tempo | É possível escolher o período de uso atual ou especificar um intervalo personalizado.  Para um intervalo personalizado, especifique o Início do intervalo e o Término do intervalo. <br>**Observação:** não é possível baixar dados de uso anteriores a janeiro de 2015 </br>. |

{style="table-layout:auto"}

1. Clique em **[!UICONTROL Baixar]**.

Esta é uma captura de tela da aparência do arquivo .csv baixado. Inclui uma coluna para a ID do conjunto de relatórios. A ID do conjunto de relatórios especifica uma ID exclusiva que pode conter apenas caracteres alfanuméricos. Essa ID não pode ser alterada após a criação de um conjunto de relatórios.

![](/help/admin/tools/server-call-usage/assets/download-usage.png)
