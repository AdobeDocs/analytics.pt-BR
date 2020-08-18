---
title: IPs e domínios usados no Adobe Experience Cloud
description: Se o firewall da sua organização bloquear endereços IP originados do Adobe, use esta lista para atualizar as configurações do firewall.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 12%

---


# IPs e domínios usados no Adobe Experience Cloud

Alguns endereços IP de firewall provenientes de configurações de dados do Adobe bloqueiam servidores ou servidores responsáveis pelo acesso aos dados. A lista de blocos de endereço IP a seguir cobre os endereços conhecidos atualmente envolvidos no Adobe Experience Cloud. Você pode usar essa lista de intervalos para alterar as configurações de firewall da sua organização para permitir acesso e enviar dados de dentro da organização.

>[!IMPORTANT]
>
>Embora a Adobe faça o melhor para manter esse documento atualizado, ela não pode garantir que a lista de intervalos IP permaneça a mesma. As possíveis mudanças no registro comercial, a expansão do registro da Internet requer mudanças no espaço de endereço IP do Adobe ou paradas de funcionamento do provedor de serviço da Internet.

## Permitir domínios de tecnologia dependentes

A Adobe Analytics usa os seguintes hosts para melhorar o desempenho e a experiência do produto. O Adobe recomenda adicionar esses domínios à lista de permissões do firewall para obter uma experiência ideal com o Adobe Analytics.

| Tecnologia | Domínio |
| --- | --- |
| Domínio Adobe Analytics | `adobe.com` |
| Domínio herdado do Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Armazenamento Blob do Microsoft Azure | `awaascicdprodva7.blob.core.windows.net` |
| CDN do Microsoft Azure | `aauicdnva7.azureedge.net` |

## Todos os blocos de endereço IP Adobe

A tabela a seguir cobre todos os endereços IP públicos da Adobe Experience Cloud de propriedade da Adobe. Esses intervalos incluem servidores de coleta de dados padrão e servidores de coleta de dados regionais para a Adobe Analytics. Eles não incluem hosts AWS individuais.

Muitos dos serviços e recursos de Adobe compartilham blocos IP, no entanto, alguns têm seu próprio espaço dedicado. Os blocos que usam apenas uma solução são indicados como tal.

| Bloco IP (Notação CIDR) | Notas |
| --- | --- |
| `62.210.161.0/24` | Específico ao Adobe Campaign |
| `63.140.32.0/19` |  |
| `66.117.16.0/20` |  |
| `66.235.128.0/19` |  |
| `67.226.212.0/23` | Específico ao Adobe Advertising Cloud |
| `103.202.219.0/24` | Específico ao Adobe Advertising Cloud |
| `130.248.0.0/16` |  |
| `172.82.192.0/18` |  |
| `185.34.188.0/22` |  |
| `185.148.48.0/24` | Específico ao Adobe Advertising Cloud |
| `192.243.224.0/19` |  |
| `198.98.22.0/23` | Específico ao Adobe Advertising Cloud |
| `205.219.231.0/24` |  |
| `208.67.40.0/22` |  |
| `208.77.136.0/22` |  |
| `208.91.168.0/21` | Específico ao Adobe Advertising Cloud |

## Coleta de dados e blocos de endereço IP FTP

Se sua organização preferir permitir intervalos de endereço IP específicos, você poderá usar a tabela a seguir. Todos os intervalos desta seção estão incluídos na tabela acima.

| Localização | Intervalo IP (Notação CIDR) | Notas |
| --- | --- | --- |
| Amsterdã | `66.117.28.0/23` |  |
| Dallas | `205.219.231.0/24` |  |
| Dallas | `66.235.152.0/22` |  |
| Dallas | `66.235.140.0/22` |  |
| Dallas | `63.140.32.0/21` |  |
| Dallas | `172.82.208.0/22` |  |
| RAE de Hong Kong da China | `66.117.24.0/22` |  |
| Londres | `66.235.156.0/24` |  |
| Londres | `66.235.148.0/23` |  |
| Londres | `66.117.16.0/23` | Específico ao Adobe Campaign |
| Londres | `63.140.40.0/22` |  |
| Londres | `208.67.41.0/24` |  |
| Londres | `192.243.254.0/23` |  |
| Londres | `192.243.244.0/22` |  |
| Londres | `185.34.188.0/23` |  |
| Londres | `130.248.152.0/21` |  |
| Londres | `172.82.224.0/21` |  |
| Londres | `172.82.232.0/21` |  |
| Oregon | `192.243.240.0/22` |  |
| Oregon | `192.243.232.0/21` |  |
| Oregon | `192.243.224.0/21` |  |
| Oregon | `130.248.160.0/21` |  |
| Oregon | `130.248.148.0/22` |  |
| Oregon | `172.82.192.0/21` |  |
| Oregon | `172.82.216.0/21` |  |
| Paris | `62.210.161.0/24` | Específico ao Adobe Campaign |
| Paris | `66.117.18.0/23` | Específico ao Adobe Campaign |
| Paris | `208.67.40.0/24` |  |
| Singapura | `66.235.150.0/24` |  |
| Singapura | `66.235.130.0/23` |  |
| Singapura | `63.140.44.0/22` |  |
| Singapura | `208.67.43.0/24` |  |
| Singapura | `172.82.240.0/22` |  |
| Singapura | `172.82.246.0/23` |  |
| Singapura | `172.82.248.0/21` |  |
| San Jose | `66.117.20.0/24` |  |
| San Jose | `66.235.132.0/22` |  |
| San Jose | `130.248.128.0/22` |  |
| San Jose | `192.243.248.0/23` |  |
| San Jose | `172.82.200.0/22` |  |
| San Jose | `66.235.136.0/22` |  |
| San Jose | `208.91.175.0/24` |  |
| San Jose | `208.91.174.0/24` |  |
| San Jose | `208.91.169.0/24` |  |
| Sydney | `216.104.216.0/23` |  |
| Tóquio | `66.235.159.0/24` |  |
| Tóquio | `66.117.21.0/24` |  |
| Tóquio | `63.140.52.0/24` |  |
| Tóquio | `63.140.50.0/23` |  |
| Virgínia | `66.235.144.0/22` |  |
| Virgínia | `208.77.138.0/23` |  |
| Virgínia | `208.77.136.0/23` |  |
| Virgínia | `192.243.250.0/23` |  |
| Virgínia | `130.248.144.0/22` |  |
| Virgínia | `172.82.204.0/22` |  |
| Virgínia | `172.82.212.0/22` |  |
| Virgínia | Consulte Hosts AWS |  |

## Hosts AWS

Alguns recursos de Adobe usam os Serviços da Web da Amazon para coletar dados. A tabela a seguir inclui hosts AWS reservados para o Adobe. Esses hosts **não** estão incluídos no intervalo de blocos de agregação acima.

| Localização | Host |
| --- | --- |
| Austrália | `13.238.77.77` |
| Austrália | `52.62.21.192` |
| Austrália | `54.66.152.159` |
| França | `15.188.154.177` |
| França | `15.236.175.233` |
| França | `15.236.9.100` |
| Índia | `13.232.177.101` |
| Índia | `13.235.4.163` |
| Índia | `3.6.119.69` |
| Irlanda | `52.17.94.37` |
| Irlanda | `52.49.253.16` |
| Irlanda | `52.51.63.15` |
| Londres | `172.82.228.19` |
| Oregon | `52.42.60.49` |
| Oregon | `54.212.169.56` |
| Oregon | `54.214.170.191` |
| Singapura | `13.228.34.224` |
| Singapura | `18.136.20.161` |
| Singapura | `52.74.162.152` |
| Tóquio | `13.112.72.86` |
| Tóquio | `18.178.74.225` |
| Tóquio | `18.179.88.228` |
| Virgínia | `34.234.106.101` |
| Virgínia | `52.22.231.198` |
| Virgínia | `54.157.65.136` |
| Virgínia | `107.23.142.4` |
| Virgínia | `34.192.14.184` |
| Virgínia | `34.192.146.173` |
| Virgínia | `34.192.229.76` |
| Virgínia | `34.196.183.216` |
| Virgínia | `34.196.219.120` |
| Virgínia | `34.196.54.55` |
| Virgínia | `34.197.179.21` |
| Virgínia | `34.197.45.49` |
| Virgínia | `34.197.93.163` |
| Virgínia | `34.198.80.27` |
| Virgínia | `34.199.102.192` |
| Virgínia | `34.199.46.40` |
| Virgínia | `34.199.99.62` |
| Virgínia | `34.200.67.35` |
| Virgínia | `34.204.146.235` |
| Virgínia | `34.204.164.1` |
| Virgínia | `34.204.27.249` |
| Virgínia | `34.205.224.111` |
| Virgínia | `34.206.69.71` |
| Virgínia | `52.193.88.44` |
| Virgínia | `52.200.108.250` |
| Virgínia | `52.200.171.156` |
| Virgínia | `52.201.49.195` |
| Virgínia | `52.205.244.105` |
| Virgínia | `52.207.161.156` |
| Virgínia | `52.22.148.55` |
| Virgínia | `52.4.155.255` |
| Virgínia | `52.72.182.205` |
| Virgínia | `52.72.185.111` |
| Virgínia | `54.152.218.194` |
| Virgínia | `54.173.37.66` |
| Virgínia | `54.173.69.38` |
| Virgínia | `54.236.180.248` |
| Virgínia | `54.236.71.218` |
| Virgínia | `54.80.103.29` |
| Virgínia | `54.88.180.124` |
