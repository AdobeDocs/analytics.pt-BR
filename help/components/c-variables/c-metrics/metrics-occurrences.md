---
description: O número de vezes em que um valor específico é capturado, além do número de exibições de página em que o valor dado persistiu. Em outras palavras, Ocorrências são a soma das exibições de página e dos eventos da página. As ocorrências estão disponíveis na Analysis Workspace e na Ad Hoc Analysis.
title: Ocorrências
topic: Metrics
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ocorrências

O número de vezes em que um valor específico é capturado, além do número de exibições de página em que o valor dado persistiu. Em outras palavras, Ocorrências são a soma das exibições de página e dos eventos da página. As ocorrências estão disponíveis na Analysis Workspace e na Ad Hoc Analysis.

## Comparação de instâncias e ocorrências {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Duas métricas que parecem ser semelhantes estão listadas:

**[Instâncias](/help/components/c-variables/c-metrics/metrics-instance.md)**: o número de vezes que um valor foi definido para uma variável.

**Ocorrências**: o número total de vezes que um valor foi definido ou persistido.

| Situação | Descrição |
|---|---|
| Ocorrências mais altas do que Instâncias | Isso é esperado de variáveis de conversão, já que ocorrências também inclui o número de vezes em que a variável foi definida (instâncias). |
| Instâncias mais altas do que Ocorrências | Isso não é possível em relatórios, pois todas as instâncias também são registradas como ocorrências. |
| Instâncias iguais a Ocorrências | Isso é o mais comum para variáveis de tráfego, que por natureza não persistem além da solicitação de imagem. |

>[!MORELIKETHIS]
>
>* [Instâncias](/help/components/c-variables/c-metrics/metrics-instance.md)

