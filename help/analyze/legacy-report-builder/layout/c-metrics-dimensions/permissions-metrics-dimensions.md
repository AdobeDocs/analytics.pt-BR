---
description: O Report Builder da Adobe agora possui configurações de permissões análogas às das ferramentas administrativas do Analytics.
title: Permissões de acesso do usuário para dimensões e métricas
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
TQID: https://experienceleague.adobe.com/p-nsvA1hqNBbwXesj5cumraamq2nEk1zVHgbby-XwEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 56%

---

# Permissões de acesso do usuário para dimensões e métricas

{{legacy-arb}}

O Adobe Report Builder apresenta configurações de permissão semelhantes às das Ferramentas administrativas do Analytics.

Como usuário não administrador, é possível ter criado anteriormente pastas de trabalho com solicitações que apontam para dimensões e métricas as quais você não tem acesso. Essas permissões agora são aplicadas.

Por exemplo, se você atualizar uma solicitação que inclui dimensões ou métricas às quais você não tem acesso, você receberá um Erro de permissão restrita. A mensagem de erro indica que uma solicitação não está disponível para sua conta de usuário devido a permissões administrativas.

![Captura de tela mostrando a mensagem Erro de Permissão Restrita.](assets/arb_restrc_perm.png)

Siga estas instruções para **cada** pasta de trabalho do Report Builder que você mantém:

1. Abra a pasta de trabalho.
1. Atualizar todas as solicitações.
1. Se você receber um aviso em um erro de Permissão de Acesso do Usuário, clique em **[!UICONTROL Abrir Arquivo CSV]** para obter acesso à lista de erros de permissões restritas.
1. Crie um arquivo &quot;AllRestrictedPermissionErrors.xlsx&quot; e copie/cole a lista de erros de permissões restritas do arquivo CSV nesse arquivo.
1. Feche a pasta de trabalho do Report Builder.

Depois de processar todas as pastas de trabalho, você deve ter uma lista abrangente de erros de permissão restritos em &quot;AllRestrictedPermissionErrors.xlsx&quot;. Envie essa lista para o administrador de acesso do usuário do Adobe Analytics, solicitando que conceda acesso às métricas e dimensões.
