---
description: Saiba como usar o modo offline para retornar dados de espaço reservado.
title: Como ativar o modo offline
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 15%

---

# Modo offline para criação e edição de solicitações

{{legacy-arb}}

O modo offline retorna dados de espaço reservado para acelerar o processo de criação e edição de solicitações.

Ao criar ou editar uma nova solicitação, são feitas chamadas da API de relatório para recuperar a resposta. Às vezes, essas chamadas retardam o processo de criação de solicitações, pois é necessário aguardar o retorno dos dados antes de seguir para a próxima etapa. O modo offline retorna somente dados de espaço reservado e a API não é criada.

Para ativar o modo offline

1. Clique em **[!UICONTROL Opções]** no menu do Report Builder.

   ![Captura de tela da tela Opções com o modo offline selecionado.](assets/offline_mode.png)

1. Marque a caixa de seleção ao lado de **[!UICONTROL Ativar modo offline para criar e editar solicitações]**.
1. No campo **[!UICONTROL Exibir Dados de Métrica como]**, insira os dados de espaço reservado que você deseja retornar na solicitação. Por exemplo, digite &quot;1&quot;.
1. Clique em **[!UICONTROL OK]**.
1. Crie e execute sua solicitação no modo off-line usando o Assistente de solicitação. A captura de tela a seguir mostra um exemplo de uma solicitação com &quot;1&quot; como os dados de espaço reservado.

   ![Captura de tela mostrando o exemplo de modo offline usando 1 como um espaço reservado.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Certifique-se de desativar o Modo offline antes de executar suas solicitações com dados reais.
