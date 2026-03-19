---
title: Acesso único
description: O número de vezes que um item de dimensão não foi alterado em uma visita.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 15%

---

# Acesso único

A **[!UICONTROL métrica]** de [ de Acesso único](overview.md) mostra o número de visitas em que a dimensão de relatório aplicável continha apenas um único valor para uma visita inteira. É a versão mais ampla e específica da dimensão de [[!UICONTROL Visitas em única página]](single-page-visits.md). Essa métrica é útil no contexto de qualquer dimensão em que você deseja ver o valor de uma dimensão quando ele foi definido apenas uma vez durante uma visita.

## Como essa métrica é calculada

A definição dessa métrica depende da configuração do projeto de [[!UICONTROL Contar instâncias repetidas]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **Contar instâncias repetidas habilitado**: conta visitas em que a dimensão contém exatamente um valor em uma visita. Se a dimensão persistir, ela não se qualificará mais como um único acesso.
* **Contar instâncias repetidas desabilitadas**: conta visitas em que a dimensão contém um único valor exclusivo. É possível definir o item de dimensão com o mesmo valor várias vezes ou mantê-lo e ele ainda será contado como um único acesso.

Independentemente de &#39;[!UICONTROL Contar instâncias repetidas]&#39;, a visita não se qualifica mais como um único acesso se a dimensão mudar para um segundo valor único. As chamadas de rastreamento de link são incluídas neste cálculo se a dimensão estiver definida nelas.

## Diferença entre &#39;[!UICONTROL Acesso único]&#39; e &#39;[!UICONTROL Visita de página única]&#39;

No contexto da dimensão [[!UICONTROL Página]](../dimensions/page.md), &#39;[!UICONTROL Acesso único]&#39; e &#39;[!UICONTROL Visitas de página única]&#39; são sempre exatamente idênticos, independentemente da configuração de projeto &#39;[!UICONTROL Contar instâncias repetidas]&#39;. As diferenças surgem quando se utilizam outras dimensões.

* **[!UICONTROL Acesso único]**: mostra o número de visitas em que determinado item de dimensão estava presente para uma única ocorrência. É contextual à dimensão utilizada no projeto.
* **[!UICONTROL Visita em única página]**: mostra o número de visitas em que a dimensão &#39;[!UICONTROL Página]&#39; estava presente para uma única ocorrência. Mesmo se outra dimensão for utilizada no relatório, ainda serão contabilizadas visitas com um único item de dimensão &quot;[!UICONTROL Página]&quot; exclusivo.

Se [[!UICONTROL Contar instâncias repetidas]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) estiver desabilitado, as definições de métrica serão levemente alteradas:

* **Acesso único**: mostra o número de visitas em que determinado item de dimensão não foi alterado em toda a visita.
* **Visita em única página**: mostra o número de visitas em que a dimensão &#39;[!UICONTROL Página]&#39; não foi alterada em toda a visita.

Por exemplo, considere o exemplo a seguir como visitas com duas ocorrências. A dimensão do relatório é [[!UICONTROL Seção do site]](../dimensions/site-section.md) e &#39;[!UICONTROL Contar instâncias repetidas]&#39; está desabilitada.

* Um visitante acessa duas páginas, mas ambas estão na mesma seção do site. Como a seção do site permaneceu a mesma durante a visita, é contabilizado um único acesso. Não conta como uma visita de página única porque a visita contém mais de um item de dimensão [!UICONTROL Página] exclusivo.
* Um visitante acessa duas páginas em seções diferentes do site, mas ambas têm o mesmo nome. A visita não conta como um único acesso porque havia dois valores exclusivos de seção do site. Conta como uma visita de página única porque havia um único item de dimensão [!UICONTROL Página] exclusivo.
