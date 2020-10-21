---
title: IPs e domínios usados pela Adobe Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
translation-type: tm+mt
source-git-commit: a7955e7f6fd92fff7188711d8aef9526ebf3700f
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 86%

---


# IPs e domínios usados pela Adobe Analytics

Algumas configurações de firewall bloqueiam endereços IP dos servidores de coleção de dados da Adobe ou dos servidores responsáveis por acessar os dados do Você pode usar essa lista de intervalos para alterar as configurações de firewall da sua organização para permitir acesso e enviar dados de dentro da organização.

>[!IMPORTANT]
>
>Enquanto a Adobe faz o melhor para manter esse documento atualizado, não é possível garantir que a lista de intervalos IP permanecerá a mesma. As possíveis alterações incluem o crescimento e a expansão dos negócios, um registro da Internet exige alterações no espaço de endereço IP da Adobe ou um provedor de serviços de Internet deixa de funcionar.

## Permitir domínios de tecnologia dependentes

O Adobe Analytics usa os seguintes hosts para melhorar o desempenho e a experiência do produto. A Adobe recomenda adicionar esses domínios à lista de permissões do firewall para obter uma experiência ideal com o Adobe Analytics.

| Tecnologia | Domínio |
| --- | --- |
| Domínios Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Domínio herdado do Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Armazenamento Microsoft Azure Blob | `awaascicdprodva7.blob.core.windows.net` |
| CDN do Microsoft Azure | `aauicdnva7.azureedge.net` |

## Todos os blocos de endereço IP da Adobe Analytics

A tabela a seguir abrange todos os servidores de coleta de dados padrão e os servidores de coleta de dados regionais para a Adobe Analytics. Eles não incluem hosts AWS individuais.

| Bloco IP (Notação CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `172.82.192.0/18` |
| `185.34.188.0/22` |
| `192.243.224.0/19` |
| `205.219.231.0/24` |
| `208.67.40.0/22` |
| `208.77.136.0/22` |

## Coleta de dados e blocos de endereço IP de FTP

Se sua organização preferir permitir intervalos de endereços IP específicos, você pode usar a tabela a seguir. Todos os intervalos desta seção estão incluídos na tabela acima.

| Localização | Intervalo IP (Notação CIDR) |
| --- | --- |
| Amsterdã | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| RAE de Hong Kong da China | `66.117.24.0/22` |
| Londres | `66.235.156.0/24` |
| Londres | `66.235.148.0/23` |
| Londres | `63.140.40.0/22` |
| Londres | `208.67.41.0/24` |
| Londres | `192.243.254.0/23` |
| Londres | `192.243.244.0/22` |
| Londres | `185.34.188.0/23` |
| Londres | `130.248.152.0/21` |
| Londres | `172.82.224.0/21` |
| Londres | `172.82.232.0/21` |
| Oregon | `192.243.240.0/22` |
| Oregon | `192.243.232.0/21` |
| Oregon | `192.243.224.0/21` |
| Oregon | `130.248.160.0/21` |
| Oregon | `130.248.148.0/22` |
| Oregon | `172.82.192.0/21` |
| Oregon | `172.82.216.0/21` |
| Paris | `208.67.40.0/24` |
| Singapura | `66.235.150.0/24` |
| Singapura | `66.235.130.0/23` |
| Singapura | `63.140.44.0/22` |
| Singapura | `208.67.43.0/24` |
| Singapura | `172.82.240.0/22` |
| Singapura | `172.82.246.0/23` |
| Singapura | `172.82.248.0/21` |
| San Jose | `66.117.20.0/24` |
| San Jose | `66.235.132.0/22` |
| San Jose | `130.248.128.0/22` |
| San Jose | `192.243.248.0/23` |
| San Jose | `172.82.200.0/22` |
| San Jose | `66.235.136.0/22` |
| San Jose | `208.91.175.0/24` |
| San Jose | `208.91.174.0/24` |
| San Jose | `208.91.169.0/24` |
| Sydney | `216.104.216.0/23` |
| Tóquio | `66.235.159.0/24` |
| Tóquio | `66.117.21.0/24` |
| Tóquio | `63.140.52.0/24` |
| Tóquio | `63.140.50.0/23` |
| Virgínia | `66.235.144.0/22` |
| Virgínia | `208.77.138.0/23` |
| Virgínia | `208.77.136.0/23` |
| Virgínia | `192.243.250.0/23` |
| Virgínia | `130.248.144.0/22` |
| Virgínia | `172.82.204.0/22` |
| Virgínia | `172.82.212.0/22` |
| Virgínia | Consulte Hosts AWS |

## Hosts AWS

A Adobe Analytics usa os Amazon Web Services como parte de seu processo de coleta de dados. A tabela a seguir inclui hosts AWS reservados para a Adobe. Esses hosts **não** estão incluídos no intervalo de blocos de agregação acima.

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
| Oregon | `52.42.60.49` |
| Oregon | `54.212.169.56` |
| Oregon | `54.214.170.191` |
| Singapura | `13.228.34.224` |
| Singapura | `18.136.20.161` |
| Singapura | `52.74.162.152` |
| Tóquio | `13.112.72.86` |
| Tóquio | `18.178.74.225` |
| Tóquio | `18.179.88.228` |
| Virgínia | `3.220.129.153` |
| Virgínia | `18.211.197.67` |
| Virgínia | `34.228.124.176` |
| Virgínia | `34.234.106.101` |
| Virgínia | `52.22.231.198` |
| Virgínia | `54.157.65.136` |
| Virgínia | `3.213.168.181` |
| Virgínia | `3.219.249.186` |
| Virgínia | `34.227.41.189` |
