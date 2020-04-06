---
description: Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como "não identificado".
title: Suporte a JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Suporte a JavaScript

Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como &quot;não identificado&quot;.

>[!NOTE] No começo de novembro de 2016, pretendemos remover a restrição que lista o JavaScript como *`disabled / unidentified`* para dispositivos móveis.

O relatório JavaScript corresponde ao javascript da coluna nos dados brutos.

javascript é um campo de nível de visita, portanto, ele persiste o valor da primeira ocorrência na visita. A coluna javascript se baseia no primeiro valor presente na coluna j_jscript (como uma visit_quem indicou persistirá somente a primeira quem indicou da visita).

j_jscript é preenchido a partir do parâmetro j da solicitação de imagem do Adobe Analytics.

Exemplo:

| Ocorrência | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Como resultado, não importa se você tem uma versão javascript especificada em algum ponto da visita - ela sempre será exibida como não Javascript, pois a primeira ocorrência não continha nenhum valor para j_jscript.
