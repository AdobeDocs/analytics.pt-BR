---
description: Habilite as dimensões de gerenciamento de consentimento.
title: Relatórios de privacidade
feature: Admin Tools
exl-id: 307c9ae2-2135-4a0b-9d2d-3c13a27b8361
source-git-commit: b5aba8a42f524ef3367a779e6fb1a731de680750
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 45%

---

# Relatórios de privacidade

Os relatórios de privacidade permitem ativar o [Aceitação no gerenciamento de consentimento](/help/components/dimensions/cm-opt-in.md), [Recusa no gerenciamento de consentimento](/help/components/dimensions/cm-opt-out.md) e [Consentimento de publicidade](/help/components//dimensions/ad-consent.md) dimensões para usar em relatórios.

>[!NOTE]
>
>Adicionamos um novo sinalizador de Consentimento da plataforma de anúncio. Você precisa reativar os Relatórios da Privacidade de dados se quiser que essa nova variável entre em vigor.

Para acessar esta página:

1. Faça logon no Adobe Analytics e acesse **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione um ou mais conjuntos de relatórios e, em seguida, selecione **[!UICONTROL Editar configurações]** > **[!UICONTROL Gerenciamento de privacidade]** > **[!UICONTROL Relatórios de privacidade]**.

   ![Editar configurações](assets/rsm-privacy-select.png)

1. Clique em **[!UICONTROL Ativar relatórios de privacidade de dados]**.

   >[!NOTE]
   >
   >Após ativadas, essas variáveis não podem ser desativadas.

   ![Ativar](assets/rsm-privacy-enable.png)

1. Depois de ativado, uma mensagem de confirmação é exibida. As dimensões estarão disponíveis em relatórios.

   ![Relatório](assets/consent-management.png)

## Dimensão Consentimento de anúncio

A variável [Dimensão Consentimento de anúncio](/help/components/dimensions/ad-consent.md) exibe se o consentimento é coletado para enviar dados a provedores de publicidade de terceiros, como Google, Meta e outros.