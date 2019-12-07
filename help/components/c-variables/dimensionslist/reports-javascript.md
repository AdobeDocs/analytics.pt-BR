---
description: Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como "não identificado".
title: Suporte a JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suporte a JavaScript

Exibe métricas que se baseiam no fato de um dispositivo ter o JavaScript habilitado, desabilitado ou se é considerado como "não identificado".

> [!NOTE] No começo de novembro de 2016, pretendemos remover a restrição que lista o JavaScript como *`disabled / unidentified`* para dispositivos móveis.

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
