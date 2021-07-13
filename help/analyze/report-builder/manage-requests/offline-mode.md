---
description: O modo offline retorna dados de espaço reservado para acelerar o processo de criação e edição de solicitações.
title: Modo offline para criação e edição de solicitações
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 100%

---

# Modo offline para criação e edição de solicitações

O modo offline retorna dados de espaço reservado para acelerar o processo de criação e edição de solicitações.

Ao criar ou editar uma nova solicitação, são efetuadas chamadas da API de relatório para recuperar a resposta. Isso reduz o processo de criação de solicitação, pois é necessário aguardar para que os dados retornem antes de seguir para a próxima etapa. O modo offline retorna apenas dados do espaço reservado, portanto, não é necessário efetuar chamadas de API.

Para habilitar o modo offline:

1. Clique em **[!UICONTROL Opções]** no menu do Report Builder.

   ![](assets/offline_mode.png)

1. Marque a caixa de seleção ao lado de **[!UICONTROL Ativar o modo offline para criar e editar solicitações]**.
1. No campo **[!UICONTROL Exibir dados de métrica como]**, insira os dados de espaço reservado os quais você deseja que retornem na solicitação. Por exemplo, digite &quot;1&quot;.
1. Clique em **[!UICONTROL OK]**.
1. Agora, crie e execute sua solicitação (no modo offline) com o Assistente de solicitação.
1. Sua solicitação com &quot;1&quot; como dados de espaço reservado são semelhantes a isto:

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Certifique-se de desativar o Modo offline ao executar suas solicitações com dados reais. Para fazer isso, retorne às **[!UICONTROL Opções]** e remova a marca de seleção.
