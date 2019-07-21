---
title: Solução de problemas de sessões no Adobe Analytics
description: Saiba como resolver problemas de logout do Adobe Analytics.
seo-title: Solução de problemas de sessões no Adobe Analytics
seo-description: Saiba como resolver problemas de logout do Adobe Analytics.
translation-type: tm+mt
source-git-commit: b5e3801454dafbcc47b93e65f8b5e7c59c3a8081

---


# Solução de problemas de sessões no Adobe Analytics

Esta página aborda as sessões de solução de problemas, o que significa que você poderá fazer o logon com êxito, mas com problemas ao se conectar. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Quase todos os problemas baseados em sessão são originários da rede corporativa personalizada de uma organização. Se você conseguir fazer logon no Adobe Analytics mas tiver problemas com o logon, use este artigo para ajudar a determinar a causa.

## Determine se o problema se deve à rede de sua organização

Muitas organizações implantam recursos de rede adicionais para aprimorar a segurança, como servidores proxy ou firewalls. Essas personalizações podem interferir na capacidade de reter uma sessão ativa no Adobe Analytics.

Para determinar se a rede corporativa a que você está conectado está causando problemas com o uso do Adobe Analytics, use as credenciais de logon da Experience Cloud em um dispositivo fora da rede corporativa. Exemplos de dispositivos podem estar por meio da rede inicial ou do plano de dados de um dispositivo móvel. Se você for capaz de mover-se de forma bem-sucedida para a página sem ser desconectado, a rede da sua empresa provavelmente será o motivo por que você é desconectado do Adobe Analytics.

## Problemas devido ao pooling de IP

Algumas redes usam uma prática chamada pooling de IP, em que o endereço IP de um dispositivo pode ser alterado frequentemente dentro de um intervalo usado pela organização. Como parte das práticas de segurança da Adobe, se um endereço IP mudar de sessão, essa sessão expirará.

Se sua organização usar pooling de IP, use as instruções a seguir para adicionar seus intervalos IP à lista de permissões da Adobe:

1. Trabalhar com a equipe de TI da sua organização para obter uma lista de intervalos IP usados em sua organização
2. Solicite que um representante de suporte ao cliente entre em contato com o Atendimento ao cliente da Adobe e forneça aos intervalos IP a Adobe
3. O agente insere os intervalos IP em uma lista de permissões para impedir que as sessões expirem se ambos os endereços estiverem nos intervalos fornecidos

## Problemas devido ao proxy

A Adobe usa um cabeçalho de autorização ao fazer solicitações para a Adobe. Alguns proxies, como o Bluecoat (agora pertencente à Symantec), removem informações críticas do cabeçalho de autorização usadas pelo Adobe Analytics. Quando a Adobe não visualiza o cabeçalho de autorização, a sessão expira.

Para resolver esse problema, a Adobe recomenda trabalhar com a equipe de TI da sua organização para permitir o cabeçalho de autorização por meio do proxy de sua organização.

> [!NOTE] Observação
>
> Embora os membros da comunidade do Analytics tenham localizado os seguintes links, eles não são da parte da Adobe. Considere essa observação ao visualizar seu conteúdo.

Informações sobre proxies Symantec e cabeçalhos de autenticação podem ser encontradas aqui:

* [Configurar autenticação de proxy a montante em uma implantação de cadeia de proxy em um applília proxysg ou ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Permitir proxysg para sempre encaminhar a autorização do servidor a montante](https://support.symantec.com/en_US/article.TECH244708.html)
