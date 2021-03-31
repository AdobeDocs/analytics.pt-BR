---
description: Problemas comuns ao usar o Report Builder com o Power BI.
title: Solução de problemas de integração do Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
feature: Report Builder
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 50%

---


# Solução de problemas de integração do Power BI

Pesquise e resolva problemas comuns ao usar o Report Builder com Power BI.

## Falha na publicação para o Power BI

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

Peça a um Administrador da Microsoft que analise a configuração &quot;Os usuários podem registrar o aplicativo&quot; localizada em: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Ative Diretory]** > **[!UICONTROL As Configurações do Usuário permitem opções]**. Se essa opção estiver definida como Não, esse administrador poderá registrar esses tipos de aplicativos.

Os usuários podem conceder o Acesso usando o seguinte [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Os administradores concederam acesso a cada um usando o seguinte [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).
