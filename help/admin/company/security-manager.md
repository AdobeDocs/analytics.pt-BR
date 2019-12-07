---
description: Permite que você controle o acesso aos dados de relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.
title: Gerenciador de segurança
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gerenciador de segurança

O Gerenciador de segurança permite controlar o acesso aos dados do relatório. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email.

## Configurações

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administração]** &gt; **[!UICONTROL Configurações da empresa]** &gt; **[!UICONTROL Segurança]**

| Configuração | Descrição |
|--- |--- |
| Exigir senhas de alta segurança | Faz com que os usuários criem senhas mais seguras que sigam as seguintes regras: <ul><li>Deve ter pelo menos oito caracteres de comprimento.</li><li>Deve ter pelo menos um símbolo/caractere numérico entre o primeiro e o último caractere.</li><li>Deve ter pelo menos um caractere alfa.</li><li>Não pode ser encontrada em um dicionário nem conter palavras de um dicionário (inglês).</li><li>Não pode incluir 3 (três) caracteres consecutivos do nome de usuário do logon.</li><li>Deve ser diferente das 10 senhas anteriores.</li></ul>**Observação**: Este recurso é aplicado em novas senhas futuras. Não verifica senhas existentes nem força os usuários a alterarem as senhas existentes. Por isso, considere ativar  a expiração da senha para forçar os usuários a alterarem suas senhas e aderirem às regras de senhas de alta segurança. |
| Expiração da senha | Faz com que os usuários mudem regularmente a senha de suas contas de usuário. É possível especificar o intervalo em que deseja que as senhas expirem e fazer as senhas expirarem imediatamente. |
| Impor restrições de logon de IP | (Essa funcionalidade não pode ser usada juntamente com o logon da Experience Cloud. Observe que essa funcionalidade não estará mais disponível a partir de outubro de 2020. [Mais...](/help/admin/company/login-restrictions-eol.md))<br> Limita o acesso ao relatório a endereços IP específicos ou intervalos de endereços IP. Você pode adicionar até 100 entradas na lista de Filtros de endereço IP, e cada entrada precisa ser um endereço específico ou um intervalo de endereços. Impor restrições de logon de IP não é aplicado até que haja pelo menos uma entrada na lista de Filtro de endereço IP. Endereço IP aceito: Para especificar um intervalo de endereço IP, coloque o intervalo entre parênteses (por exemplo, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8) Failed logins are logged and viewable from the [Usage and Access Log](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Impor restrições de domínio de email | Filtra os domínios e endereços de email em que o Analytics envia marcadores, relatórios para download e alertas. A lista de filtro de email oferece suporte a até 100 entradas e cada entrada pode ser um endereço de email ou todo um domínio de email. Se um relatório programado tiver um destino de email não aprovado, o Analytics envia uma notificação por email sobre o problema e um link para desprogramar o relatório. **[!UICONTROL Impor restrições de domínio de email]** não é empregado até que exista pelo menos uma entrada na lista de Filtro de domínio de email aceito. **[!UICONTROL Domínios]** e endereço de email aceitos: Para especificar um intervalo de endereços IP, coloque o intervalo entre parênteses (por exemplo, 192.168.10.[20-240]). You can also use wildcards to specify any number from 0 to 255 (for example, 192.168.[10-14].*) |
| Notificação de recuperação de senha | Notifica os administradores especificados sobre quando um usuário tenta redefinir a senha de uma conta de usuário. **[!UICONTROL Admins disponíveis]**: exibe todos os administradores. Você pode clicar e ao mesmo tempo pressionar Ctrl ou Shift para selecionar vários administradores. **[!UICONTROL Membros de email]**: exibe o grupo de email definido no momento. |
