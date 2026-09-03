---
description: Permite controlar o acesso aos dados de relatórios. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.
title: Gerenciador de segurança
feature: Company Settings
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
role: Admin
TQID: https://experienceleague.adobe.com/30JGwAhRR73qSBse0Om2mWY4k-oy7j0O-JzmFZ-kaEY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 368
ht-degree: 76%

---

# Gerenciador de segurança

O Gerenciador de segurança permite controlar o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.

## Configurações

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Configurações da empresa]** > **[!UICONTROL Segurança]**

| Configuração | Descrição |
| --- | --- |
| Exigir senhas de alta segurança | Faz com que os usuários criem senhas mais seguras que seguem as seguintes regras: <ul><li>Deve ter pelo menos oito caracteres.</li><li>Ter, pelo menos, um símbolo/caractere numérico entre o primeiro e o último caractere.</li><li>Deve ter pelo menos um caractere alpha.</li><li>Não pode ser encontrado em um dicionário ou conter palavras de um dicionário (inglês).</li><li>Não pode incluir quaisquer três (3) caracteres consecutivos do nome de usuário de login.</li><li>Deve ser diferente das 10 senhas anteriores.</li></ul>**Observação**: esse recurso é empregado em novas senhas subsequentes. Não verifica senhas existentes nem força os usuários a alterarem as senhas existentes. Por esse motivo, considere ativar a expiração da senha para forçar os usuários a alterarem suas senhas e aderirem às regras de senhas de alta segurança. |
| Expiração da senha | Faz com que os usuários mudem regularmente a senha de suas contas de usuário. Você pode especificar o intervalo em que deseja que as senhas expirem e forçar as senhas a expirarem imediatamente. |
| Impor restrições de domínio de email | Filtra os domínios e endereços de email em que o Analytics envia marcadores, relatórios para download e alertas. A lista de filtro de email oferece suporte a até 100 entradas e cada entrada pode ser um endereço de email ou todo um domínio de email. Se um relatório programado tiver um destino de email não aprovado, o Analytics envia uma notificação por email sobre o problema e um link para desprogramar o relatório. **[!UICONTROL Impor restrições de domínio de email]** não é empregado até que exista pelo menos uma entrada na lista de Filtro de domínio de email aceito. **[!UICONTROL Domínios e endereços de email aceitos]**: Para especificar um intervalo de endereço IP, coloque o intervalo entre parênteses (por exemplo, `192.168.10.[20-240]`). Também é possível usar curingas para especificar qualquer número de 0 a 255 (por exemplo, `192.168.[10-14].*`) |
| Notificação de recuperação de senha | Notifica os administradores especificados sobre quando um usuário tenta redefinir a senha de uma conta de usuário. **[!UICONTROL Admins disponíveis]**: exibe todos os administradores. Você pode clicar e ao mesmo tempo pressionar Ctrl ou Shift para selecionar vários administradores. **[!UICONTROL Membros de email]**: exibe o grupo de email definido no momento. |
