---
title: Solução de problemas de logon no Adobe Analytics
description: Etapas a serem seguidas quando não for possível fazer logon no Adobe Analytics.
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Solução de problemas de logon no Adobe Analytics

A Adobe Analytics usa vários métodos de autenticação para fazer logon:

* Adobe ID por meio do Experience Cloud
* ID herdada do Analytics
* Logon único

**Se você acessar o Analytics regularmente e começar a encontrar problemas de logon aleatoriamente, limpar os cookies e o cache do navegador resolverá a maioria dos problemas.**

Ocasionalmente, os problemas de disponibilidade podem afetar a capacidade de fazer logon. Verifique [status.adobe.com](https://status.adobe.com) se há incidentes abertos. Caso contrário, use a seção apropriada, dependendo do método de autenticação da organização.

## Adobe ID

Solucione problemas ao fazer logon no Adobe Analytics usando o Experience Cloud.

1. Navegue até [experience.adobe.com](https://experience.adobe.com). Se você não conseguir acessar este site, sua organização pode não permitir esse domínio por meio do firewall. Trabalhe com a equipe de TI de sua organização para permitir isso. Consulte [IPs e domínios usados no Adobe Experience Cloud](https://helpx.adobe.com/br/analytics/kb/adobe-ip-addresses.html) para obter informações úteis para fornecer à sua equipe de TI.

2. Autentique usando o Adobe ID: Clique em **[!UICONTROL Fazer logon com uma Adobe ID]**. Se não conseguir entrar, verifique novamente se seu endereço de email foi digitado corretamente. Caso contrário, clique em **[!UICONTROL Redefinir senha]** e siga as instruções para redefinir sua senha do Adobe ID.

3. Acesse o Analytics após a autenticação: Clique no ícone de 9-grid na parte superior direita e em Analytics. Caso não tenha essa opção ou esteja esmaecido, trabalhe com um administrador de produto em sua organização para garantir que você tenha as permissões corretas para acessar o Analytics.

## ID herdada do Analytics

Um usuário em sua organização pode receber o seguinte erro ao tentar fazer logon:

*Como precaução de segurança, esta conta foi bloqueada devido a muitas tentativas com falha de fazer logon.*

Se a limpeza dos cookies/cache do navegador não resolver o problema, trabalhe com um administrador do Analytics em sua organização para redefinir a senha do usuário.

>[!IMPORTANT]
>
>As etapas a seguir para redefinir a senha de um usuário se aplicam apenas às IDs do Analytics herdadas, não ao Adobe ID. Se sua organização usar o Adobe ID, você poderá gerenciar contas de usuário em [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Faça logon no Adobe Analytics com uma conta que tenha direitos administrativos.
2. Navegue até **[!UICONTROL Admin]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Gerenciamento de usuários]**.
3. Clique na guia **[!UICONTROL Users]** e depois clique em **[!UICONTROL Edit]** ao lado do usuário desejado.
4. Altere a senha para qualquer valor e marque a caixa **[!UICONTROL Require user to change password on next login]**.
5. Informe o usuário sobre a nova senha.

## Logon único

Entre em contato com um administrador em sua organização para resolver problemas de logon único.

## Logons expirados

Um usuário em sua organização pode receber o seguinte erro ao tentar fazer logon:

*Erro: Este logon expirou.*

Esse erro funciona conforme o esperado. O Adobe Analytics fornece aos administradores a capacidade de definir um intervalo de datas válido para uma conta de usuário. Se a data atual estiver fora do intervalo de datas válido para a conta, ela não poderá fazer logon. Trabalhe com um administrador do Analytics em sua organização para estender o intervalo de datas válido do logon. O Atendimento ao cliente do Adobe não está autorizado a alterar intervalos de datas de logon válidos para contas de usuário.

## Outros problemas de logon

Se nenhuma das etapas acima funcionar, determine a amplitude do problema de logon:

* O problema ocorre ao usar um navegador diferente ou ocorre em todos os navegadores?
* O problema ocorre em uma máquina diferente na rede ou em várias máquinas?
* Tente fazer logon usando uma rede diferente, como uma conexão de dados móvel, biblioteca ou rede doméstica. O problema está presente nas redes?

Se o problema for isolado em sua rede, trabalhe com a equipe de TI de sua organização para resolvê-lo. Se não estiver limitado a uma única rede, entre em contato com o Atendimento ao cliente do Adobe.
