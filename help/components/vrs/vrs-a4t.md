---
description: Considerações especiais ao usar o A4T e conjuntos de relatórios virtuais do Adobe Analytics
title: Conjuntos de relatórios virtuais e Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 100%

---

# Conjuntos de relatórios virtuais e Analytics for Target (A4T)

Considere estes avisos ao usar conjuntos de relatórios virtuais no contexto do Adobe Target:

* Não é possível enviar dados diretamente do Target para um conjunto de relatórios virtual, somente para um conjunto de relatórios real.
* Você pode criar relatórios sobre atividades do A4T em um conjunto de relatórios virtual. No entanto, os dados do A4T são limitados às linhas que correspondem ao segmento do conjunto de relatórios virtual (e a qualquer outro segmento aplicado). Por exemplo, se você tiver criado um conjunto de relatórios virtual para seus clientes EMEA, os dados A4T desse conjunto refletirão apenas os dados do Target para seus clientes EMEA.
* Não é possível publicar segmentos de um conjunto de relatórios virtual de volta no Target para ativação.
