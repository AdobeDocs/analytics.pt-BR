---
description: Visão geral de como a ativação de visitante por vários dispositivos afeta os dados que você vê nos relatórios.
keywords: Implementação do Analytics
seo-description: Visão geral de como a ativação de visitante por vários dispositivos afeta os dados que você vê nos relatórios.
seo-title: Impacto de dados da identificação de visitantes em vários dispositivos
solution: Analytics
subtopic: Visitantes
title: Impacto de dados da identificação de visitantes em vários dispositivos
topic: Desenvolvedor e implementação
uuid: 1 db 4 d 149-cd 50-4 b 41-a 850-988901 f 25051
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Impacto de dados da identificação de visitantes em vários dispositivos

>[!IMPORTANT]
>
>Não é mais recomendado este método de identificação de visitantes em dispositivos. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Visão geral de como a ativação de visitante por vários dispositivos afeta os dados que você vê nos relatórios.

Para compreender como esse recurso afeta a coleta de dados, é útil compreender os campos de dados do visitante em um perfil de visitante:

| Campo de dados | Descrição |
|---|---|
| Cookie da ID do visitante | ID gerada automaticamente na primeira visita de um dispositivo ou navegador e armazenado no código `s_vi`. |
| Variável da ID do visitante | [!UICONTROL ID de visitante] opcional definida com o uso da variável `s.visitorID`. Esse valor é preenchido depois que um usuário é autenticado e pode corresponder a uma ID que sua empresa usa para rastrear um usuário em vários canais de marketing digital. |
| ID efetiva do visitante | A [!UICONTROL ID efetiva do visitante] é a ID real para o perfil do usuário. Esse valor é definido como o cookie da [!UICONTROL ID do visitante] ou a variável da [!UICONTROL ID do visitante], caso uma tenha sido fornecida. |

