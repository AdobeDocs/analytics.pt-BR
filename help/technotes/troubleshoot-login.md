---
title: Solucionar problemas de logon no Adobe Analytics
description: Etapas a serem seguidas quando não for possível fazer logon no Adobe Analytics.
feature: Analytics Basics
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
TQID: https://experienceleague.adobe.com/akXZpx8BUywqvI2NGvk9dqIBL-pHEAza1-I05pC89io
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 607
ht-degree: 88%

---

# Solucionar problemas de logon no Adobe Analytics

O Adobe Analytics usa vários métodos de autenticação para fazer logon:

* Adobe ID por meio do CX Enterprise
* ID herdada do Analytics
* Logon único

**Se você acessar o Analytics regularmente e começar a encontrar problemas ao fazer logon aleatoriamente, limpar os cookies e o cache do navegador resolverá a maioria dos problemas.**

Ocasionalmente, problemas de disponibilidade podem afetar a capacidade de fazer logon. Verifique em [status.adobe.com](https://status.adobe.com) se há incidentes abertos. Caso contrário, use a seção apropriada, dependendo do método de autenticação da organização.

## Adobe ID

Solucione problemas ao fazer logon no Adobe Analytics usando o CX Enterprise.

1. Navegue até [Adobe CX Enterprise](https://experience.adobe.com). Se você não conseguir acessar esse site, talvez sua organização não permita esse domínio por meio do firewall. Fale com a equipe de TI da sua organização para obter permissão. Consulte [Endereços IP usados pelo Adobe Analytics](/help/technotes/ip-addresses.md) para obter informações úteis para fornecer à sua equipe de TI.

2. Autentique usando a Adobe ID: clique em **[!UICONTROL Fazer logon com uma Adobe ID]**. Se não conseguir fazer logon, verifique se seu endereço de email foi digitado corretamente. Caso contrário, clique em **[!UICONTROL Redefinir senha]** e siga as instruções para redefinir a senha da Adobe ID.

3. Acesse o Analytics após a autenticação: clique no ícone de nove grades na parte superior direita e clique no Analytics. Caso não haja essa opção ou ela esteja esmaecida, trabalhe com um administrador de produto em sua organização para garantir que você tenha as permissões corretas para acessar o Analytics.

## ID herdada do Analytics

Um usuário em sua organização pode receber o seguinte erro ao tentar fazer logon:

*Como precaução de segurança, essa conta foi bloqueada devido a muitas tentativas de logon com falha.*

Se a limpeza dos cookies/cache do navegador não resolver o problema, peça a um administrador do Analytics em sua organização que redefina a senha do usuário.

>[!IMPORTANT]
>
>As etapas a seguir para redefinir a senha de um usuário se aplicam apenas às IDs do Analytics herdadas, não à Adobe ID. Se sua organização usar o Adobe ID, você poderá gerenciar contas de usuário em [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Faça logon no Adobe Analytics com uma conta que tenha direitos administrativos.
2. Navegue até **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL User Management]**.
3. Clique na guia **[!UICONTROL Usuários]** e depois clique em **[!UICONTROL Editar]** próximo ao usuário desejado.
4. Altere a senha para qualquer valor e marque a caixa **[!UICONTROL Exigir que o usuário altere a senha no próximo logon]**.
5. Informe o usuário sobre a nova senha.

## Logon único

Entre em contato com um administrador em sua organização para resolver problemas de logon único.

## Logons expirados

Um usuário em sua organização pode receber o seguinte erro ao tentar fazer logon:

*Erro: este logon expirou.*

Esse erro funciona conforme o esperado. O Adobe Analytics fornece aos administradores a capacidade de definir um intervalo de datas válido para uma conta de usuário. Se a data atual estiver fora do intervalo de datas válido para a conta, não será possível fazer logon. Peça a um administrador do Analytics em sua organização que estenda o intervalo de datas válido do logon. O Atendimento ao cliente da Adobe não está autorizado a alterar intervalos de datas de logon válidos para contas de usuário.

## Outros problemas de logon

Se nenhuma das etapas acima funcionar, determine a amplitude do problema de logon:

* O problema ocorre ao usar um navegador diferente ou ocorre em todos os navegadores?
* O problema ocorre em uma máquina diferente na rede ou em várias máquinas?
* Tente fazer logon usando uma rede diferente, como uma conexão de dados móvel, uma biblioteca ou uma rede doméstica. O problema acontece em várias redes?

Se o problema for isolado em sua rede, fale com a equipe de TI de sua organização para resolvê-lo. Se não estiver limitado a uma única rede, entre em contato com o Atendimento ao cliente da Adobe.
