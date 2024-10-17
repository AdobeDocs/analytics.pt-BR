---
description: O Report Builder da Adobe agora possui configurações de permissões análogas às das ferramentas administrativas do Analytics.
title: Permissões de acesso do usuário para dimensões e métricas
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 71%

---

# Permissões de acesso do usuário para dimensões e métricas

{{legacy-arb}}

O Adobe Report Builder apresenta configurações de permissão semelhantes às das Ferramentas administrativas do Analytics.

Como usuário não administrador, é possível ter criado anteriormente pastas de trabalho com solicitações que apontam para dimensões e métricas as quais você não tem acesso. Essas permissões são aplicadas agora.

Por exemplo, se você atualizar uma solicitação que inclui dimensões ou métricas às quais você não tem acesso, você receberá um Erro de permissão restrita. A mensagem de erro indica que uma solicitação não está disponível para sua conta de usuário devido a permissões administrativas.

![Captura de tela mostrando a mensagem Erro de Permissão Restrita.](assets/arb_restrc_perm.png)

Siga estas instruções para **cada** pasta de trabalho do Report Builder que você mantém:

1. Abra a pasta de trabalho.
1. Atualizar todas as solicitações.
1. Se você receber um erro de Permissão de acesso do usuário, clique em **[!UICONTROL Abrir arquivo CSV]** para obter acesso à lista de erros de permissões restritas.
1. Crie um arquivo &quot;AllRestrictedPermissionErrors.xlsx&quot; e copie/cole a lista de erros de permissões restritas do arquivo CSV nesse arquivo.
1. Feche a pasta de trabalho do Report Builder.

Depois de processar todas as pastas de trabalho, você deve ter uma lista abrangente de erros de permissão restritos em &quot;AllRestrictedPermissionErrors.xlsx&quot;. Envie essa lista para o administrador de acesso do usuário do Adobe Analytics, solicitando que conceda acesso às métricas e dimensões.
