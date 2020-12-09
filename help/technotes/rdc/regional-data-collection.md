---
title: Coleta de dados regionais
description: Informação sobre a coleta de dados regionais
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 77%

---


# Coleta de dados regionais

A Adobe Experience Cloud usa a RDC (Coleta de dados regionais) para que as interações entre os usuários finais e a Adobe Experience Cloud ocorram o mais próximo possível dos usuários finais. Isso melhora o desempenho do seu site/aplicativo e garante que os dados sejam coletados o mais rápido possível para otimizar a experiência do usuário final. Uma vez que os dados das propriedades digitais forem coletados regionalmente em um Centro de coleta de dados (DCC), eles serão transferidos por uma conexão segura para um Centro de processamento de dados (DPC), onde serão processados e disponibilizados para os produtos na Adobe Experience Cloud.

>[!IMPORTANT]
>
>O Pacote Complemento RDC (Otimização do Desempenho da China) é um complemento cobrado da Adobe Analytics. A Otimização do Desempenho do Adobe na China continental permite que os clientes na China enviem dados diretamente para o nó de fronteira da China, em vez de outros locais globalmente. Isso melhora o tempo de carregamento da página e a precisão dos dados ao enviar os dados para nós fora da China. Entre em contato com seu representante de vendas de Adobe para obter mais informações.

Atualmente, a RDC inclui as seguintes localidades (sujeitas a mudança)

## Coleta de dados HTTP e de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Padrão | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |

Note: If your Analytics image request is sent to the `adobedc`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. É possível determinar se um desses endpoints aparecem na URL de suas solicitações.

## Coleta de dados HTTPS de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Global (Padrão) | Oregon, Virgínia, Irlanda, Paris, Mumbai, Singapura, Tóquio, Sydney |
| Somente Américas | Oregon, Virgínia |
| Somente Europa | Irlanda, Paris |
| Somente Pacífico Asiático | Mumbai, Singapura, Tóquio, Sidney |

Observação: a Experience Edge Global oferece o melhor desempenho aos usuários finais.  Se quiser usar um tipo da RDC alternativo, entre em contato com o Atendimento ao cliente da Adobe para obter assistência.

## Como a RDC funciona

A lista a seguir descreve o processo de coleta de dados usado pela Adobe:

1. A DNS corrige automaticamente o nome de host da coleta para o endereço IP do Centro de coleta de dados mais próximo do visitante.
1. O visitante envia os dados para o local.
1. Os dados são encaminhados imediatamente por meio de uma conexão segura para o Centro de processamento de dados, onde é processado e disponibilizado para os produtos na Adobe Experience Cloud.
