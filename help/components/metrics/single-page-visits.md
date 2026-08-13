---
title: Visitas em única página (métricas)
description: O número de vezes que o item de dimensão “Página” não foi alterado em uma visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
TQID: https://experienceleague.adobe.com/iDXuwf-Ls1N7VzmtZiMRISLbSEtHOtDTeoddfDEiAwA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 33%

---

# Visitas em única página

*Esta página de ajuda descreve como a dimensão “Visitas em única página” funciona como uma métrica. Consulte a dimensão [Visitas em única página](../dimensions/single-page-visits.md) para obter mais informações.*

A **[!UICONTROL Visitas em única página]** [métrica](overview.md) mostra o número de visitas em que o item de dimensão [Página](../dimensions/page.md) continha apenas um único valor para toda a visita. Essa métrica é útil no contexto de dimensões em que você deseja ver as visitas curtas, mas não tem regras tão rigorosas quanto [[!UICONTROL Rejeições]](bounces.md).

## Como essa métrica é calculada

A definição dessa métrica depende da configuração do projeto de [[!UICONTROL Contar instâncias repetidas]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **[!UICONTROL Contar instâncias repetidas] habilitado**: conta o número de visitas em que a dimensão [!UICONTROL Página] continha um único valor para a visita. Se um visitante recarregar a página, ele se desqualifica como uma visita de página única.
* **[!UICONTROL Contar instâncias repetidas] desabilitadas**: conta o número de visitas em que a dimensão [!UICONTROL Página] continha um único valor exclusivo para toda a visita.

Independentemente da configuração de projeto &#39;[!UICONTROL Contar instâncias repetidas]&#39;, essa métrica segue as seguintes regras:

* Uma visita ainda se qualifica como uma visita de página única se um visitante acionar chamadas de rastreamento de link (a dimensão [!UICONTROL Página] é removida de todas as chamadas de rastreamento de link).
* Assim que a dimensão [!UICONTROL Página] mudar para um segundo valor único, a visita não se qualificará mais como uma visita de página única.

Consulte [Acesso único](single-access.md) para obter uma comparação entre as métricas.
