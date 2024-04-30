---
title: IPs e domínios usados pelo Adobe Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 32%

---

# IPs e domínios usados pelo Adobe Analytics

Algumas configurações de firewall bloqueiam domínios dos quais a Adobe Analytics depende para sua interface de produto. Você pode usar essa lista de domínios para alterar as configurações de rede de sua organização para permitir o acesso ao produto de dentro da organização.

## Permitir domínios de tecnologia dependentes

O Adobe Analytics usa os seguintes hosts para melhorar o desempenho e a experiência do produto. A Adobe recomenda permitir esses domínios por meio do firewall da sua organização para obter uma experiência ideal com o Adobe Analytics.

| Tecnologia | Domínio |
| --- | --- |
| Domínios do Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Domínio herdado do Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Armazenamento Microsoft Azure Blob | `awaascicdprodva7.blob.core.windows.net` |
| CDN do Microsoft Azure | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Blocos de endereço IP do Adobe Experience Cloud

Além dos domínios acima, o Adobe Analytics depende de vários blocos de endereço IP para a coleta de dados e a exportação de relatórios.

Consulte Endereços IP da Adobe Experience Cloud para obter a lista completa de intervalos IP.

## Endereços IP de Otimização de desempenho da China

O pacote complementar para Otimização de desempenho na China é um serviço pago adicional que melhora o desempenho da coleta de dados do AppMeasurement para visitantes na China. Entre em contato com a equipe de conta do Adobe para saber mais sobre como usar esse recurso.

>[!IMPORTANT]
>
>O RDC da China não está disponível para a coleta de dados do SDK da Web. Esses servidores se aplicam somente às bibliotecas do AppMeasurement.

Os servidores de coleta de dados regionais na China usam os seguintes endereços IP:

| Localização | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

{style="table-layout:auto"}
