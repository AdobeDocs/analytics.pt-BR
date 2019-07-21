---
description: O Construtor de relatórios da Adobe agora possui configurações de permissões análogas às das ferramentas administrativas do Analytics.
seo-description: O Construtor de relatórios da Adobe agora possui configurações de permissões análogas às das ferramentas administrativas do Analytics.
seo-title: Permissões de acesso do usuário para dimensões e métricas
solution: Analytics
title: Permissões de acesso do usuário para dimensões e métricas
topic: Construtor de relatórios
uuid: b 561407 d-c 4 fa -4 f 1 e -8 b 16-5 ca 46 fcbf 36 f
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Permissões de acesso do usuário para dimensões e métricas

O Construtor de relatórios da Adobe agora possui configurações de permissões análogas às das ferramentas administrativas do Analytics.

Como usuário não administrador, é possível ter criado anteriormente pastas de trabalho com solicitações que apontam para dimensões e métricas as quais você não tem acesso. Essas permissões são aplicadas agora.

Por exemplo, se você atualizou uma solicitação que inclui dimensões ou métricas às quais você não tem acesso, você obterá um Erro de permissão restrita:

![](assets/arb_restrc_perm.png)

Siga estas instruções para **cada** pasta de trabalho do Construtor de relatórios que você mantém:

1. Abra a pasta de trabalho.
1. Atualizar todas as solicitações.
1. Se você receber um erro de Permissão de acesso do usuário, clique em **[!UICONTROL Abrir arquivo CSV]para obter acesso à lista de erros de permissões restritas.**
1. Crie um arquivo "AllRestrictedPermissionErrors.xlsx" e copie/cole a lista de erros de permissões restritas do arquivo CSV nesse arquivo.
1. Feche a pasta de trabalho do Construtor de relatórios.

Depois de processar todas as pastas de trabalho, você deve ter uma lista abrangente de erros de permissão restritos em "AllRestrictedPermissionErrors.xlsx". Envie essa lista para o administrador de acesso do usuário do Adobe Analytics, solicitando que conceda acesso às métricas e dimensões.
