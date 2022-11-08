---
title: Coleta de dados regionais
description: Informação sobre a coleta de dados regionais
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 60c2422ef32a4fadbb975006c111d12878a98f53
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 90%

---

# Coleta de dados regionais

A Adobe Experience Cloud usa a RDC (Coleta de dados regionais) para que as interações entre os usuários finais e a Adobe Experience Cloud ocorram o mais próximo possível dos usuários finais. Isso melhora o desempenho do seu site/aplicativo e garante que os dados sejam coletados o mais rápido possível para otimizar a experiência do usuário final. Uma vez que os dados das propriedades digitais forem coletados regionalmente em um Centro de coleta de dados (DCC), eles serão transferidos por uma conexão segura para um Centro de processamento de dados (DPC), onde serão processados e disponibilizados para os produtos na Adobe Experience Cloud.

>[!IMPORTANT]
>
>O pacote de complemento RDC da China (Otimização de desempenho na China) é um complemento pago do Adobe Analytics. A Otimização de desempenho na China continental permite que os usuários da China enviem esses dados diretamente para a coleta de Adobe dentro da China, em vez de para o mundo inteiro. Isso melhora os tempos de carregamento de páginas e a precisão dos dados em comparação ao envio de dados para nós fora da China. Observe que, em última análise, os dados são transferidos para um dos Adobe Data Processing Center (DPC) fora da China. Entre em contato com o representante da Adobe Sales para obter mais informações.

Atualmente, a RDC inclui as seguintes localidades (sujeito a mudança):

## Coleta de dados de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Padrão | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney, China* |

*O RDC da China exige o pacote do complemento da China. Consulte a nota &quot;Importante&quot; acima.

>[!NOTE]
>
>Se sua solicitação de imagem do Analytics for enviada para os endpoints `adobedc` `2o7.net` ou `omtrdc.net`, ocorrerá coleta de dados por terceiros. É possível determinar isso se um desses endpoints aparecerem no URL das solicitações.

## Coleta de dados primária

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Global (Padrão) | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |
| Global + China* | China*, Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |
| Somente Américas | Oregon, Virgínia |
| Somente Europa | Irlanda, Paris |
| Somente Pacífico Asiático | Mumbai, Singapura, Tóquio, Sidney |
| Somente China* | Pequim |

*Somente China e RDCs do tipo Global + China exigem o pacote de complemento para a China. Consulte a nota &quot;Importante&quot; acima. Global + China roteará os dados originados na China para nossa RDC da China, enquanto os dados originados fora da China serão roteados para a RDC mais próxima fora da China.

>[!NOTE]
>
>A Experience Edge Global oferece o melhor desempenho aos usuários finais.  Se quiser usar um tipo alternativo de RDC, entre em contato com o Atendimento ao cliente da Adobe para obter assistência.

## Benefícios da RDC

| Benefícios | Descrição |
| --- | --- |
| Desempenho | Com a RDC, seus visitantes se conectam ao DCC mais próximo. Isso fornece o tempo de resposta mais rápido, resultando em rastreamento mais preciso e em tempos de carregamento mais rápidos. |
| Redundância | No caso de uma interrupção na comunicação entre o DCC e sua DPC, a infraestrutura da RDC da Adobe salva os dados localmente e, em seguida, os encaminha para a DPC quando as comunicações são restauradas. |

## Como a RDC funciona

A lista a seguir descreve o processo de coleta de dados usado pela Adobe:

1. A DNS corrige automaticamente o nome de host da coleta para o endereço IP do Centro de coleta de dados mais próximo do visitante.
1. O visitante envia os dados para o local.
1. Os dados são encaminhados imediatamente por meio de uma conexão segura para o Centro de processamento de dados, onde é processado e disponibilizado para os produtos na Adobe Experience Cloud.
