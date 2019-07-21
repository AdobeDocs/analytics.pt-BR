---
description: 'Você pode proteger todas as solicitações em uma pasta de trabalho em comparação a adicionar e editar solicitações ao bloquear a pasta de trabalho. Isso permite editar pastas de trabalho offline, pausando todas as solicitações de relatório para obter uma edição mais eficiente. '
seo-description: 'Você pode proteger todas as solicitações em uma pasta de trabalho em comparação a adicionar e editar solicitações ao bloquear a pasta de trabalho. Isso permite editar pastas de trabalho offline, pausando todas as solicitações de relatório para obter uma edição mais eficiente. '
seo-title: Bloquear/desbloquear pastas de trabalho
solution: Analytics
title: Bloquear/desbloquear pastas de trabalho
topic: Construtor de relatórios
uuid: ef 5 c 276 c -5 f 74-4741-b 6 fa -4 c 79 eda 29 f 62
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Bloquear/desbloquear pastas de trabalho

Você pode proteger todas as solicitações em uma pasta de trabalho em comparação a adicionar e editar solicitações ao bloquear a pasta de trabalho. Isso permite editar pastas de trabalho offline, pausando todas as solicitações de relatório para obter uma edição mais eficiente. 

Como um analista, o bloqueio de uma pasta de trabalho permite que você proteja suas solicitações de pasta de trabalho contra adulterações por outros usuários na organização. Ao mesmo tempo, esses usuários ainda podem atualizar as solicitações na pasta de trabalho.

Para proteger uma pasta de trabalho contra edição, clique em **[!UICONTROL Bloqueado]** na barra de ferramentas do Construtor de relatórios ( ![](assets/locked_icon.png)

).

Para desbloquear uma pasta de trabalho, clique em **[!UICONTROL Desbloqueado]** ( ![](assets/unlocked_icon.png)

).

É possível desbloquear uma pasta de trabalho bloqueada se você tiver uma das seguintes permissões:

* Você é um administrador ou
* Você é a pessoa que inicialmente bloqueou a pasta de trabalho. Nesse caso, você não precisa ser um administrador.

>[!NOTE]
>
>Não é possível adicionar uma solicitação a uma pasta de trabalho protegida a menos que você tenha as permissões para desbloquear a pasta de trabalho.

Quando uma pasta de trabalho é bloqueada contra edição de solicitação.

* Os usuários não conseguem criar/adicionar solicitações.
* Os usuários não conseguem editar solicitações através do Assistente de solicitações.
* Os usuários não conseguem editar solicitações através dos recursos de Editar várias solicitações.
* Os usuários não podem cortar, copiar ou colar solicitações. No entanto, os usuários ainda podem usar o menu de contexto Cortar/Copiar/Colar nativo do Excel para cortar/copiar/colar o conteúdo das solicitações.
* Os usuários podem atualizar solicitações, de forma individual, ou como parte de um grupo.
* Se a solicitação usa valores de entrada de células (intervalo de datas, segmento, filtros), os usuários podem alterar esses valores em células e, portanto, editar indiretamente as solicitações ao atualizá-las.

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* Se você não tem permissões para desbloquear as solicitações, este prompt aparece:

   ![](assets/locked_workbook_error.png)

* Se você tem as permissões necessárias, nenhum prompt é exibido, e é possível editar a solicitação.

## Fluxo de trabalho {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Considere que a pasta de trabalho A tem uma solicitação que está em um estado bloqueado e foi criada pelo usuário A.

**Exemplo 1: Usuário administrador (ou usuário A)**

1. O usuário entra no Construtor de relatórios e abre uma pasta de trabalho 
1. A pasta de trabalho A está bloqueada no momento, portanto, o botão "Criar solicitação" está desativado na barra de ferramentas, juntamente com o resto dos botões cuja funcionalidade está desabilitada por bloqueio.
1. Se o usuário tentar usar um dos botões desativados, uma mensagem aparece informando que a pasta de trabalho está bloqueada no momento.
1. O usuário pode desbloquear a pasta de trabalho, o que habilita a função de edição completa.
1. Depois de desbloquear, a pasta de trabalho permanece desbloqueada até ser explicitamente bloqueada novamente.

**Exemplo 2: Usuário não administrador (usuário B)**

1. O usuário entra no Construtor de relatórios e abre uma pasta de trabalho 
1. O usuário não pode adicionar/editar a solicitação.
1. O usuário não pode desbloquear a pasta de trabalho.

