---
title: Perguntas frequentes sobre a identificação de visitantes entre dispositivos
description: Perguntas frequentes sobre identificação de visitantes entre dispositivos
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Perguntas frequentes sobre a identificação de visitantes entre dispositivos

Perguntas frequentes sobre identificação de visitantes entre dispositivos.

+++Qual é a diferença entre a identificação de visitantes em vários dispositivos e o Cross-Device Analytics?
A identificação de visitantes entre dispositivos usa a variável `visitorID` para unir dispositivos, com várias limitações principais. Uma das maiores limitações desse método é que as ocorrências não autenticadas são isoladas, a menos que o dispositivo já tenha sido reconhecido. Essas ocorrências não autenticadas podem aumentar as contagens de visitantes únicos.

O Cross-Device Analytics é o mais recente método de identificação de visitantes em vários dispositivos da Adobe. Ela usa o serviço da Experience Cloud ID e o gráfico de dispositivos para unir retroativamente as visitas de diferentes dispositivos. A CDA requer o uso da função `setCustomerIDs` para determinar quais dispositivos são usados pelo mesmo visitante.
+++

+++Como a identificação de visitantes em vários dispositivos lida com segmentos?
A identificação de visitantes entre dispositivos trata segmentos de forma semelhante a outros recursos. Ela verifica cada ocorrência individual para ver se corresponde aos critérios do segmento e inclui essas ocorrências nos dados, se corresponderem. Os segmentos que usam contêineres baseados em visita e visitantes ainda analisam a ID do visitante. Certifique-se de que a implementação utiliza a variável `visitorID` sempre que possível para identificar de forma consistente os visitantes únicos para segmentação.
+++
