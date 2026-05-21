---
title: account
description: (Desativado) Determine o conjunto de relatórios para o qual os dados são enviados.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: https://experienceleague.adobe.com/TmNxbAFJXxEnMJZNNZKP1ldkmeYICEzKdNoptNChzko
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>Essa variável foi removida. Use a função [`s.sa()`](../functions/sa-method.md) se a implementação exigir que modifique o destino do conjunto de relatórios.

Em versões anteriores do Adobe Analytics, a variável `account` determinava o conjunto de relatórios para o qual você deseja enviar dados. É necessária uma ID de conjunto de relatórios para enviar dados ao Adobe Analytics.

* Se você usar o Web SDK, os conjuntos de relatórios estarão nas configurações de serviço do Adobe Analytics na sequência de dados para a qual o Web SDK envia dados.
* Se você usar a extensão do Adobe Analytics, os conjuntos de relatórios ficarão na opção [!UICONTROL Gerenciamento de biblioteca] ao configurar a extensão do Adobe Analytics.
* Se você usar a função [`s_gi()`](../functions/s-gi.md) para instanciar um objeto de rastreamento do Analytics, as IDs do conjunto de relatórios já existem como um argumento obrigatório na função.
