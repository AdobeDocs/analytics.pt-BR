---
title: Solução de problemas de sessões no Adobe Analytics
description: Saiba mais sobre como resolver problemas ao desconectar-se do Adobe Analytics.
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 99%

---

# Solução de problemas de sessões no Adobe Analytics

Esta página trata da solução de problemas de sessões, o que significa que você consegue fazer logon com êxito, mas tem problemas para continuar conectado. Se tiver problemas ao fazer logon no Adobe Analytics, consulte [Solução de problemas ao fazer logon no Adobe Analytics](troubleshoot-login.md).

Quase todos os problemas de sessões se originam da rede corporativa personalizada de uma organização. Se você conseguir fazer logon no Adobe Analytics, mas tiver problemas para permanecer conectado, use este artigo para ajudar a determinar a causa.

## Determine se o problema ocorre devido à rede de sua organização {#network}

Muitas organizações implantam recursos de rede adicionais para melhorar a segurança, como servidores de proxy ou firewalls. Às vezes, essas personalizações podem interferir na capacidade de manter uma sessão ativa no Adobe Analytics.

Para determinar se a rede corporativa à qual você está conectado está causando problemas quando você usa o Adobe Analytics, use suas credenciais de logon da Experience Cloud em um dispositivo fora da rede corporativa. Exemplos de dispositivos podem ser: conectar-se pela sua rede doméstica ou pelo plano de dados de um dispositivo móvel. Se você conseguir transitar de uma página para outra sem ter sido desconectado, a rede de sua organização provavelmente será o motivo de ser desconectado do Adobe Analytics.

## Problemas de proxy {#proxy}

A Adobe usa um cabeçalho de autorização ao fazer solicitações à Adobe. Alguns proxies, como o Edge Secure Web Gateway (antigo Bluecat), removem informações críticas do cabeçalho de autorização usadas pelo Adobe Analytics. Quando a Adobe não vê o cabeçalho de autorização, a sessão expira.

Para resolver esse problema, a Adobe recomenda trabalhar com a equipe de TI de sua organização para permitir o cabeçalho de autorização no proxy de sua organização.

>[!NOTE]
>
>Embora os membros da comunidade do Analytics tenham considerado os seguintes links úteis, eles não são de propriedade da Adobe. Leve isso em consideração ao exibir o conteúdo.

Informações sobre proxies da e cabeçalhos de autenticação podem ser encontradas aqui:

* [Configurar a autenticação upstream em proxy em uma Implantação da cadeia de proxy em um equipamento ProxySG ou ASG](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [Como encaminhar credenciais de usuário para um servidor por meio do equipamento ProxySG](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
