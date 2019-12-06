---
title: Perguntas frequentes sobre identificação de visitantes em vários dispositivos
description: Perguntas frequentes sobre identificação de visitantes em vários dispositivos
translation-type: tm+mt
source-git-commit: 3e2f0bccbe7183ea75b12b1ef2b5afdd87837629

---


# Perguntas frequentes sobre a identificação de visitantes em vários dispositivos

Perguntas frequentes sobre a identificação de visitantes entre dispositivos.

**Qual é a diferença entre a identificação de visitantes entre dispositivos e o Analytics entre dispositivos?**

A identificação de visitantes entre dispositivos usa a `visitorID` variável para unir dispositivos, com várias limitações principais. Uma das maiores limitações desse método de identificação é que as ocorrências não autenticadas são isoladas, a menos que o dispositivo já tenha sido reconhecido. Essas ocorrências não autenticadas podem aumentar suas contagens de visitantes únicos.

O Analytics entre dispositivos é o mais recente método de identificação de visitantes entre dispositivos da Adobe. Ele usa o serviço da Experience Cloud ID e o gráfico de dispositivos para unir retroativamente as visitas de diferentes dispositivos. O CDA requer o uso da `setCustomerIDs` função para determinar quais dispositivos são usados pelo mesmo visitante.

**Como a identificação de visitantes entre dispositivos lida com segmentos?**

A identificação de visitantes entre dispositivos trata segmentos de forma semelhante a outros recursos. Ele verifica cada ocorrência individual para ver se corresponde aos critérios do segmento e inclui essas ocorrências nos dados, se corresponderem. Segmentos que usam contêineres baseados em visita e visitantes ainda analisam a ID do visitante. Certifique-se de que sua implementação use a `visitorID` variável sempre que possível para identificar de forma consistente visitantes únicos para segmentação.
