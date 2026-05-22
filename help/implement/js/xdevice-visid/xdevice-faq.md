---
title: Perguntas frequentes sobre a identificação de visitantes entre dispositivos
description: Perguntas frequentes sobre identificação de visitantes entre dispositivos
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: 'https://experienceleague.adobe.com/RBciiyfaq671zJ51QdJJDXcekFr-lfq0WPY0UAuWoVA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# Perguntas frequentes sobre a identificação de visitantes entre dispositivos

Perguntas frequentes sobre a identificação de visitantes entre dispositivos.

+++Qual é a diferença entre a identificação de visitantes em vários dispositivos e o Cross-Device Analytics?
A identificação de visitantes entre dispositivos usa a variável `visitorID` para unir dispositivos, com várias limitações principais. Uma das maiores limitações desse método é que as ocorrências não autenticadas são isoladas, a menos que o dispositivo já tenha sido reconhecido. Essas ocorrências não autenticadas podem aumentar as contagens de visitantes únicos.

O Cross-Device Analytics é o mais recente método de identificação de visitantes em vários dispositivos da Adobe. Ele usa o serviço da Experience Cloud ID e a compilação em campo para compilar retroativamente as visitas de diferentes dispositivos. A CDA requer o uso da função `setCustomerIDs` para determinar quais dispositivos são usados pelo mesmo visitante.
+++

+++Como a identificação de visitantes entre dispositivos lida com segmentos?
A identificação de visitantes entre dispositivos trata segmentos de forma semelhante a outros recursos. Ela verifica cada ocorrência individual para ver se corresponde aos critérios do segmento e inclui essas ocorrências nos dados, se corresponderem. Os segmentos que usam contêineres baseados em visita e visitantes ainda analisam a ID do visitante. Certifique-se de que a implementação utiliza a variável `visitorID` sempre que possível para identificar de forma consistente os visitantes únicos para segmentação.
+++
