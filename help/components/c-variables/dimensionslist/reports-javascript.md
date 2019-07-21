---
description: Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como "não identificado".
seo-description: Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como "não identificado".
seo-title: Suporte a JavaScript
solution: Analytics
title: Suporte a JavaScript
topic: 'Relatórios  '
uuid: 7 b 95001 a-cd 35-478 a -8 b 24-54 d 30666110 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Suporte a JavaScript

Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como "não identificado".

>[!NOTE]
>
>In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

O relatório JavaScript corresponde ao javascript da coluna nos dados brutos.

javascript é um campo de nível de visita, portanto, o valor persiste desde a primeira ocorrência na visita. A coluna javascript tem por base o primeiro valor presente na coluna j_jscript (como um visit_referrer persistirá somente o primeiro referenciador da visita).

j_jscript é preenchido a partir do parâmetro j da solicitação de imagem do Adobe Analytics.

Exemplo:

| Ocorrência | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Como resultado, não importa se você tem uma versão do javascript especificada em algum ponto na visita, ela sempre será exibida como não Javascript, pois a primeira ocorrência não continha o valor de j_jscript.
