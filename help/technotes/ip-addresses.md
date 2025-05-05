---
title: Endereços IP usados pelo Adobe Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 35%

---

# Endereços IP usados pelo Adobe Analytics

Algumas configurações de firewall bloqueiam endereços IP dos servidores de coleção de dados da Adobe ou dos servidores responsáveis por acessar os dados do Você pode usar essa lista de intervalos para alterar as configurações de firewall da sua organização para permitir acesso e enviar dados de dentro da organização.

Todos os endereços IP usados pelo Adobe Analytics fazem parte de [endereços IP usados pelo Adobe Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/ip-addresses), com exceção do pacote complementar para Otimização de Desempenho na China.

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

>[!MORELIKETHIS]
>
>[Endereços IP usados pelo Adobe Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domínios usados pelo Adobe Analytics](domains.md)
