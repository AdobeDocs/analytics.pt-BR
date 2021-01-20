---
title: Perguntas frequentes sobre a identificação de visitantes entre dispositivos
description: Perguntas frequentes sobre identificação de visitantes entre dispositivos
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 89%

---


# Perguntas frequentes sobre a identificação de visitantes entre dispositivos

Perguntas frequentes sobre a identificação de visitantes entre dispositivos.

**Qual é a diferença entre a identificação de visitantes entre dispositivos e o Cross-Device Analytics?**

A identificação de visitantes entre dispositivos usa a variável `visitorID` para unir dispositivos, com várias limitações principais. Uma das maiores limitações desse método é que as ocorrências não autenticadas são isoladas, a menos que o dispositivo já tenha sido reconhecido. Essas ocorrências não autenticadas podem aumentar as contagens de visitantes únicos.

O Cross-Device Analytics é o método mais recente de identificação de visitantes entre dispositivos. Ela usa o serviço da Experience Cloud ID e o gráfico de dispositivos para unir retroativamente as visitas de diferentes dispositivos. A CDA requer o uso da função `setCustomerIDs` para determinar quais dispositivos são usados pelo mesmo visitante.

**Como a identificação de visitantes entre dispositivos lida com segmentos?**

A identificação de visitantes entre dispositivos trata segmentos de forma semelhante a outros recursos. Ela verifica cada ocorrência individual para ver se corresponde aos critérios do segmento e inclui essas ocorrências nos dados, se corresponderem. Os segmentos que usam contêineres baseados em visita e visitantes ainda analisam a ID do visitante. Certifique-se de que a implementação use a variável `visitorID` sempre que possível para identificar de forma consistente visitantes únicos para segmentação.
