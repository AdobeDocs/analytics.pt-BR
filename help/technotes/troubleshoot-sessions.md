---
title: Solução de problemas de sessões no Adobe Analytics
description: Saiba mais sobre como resolver problemas ao desconectar-se do Adobe Analytics.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Solução de problemas de sessões no Adobe Analytics

Esta página trata das sessões de solução de problemas, o que significa que você pode fazer logon com êxito, mas tem problemas para continuar conectado. Se tiver problemas ao fazer logon no Adobe Analytics, consulte [Solução de problemas ao fazer logon no Adobe Analytics](troubleshoot-login.md).

Quase todos os problemas com base em sessões se originam da rede corporativa personalizada de uma organização. Se você conseguir fazer logon no Adobe Analytics, mas tiver problemas para permanecer conectado, use este artigo para ajudar a determinar a causa.

## Determine se o problema ocorre devido à rede de sua organização

Muitas organizações implantam recursos de rede adicionais para melhorar a segurança, como servidores proxy ou firewalls. Às vezes, essas personalizações podem interferir na capacidade de manter uma sessão ativa no Adobe Analytics.

Para determinar se a rede corporativa à qual você está conectado está causando problemas ao usar o Adobe Analytics, use suas credenciais de logon da Experience Cloud em um dispositivo fora da rede corporativa. Exemplos de dispositivos podem ser encontrados por meio da sua rede doméstica ou do plano de dados de um dispositivo móvel. Se você conseguir mover-se de uma página para outra sem ter sido desconectado, a rede de sua organização provavelmente será o motivo pelo qual você terá desconectado do Adobe Analytics.

## Problemas devidos ao proxy

A Adobe usa um cabeçalho de autorização ao fazer solicitações à Adobe. Alguns proxies, como o Bluecat (agora pertencente à Symantec), removem informações do cabeçalho de autorização crítica usadas pelo Adobe Analytics. Quando a Adobe não vê o cabeçalho de autorização, a sessão expira.

Para resolver esse problema, a Adobe recomenda trabalhar com a equipe de TI de sua organização para permitir o cabeçalho da autorização por meio do proxy de sua organização.

> [!NOTE] Embora os membros da comunidade do Analytics tenham considerado os seguintes links úteis, eles não são de propriedade da Adobe. Leve isso em consideração ao exibir o conteúdo.

Informações sobre proxies da Symantec e cabeçalhos de autenticação podem ser encontradas aqui:

* [Configurar a Autenticação Proxy Upstream em uma Implantação da Cadeia Proxy em um Equipamento ProxySG ou ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Permitir que o ProxySG sempre encaminhe a autorização do servidor a montante](https://support.symantec.com/en_US/article.TECH244708.html)
