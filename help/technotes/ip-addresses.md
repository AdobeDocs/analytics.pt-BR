---
title: IPs e domínios usados pela Adobe Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
translation-type: tm+mt
source-git-commit: 8986b30ca08224e2b992e8ed238e74e40e9a7b41
workflow-type: tm+mt
source-wordcount: '393'
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

## Todos os blocos de endereço IP da coleção de dados do Adobe Analytics

A tabela a seguir cobre todos os servidores de coleta de dados padrão e os servidores de coleta de dados regionais para o Adobe Analytics. Eles não incluem hosts AWS individuais.

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

O Adobe Analytics usa os Serviços Web da Amazon como parte de seu processo de coleta de dados. A tabela a seguir inclui hosts AWS reservados para a Adobe. Esses hosts **não** estão incluídos no intervalo de blocos de agregação acima.

| Localização | Host |
| --- | --- |
| Austrália | `13.238.77.77` |
| Austrália | `52.62.21.192` |
| Austrália | `54.66.152.159` |
| China | `52.81.111.133` |
| China | `140.179.22.22` |
| França | `15.237.76.117` |
| França | `15.237.136.106` |
| França | `35.181.18.61` |
| Índia | `65.0.114.116` |
| Índia | `65.0.115.179` |
| Índia | `65.0.25.111` |
| Irlanda | `18.202.158.78` |
| Irlanda | `54.72.205.114` |
| Irlanda | `54.78.36.71` |
| Oregon | `44.233.255.254` |
| Oregon | `44.237.54.118` |
| Oregon | `44.238.157.95` |
| Singapura | `52.220.116.94` |
| Singapura | `52.76.68.91` |
| Singapura | `54.179.114.68` |
| Tóquio | `18.182.161.178` |
| Tóquio | `54.168.58.167` |
| Tóquio | `54.178.61.109` |
| Virgínia | `3.213.168.181` |
| Virgínia | `3.219.249.186` |
| Virgínia | `3.220.129.153` |
| Virgínia | `18.206.109.10` |
| Virgínia | `18.211.197.67` |
| Virgínia | `34.227.41.189` |
| Virgínia | `34.228.124.176` |
| Virgínia | `54.90.190.103` |
| Virgínia | `54.174.149.161` |
