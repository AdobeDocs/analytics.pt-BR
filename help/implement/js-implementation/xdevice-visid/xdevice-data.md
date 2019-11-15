---
description: Visão geral de como a ativação de visitante por vários dispositivos afeta os dados que você vê nos relatórios.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Impacto de dados da identificação de visitantes em vários dispositivos
topic: Developer and implementation
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Impacto de dados da identificação de visitantes em vários dispositivos

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a Documentação [do Device Co-op da](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Visão geral de como a ativação de visitante por vários dispositivos afeta os dados que você vê nos relatórios.

Para compreender como esse recurso afeta a coleta de dados, é útil compreender os campos de dados do visitante em um perfil de visitante:

| Campo de dados | Descrição |
|---|---|
| Visitor ID cookie | ID gerada automaticamente na primeira visita de um dispositivo ou navegador e armazenado no código `s_vi`. |
| Variável da ID do visitante | [!UICONTROL ID de visitante] opcional definida com o uso da variável `s.visitorID`. Esse valor é preenchido depois que um usuário é autenticado e pode corresponder a uma ID que sua empresa usa para rastrear um usuário em vários canais de marketing digital. |
| ID efetiva do visitante | A [!UICONTROL ID efetiva do visitante] é a ID real para o perfil do usuário. Esse valor é definido como o cookie da [!UICONTROL ID do visitante] ou a variável da [!UICONTROL ID do visitante], caso uma tenha sido fornecida. |

