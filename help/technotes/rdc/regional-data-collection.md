---
title: Coleta de dados regionais
description: Informação sobre a coleta de dados regionais
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 8f02656820ed0b9201f29fc9dca6870e6f7fe8fd
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 37%

---

# Coleta de dados regionais

A Adobe Experience Cloud usa a RDC (Coleta de dados regionais) para que as interações entre seus visitantes e o Adobe ocorram o mais próximo possível de seus visitantes. Depois que os dados são coletados regionalmente em um Centro de coleta de dados (DCC), eles são encaminhados por uma conexão segura para um Centro de processamento de dados (DPC). Após o processamento, os dados ficam disponíveis para produtos na Adobe Experience Cloud.

O processo de coleta de dados regional usa as seguintes etapas:

1. O DNS resolve automaticamente o nome do host da coleção para o endereço IP do Centro de coleta de dados mais próximo do visitante.
1. O visitante envia os dados para o local.
1. Os dados são encaminhados imediatamente por meio de uma conexão segura para o Centro de processamento de dados, onde é processado e disponibilizado para os produtos na Adobe Experience Cloud.

O uso da coleta de dados regional oferece vários benefícios:

* **Desempenho**: com a RDC, seus visitantes se conectam ao DCC mais próximo. Essa otimização fornece o tempo de resposta mais rápido, resultando em rastreamento mais preciso e em tempos de carregamento mais rápidos.
* **Redundância**: Se houver uma interrupção na comunicação entre o DCC e o DPC, a infraestrutura do RDC do Adobe salva os dados localmente e, em seguida, os encaminha para o DPC quando as comunicações forem restauradas.

Atualmente, a RDC inclui as seguintes localidades (sujeito a mudança):

## Coleta de dados de terceiros

| Tipo da RDC | Centros de coleta de dados |
| --- | --- |
| Padrão | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney, China* |

{style="table-layout:auto"}

*O RDC da China exige o pacote do complemento da China. Consulte [Otimização do desempenho da China](#china-performance-optimization) abaixo.

>[!NOTE]
>
>Se sua solicitação de imagem do Analytics for enviada para os endpoints `adobedc` `2o7.net` ou `omtrdc.net`, ocorrerá coleta de dados por terceiros. É possível determinar isso se um desses endpoints aparecerem no URL das solicitações.

## Coleta de dados primária

| Tipo da RDC | Centros de coleta de dados |
| --- | --- |
| Global (Padrão) | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |
| Global + China* | China*, Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |
| Somente Américas | Oregon, Virgínia |
| Somente Europa | Irlanda, Paris |
| Somente Pacífico Asiático | Mumbai, Singapura, Tóquio, Sidney |
| Somente China* | Pequim |

{style="table-layout:auto"}

*Somente China e RDCs do tipo Global + China exigem o pacote de complemento para a China. Global + China roteia dados originários da China para a RDC da China Adobe, enquanto os dados originários da China são roteados para a RDC mais próxima fora da China. Consulte [Otimização do desempenho da China](#china-performance-optimization) abaixo.

## Otimização do desempenho da China

O pacote complementar RDC da China (Otimização de desempenho na China) é um complemento pago do Adobe Analytics. A otimização de desempenho do Adobe na China continental permite que clientes na China enviem esses dados diretamente para servidores de coleta de dados do Adobe na China, em vez de outros locais globalmente. Essa otimização melhora os tempos de carregamento de página e a precisão dos dados em relação ao envio de dados para locais fora da China. Os dados são transferidos para um dos Centros de processamento de dados (DPCs) do Adobe fora da China. Entre em contato com o representante de vendas da Adobe para obter mais informações.

>[!NOTE]
>
>O pacote complementar RDC da China não é compatível com o [SDK da Web](/help/implement/aep-edge/overview.md).

