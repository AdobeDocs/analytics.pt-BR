---
description: Problemas comuns ao usar o Report Builder com o Power BI.
title: Solução de problemas de integração do Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 66%

---

# Solução de problemas de integração do Power BI

{{legacy-arb}}

Pesquisar e resolver problemas comuns ao usar o Report Builder com o Power BI.

## Falha ao publicar no Power BI

Pastas de trabalho agendadas que exigem publicação no Power BI dependem de serviços do Power BI para funcionar. Duas razões principais para uma falha na publicação são:

* Os serviços do Power BI não estão ativos.
* O usuário que agendou a pasta de trabalho não possui mais credenciais válidas para uma conta da Microsoft.

Cada tarefa agendada do Report Builder tem três tentativas por execução agendada:

* Após a primeira tentativa mal sucedida, aparecerá a mensagem “Não foi possível publicar essa pasta de trabalho agendada no Microsoft Power BI. Tentaremos novamente em breve.”
* Após a segunda tentativa mal sucedida, não aparecerá nenhuma mensagem.
* Após a terceira tentativa mal sucedida, aparecerá a mensagem: “Não foi possível publicar essa pasta de trabalho no Power BI.”

## Visualizações quebradas no Power BI

Essas são as principais razões pelas quais visualizações quebradas podem ocorrer após a publicação de solicitações do Report Builder no Power BI:

* Você editou uma solicitação no Report Builder, tal como alteração de métricas ou dimensões e depois republicou no Power BI. A edição de solicitações pode quebrar as suas visualizações.
* Você excluiu uma solicitação que foi usada em uma visualização.

>[!IMPORTANT]
>
>O Report Builder requer um administrador para autorizar o acesso aos recursos da organização. Se precisar de acesso, peça a um administrador que conceda permissão.
>> Um Administrador do Microsoft pode examinar a configuração *Usuários podem registrar o aplicativo*, localizada em: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Ative Diretory]** > **[!UICONTROL As configurações de usuário permitem opções]**. Se essa opção estiver definida como **Não**, o administrador poderá registrar esses tipos de aplicativos.

Os usuários podem conceder o Acesso fazendo logon em sua [conta do Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Os administradores podem conceder acesso a cada um deles fazendo logon em sua [conta de administrador do Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

## Atingir o limite da API

Os relatórios no Power BI funcionam com a API de relatórios do Analytics, portanto, os limites da API se aplicam.
