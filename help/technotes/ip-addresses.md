---
title: IPs e domínios usados pelo Adobe Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 4c5eb7c7704a31b2d43476e1db174da473cb1d4d
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 67%

---

# IPs e domínios usados pelo Adobe Analytics

Algumas configurações de firewall bloqueiam endereços IP dos servidores de coleção de dados da Adobe ou dos servidores responsáveis por acessar os dados do Você pode usar essa lista de intervalos para alterar as configurações de firewall da sua organização para permitir acesso e enviar dados de dentro da organização. Esta página inclui sistemas de entrada (como a coleta de dados) e sistemas de saída (como feeds de dados) que o Adobe usa.

>[!IMPORTANT]
>
>Embora o Adobe faça o possível para manter esse documento atualizado, não é possível garantir que a lista de intervalos IP permaneça a mesma. As possíveis alterações incluem o crescimento e a expansão dos negócios, um registro da Internet exige alterações no espaço de endereço IP da Adobe ou um provedor de serviços de Internet deixa de funcionar.

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

## Todos os blocos de endereço IP do Adobe Analytics

A tabela a seguir abrange todos os endereços IP de propriedade de Adobe usados para o Adobe Analytics. Eles não incluem todos os serviços hospedados em nuvens públicas.

| Bloco IP (Notação CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `172.82.192.0/18` |
| `185.34.188.0/22` |
| `192.243.240.0/22` |

## Coleta de dados e blocos de endereço IP de FTP

Se sua organização preferir permitir intervalos de endereços IP específicos, você pode usar a tabela a seguir. Todos os intervalos desta seção estão incluídos na tabela acima. As conexões FTP para o Data Warehouse e Feeds de dados são originadas apenas de Londres, Oregon e Singapura.

| Localização | Intervalo IP (Notação CIDR) |
| --- | --- |
| Austrália | `63.140.55.0/24` |
| Austrália | `63.140.56.0/23` |
| Califórnia | `63.140.32.0/23` |
| Califórnia | `63.140.34.0/24` |
| França | `63.140.62.0/23` |
| Índia | `66.117.20.0/24` |
| Índia | `66.117.22.0/23` |
| Japão | `130.248.169.0/23` |
| Japão | `63.140.50.0/23` |
| Japão | `66.117.31.0/24` |
| Londres | `66.235.156.0/24` |
| Londres | `185.34.188.0/22` |
| Londres | `130.248.152.0/22` |
| Londres | `130.248.244.0/23` |
| Oregon | `66.235.132.0/22` |
| Oregon | `130.248.130.0/23` |
| Oregon | `130.248.150.0/24` |
| Oregon | `130.248.160.0/21` |
| Oregon | `192.243.242.0/24` |
| Singapura | `130.248.170.0/23` |
| Singapura | `130.248.240.0/24` |
| Singapura | `63.140.44.0/22` |
| Singapura | `63.140.48.0/23` |
| Singapura | `66.117.30.0/24` |
| Singapura | `172.82.240.8/29` |
| Singapura | `172.82.240.88/29` |
| Virgínia | `63.140.38.0/23` |
| Virgínia | `63.140.54.0/24` |

## Hosts AWS

O Adobe Analytics usa os Serviços Web da Amazon como parte de seu processo de coleção de dados. A tabela a seguir inclui endereços de host IPv4 da AWS reservados para o Adobe. Esses hosts **não** estão incluídos no intervalo de blocos de agregação acima.

| Localização | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

A tabela a seguir inclui os blocos de endereço IPv6 do AWS usados pelo Adobe. Esses hosts **não** estão incluídos no intervalo de blocos de agregação acima.

| Localização | Host |
| --- | --- |
| Austrália | `2406:da1c:406:1a00::/56` |
| Austrália | `2406:da1c:ce5:b400::/56` |
| Califórnia | `2600:1f1c:366:d900::/56` |
| França | `2a05:d012:706:d000::/56` |
| Índia | `2406:da1a:f34:6a00::/56` |
| Irlanda | `2a05:d018:309:600::/56` |
| Japão | `2406:da14:b07:ab00::/56` |
| Oregon | `2600:1f14:1eb:7d00::/56` |
| Oregon | `2600:1f14:9d3:2b00::/56` |
| Singapura | `2406:da18:6e8:1e00::/56` |
| Virgínia | `2600:1f18:1a20:e800::/56` |
| Virgínia | `2600:1f18:4fd:6000::/56` |
| Virgínia | `2600:1f18:b00:e100::/56` |
| Virgínia | `2600:1f18:d1f:bd00::/56` |
