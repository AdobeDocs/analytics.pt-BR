---
title: Solução de problemas de logon no Adobe Analytics
description: Etapas a serem executadas quando não for possível fazer logon no Adobe Analytics.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 3%

---


# Solução de problemas de logon no Adobe Analytics

A Adobe Analytics usa vários métodos de autenticação para fazer logon:

* Adobe ID através do Experience Cloud
* ID antiga do Analytics
* Logon único

**Se você acessar regularmente o Analytics e encontrar aleatoriamente problemas de login no start, limpar os cookies e o cache do navegador resolverá a maioria dos problemas.**

Ocasionalmente, problemas de disponibilidade podem afetar a capacidade de fazer logon. Verifique [status.adobe.com](https://status.adobe.com) em busca de incidentes abertos. Caso contrário, use a seção apropriada, dependendo do método de autenticação de sua organização.

## Adobe ID

Solucione problemas com o logon no Adobe Analytics usando o Experience Cloud.

1. Navegue até [experience.adobe.com](https://experience.adobe.com). Se você não conseguir acessar este site, sua organização pode não permitir esse domínio por meio do firewall. Trabalhe com a equipe de TI de sua organização para permitir isso. Consulte [IPs e domínios usados na Adobe Experience Cloud](https://helpx.adobe.com/br/analytics/kb/adobe-ip-addresses.html) para obter informações úteis para a sua equipe de TI.

2. Autentique usando o Adobe ID: Clique em **[!UICONTROL Fazer logon com um Adobe ID]**. Se você não conseguir fazer logon, o duplo verificará se seu endereço de email foi digitado corretamente. Caso contrário, clique em **[!UICONTROL Redefinir senha]** e siga os prompts para redefinir sua senha do Adobe ID.

3. Acesse o Analytics após a autenticação: Clique no ícone de grade de 9 na parte superior direita e clique em Analytics. Se você não tiver essa opção ou ela estiver acinzentada, trabalhe com um administrador de produto em sua organização para garantir que você tenha as permissões corretas para acessar o Analytics.

## ID antiga do Analytics

Ocasionalmente, um usuário em sua organização recebe a seguinte mensagem de erro ao fazer logon:

*Como precaução de segurança, esta conta foi bloqueada devido a muitas tentativas de login com falha.*

Se a limpeza dos cookies/cache do navegador não resolver o problema, entre em contato com um administrador do Analytics em sua organização para redefinir a senha do usuário.

>[!IMPORTANT]
>
>As etapas a seguir para redefinir a senha de um usuário se aplicam somente às IDs herdadas do Analytics, não à Adobe ID. Se sua organização usar o Adobe ID, você poderá gerenciar contas de usuário em [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Faça logon na Adobe Analytics com uma conta que tenha direitos administrativos.
2. Navegue até **[!UICONTROL Admin]** > Gerenciamento **** do usuário.
3. Clique na guia **[!UICONTROL Usuários]** e, em seguida, clique em **[!UICONTROL Editar]** ao lado do usuário desejado.
4. Altere a senha para qualquer valor e marque a caixa **[!UICONTROL Exigir que o usuário altere a senha no próximo login]**.
5. Informe o usuário sobre a nova senha.

## Logon único

Entre em contato com um administrador em sua organização para resolver problemas de logon único.

## Outros problemas de login

Se nenhuma das etapas acima funcionar, determine a amplitude do problema de login:

* O problema ocorre ao usar um navegador diferente ou ocorre em todos os navegadores?
* O problema ocorre em uma máquina diferente na rede ou em várias máquinas?
* Tente fazer logon usando uma rede diferente, como uma conexão de dados móvel, biblioteca ou rede doméstica. O problema está presente nas redes?

Se o problema estiver isolado na rede, entre em contato com a equipe de TI da sua organização para resolvê-lo. Se não estiver limitado a uma única rede, entre em contato com o Atendimento ao cliente da Adobe.
