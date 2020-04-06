---
description: Você pode proteger todas as solicitações em uma pasta de trabalho em comparação a adicionar e editar solicitações ao bloquear a pasta de trabalho. Isso permite editar pastas de trabalho offline, pausando todas as solicitações de relatório para obter uma edição mais eficiente.
title: Bloquear/desbloquear pastas de trabalho
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Bloquear/desbloquear pastas de trabalho

Você pode proteger todas as solicitações em uma pasta de trabalho em comparação a adicionar e editar solicitações ao bloquear a pasta de trabalho. Isso permite editar pastas de trabalho offline, pausando todas as solicitações de relatório para obter uma edição mais eficiente.

Como um analista, o bloqueio de uma pasta de trabalho permite que você proteja suas solicitações de pasta de trabalho contra adulterações por outros usuários na organização. Ao mesmo tempo, esses usuários ainda podem atualizar as solicitações na pasta de trabalho.

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

).

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

É possível desbloquear uma pasta de trabalho bloqueada se você tiver uma das seguintes permissões:

* Você é um administrador ou
* Você é a pessoa que inicialmente bloqueou a pasta de trabalho. Nesse caso, você não precisa ser um administrador.

>[!NOTE] Não é possível adicionar uma solicitação a uma pasta de trabalho protegida, exceto com permissões para desbloquear a pasta de trabalho.

Quando uma pasta de trabalho é bloqueada contra edição de solicitação,

* Os usuários não podem criar/adicionar solicitações.
* Os usuários não podem editar solicitações por meio do Assistente de solicitações.
* Os usuários não podem editar solicitações por meio dos recursos Editar várias solicitações.
* Os usuários não podem cortar, copiar ou colar solicitações. No entanto, os usuários ainda podem usar o menu de contexto Cortar/Copiar/Colar nativo do Excel para recortar/copiar/colar o conteúdo das solicitações.
* Os usuários podem atualizar solicitações, individualmente ou como parte de um grupo.
* Se a solicitação usar valores de entrada de células (intervalo de datas, segmento, filtros), os usuários poderão alterar esses valores nas células e, portanto, editar indiretamente as solicitações atualizando-as.

Se tentar editar uma pasta de trabalho protegida (pelo menu de contexto, ou **[!UICONTROL Request Manager]**, ou **[!UICONTROL Edit Multiple Requests]**), você pode ou não ter permissão para fazer isso:

* Se você não tiver permissões para desbloquear as solicitações, este prompt será exibido:

   ![](assets/locked_workbook_error.png)

* Se você tiver as permissões necessárias, nenhum prompt será exibido e você poderá editar a solicitação.

## Fluxo de trabalho {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Considere que a pasta de trabalho A tem uma solicitação que está em um estado bloqueado e foi criada pelo usuário A.

**Exemplo 1: usuário administrador (ou Usuário A)**

1. O usuário entra no Report Builder e abre uma pasta de trabalho.
1. A pasta de trabalho A está bloqueada no momento, portanto, o botão &quot;Criar solicitação&quot; está desativado na barra de ferramentas, juntamente com o resto dos botões cuja funcionalidade está desativada por bloqueio.
1. Se o usuário tentar usar um dos botões desativados, será exibida uma mensagem informando que a pasta de trabalho está bloqueada no momento.
1. O usuário pode desbloquear a pasta de trabalho, o que habilita a funcionalidade de edição completa.
1. Depois de desbloquear, a pasta de trabalho permanece desbloqueada até ser explicitamente rebloqueada.

**Exemplo 2: usuário não administrador (Usuário B)**

1. O usuário entra no Report Builder e abre uma pasta de trabalho.
1. O usuário não pode adicionar/editar a solicitação.
1. O usuário não pode desbloquear a pasta de trabalho.

