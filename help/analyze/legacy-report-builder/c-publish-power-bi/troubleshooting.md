---
description: Problemas comuns ao usar o Report Builder com o Power BI.
title: Solução de problemas de integração do Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 40%

---

# Solução de problemas de integração do Power BI

{{legacy-arb}}

Pesquisar e resolver problemas comuns ao usar o Report Builder com o Power BI.

## Falha ao publicar no Power BI

As pastas de trabalho agendadas que exigem publicação no Power BI dependem dos serviços da Power BI para estarem ativas e em execução. Dois motivos principais para a não publicação são:

* Os serviços da Power BI podem estar inativos.
* O usuário que agendou a pasta de trabalho não tem mais credenciais de conta válidas da Microsoft.

Cada tarefa agendada do Report Builder tem três tentativas por execução agendada:

* Após a primeira tentativa malsucedida, você receberá esta mensagem: &quot;Não foi possível publicar essa pasta de trabalho agendada no Microsoft Power BI. Vamos tentar novamente em breve.&quot;
* Após a segunda tentativa malsucedida, você não receberá nenhuma mensagem.
* Após a terceira tentativa malsucedida, você receberá esta mensagem: &quot;Não foi possível publicar esta pasta de trabalho no Power BI&quot;.

## Visualizações quebradas no Power BI

Essas são as principais razões pelas quais visualizações quebradas podem ocorrer após a publicação de solicitações do Report Builder no Power BI:

* Você editou uma solicitação no Report Builder, tal como alteração de métricas ou dimensões e depois republicou no Power BI. As solicitações de edição podem interromper suas visualizações.
* Você excluiu uma solicitação que foi usada em uma visualização.

>[!IMPORTANT]
>
>O Report Builder requer um administrador para autorizar o acesso aos recursos da organização. Se precisar de acesso, peça a um administrador que conceda permissão.
> Um Administrador do Microsoft pode examinar a configuração *Usuários podem registrar o aplicativo*, localizada em: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Ative Diretory]** > **[!UICONTROL As configurações de usuário permitem opções]**. Se essa opção estiver definida como **Não**, o administrador poderá registrar esses tipos de aplicativos.

Os usuários podem conceder o Acesso fazendo logon em sua [conta do Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Os administradores podem conceder acesso a cada um deles fazendo logon em sua [conta de administrador do Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

## Atingir o limite da API

Os relatórios no Power BI funcionam com a API de relatórios do Analytics, portanto, os limites da API se aplicam.
