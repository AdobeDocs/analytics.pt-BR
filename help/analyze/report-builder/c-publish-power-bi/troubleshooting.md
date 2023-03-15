---
description: Problemas comuns ao usar o Report Builder com o Power BI.
title: Solução de problemas de integração do Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: f6f65f34c4d8caf04eb3ea47108e36e5b9adf24f
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 89%

---

# Solução de problemas de integração do Power BI

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

## O Report Builder precisa ser autorizado a acessar os recursos da organização. Esse acesso só pode ser concedido por um administrador. Peça a um administrador que conceda permissão.

Peça a um administrador da Microsoft que analise a configuração “Usuários podem registrar um aplicativo”, localizada em: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Configurações do usuário permitem opções]**. Se essa opção estiver definida como Não, esse administrador poderá registrar esses tipos de aplicativos.

Os usuários podem conceder acesso usando este [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Os administradores recebem acesso para cada um usando este [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Atingir o limite da API

Os relatórios no Power BI funcionam com a API de relatórios do Analytics, portanto, os limites da API se aplicam. Para obter mais informações, consulte [Códigos de erro de serviços da Web](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
