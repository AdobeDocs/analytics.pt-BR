---
title: Endereços IP usados pelo Adobe Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 32%

---

# Endereços IP usados pelo Adobe Analytics

Algumas configurações de firewall bloqueiam endereços IP dos servidores de coleção de dados da Adobe ou dos servidores responsáveis por acessar os dados do Você pode usar essa lista de intervalos para alterar as configurações de firewall da sua organização para permitir acesso e enviar dados de dentro da organização.

Todos os endereços IP usados pelo Adobe Analytics fazem parte dos [endereços IP usados pelo CX Enterprise](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/ip-addresses), com exceção do pacote complementar para Otimização de desempenho na China.

## Endereços IP de Otimização de desempenho da China

O pacote complementar para Otimização de desempenho na China é um serviço pago adicional que melhora o desempenho da coleta de dados do AppMeasurement para visitantes na China. Entre em contato com a equipe de conta da Adobe para saber mais sobre como usar esse recurso.

>[!IMPORTANT]
>
>O RDC da China não está disponível para a coleta de dados do Web SDK. Esses servidores se aplicam somente às bibliotecas AppMeasurement.

Os servidores de coleta de dados regionais na China usam os seguintes endereços IP:

| Localização | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[Endereços IP usados pelo CX Enterprise](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domínios usados pelo Adobe Analytics](domains.md)
