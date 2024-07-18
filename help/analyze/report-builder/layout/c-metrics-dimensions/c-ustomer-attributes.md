---
description: Os atributos do cliente são armazenados em um novo tipo de elemento chamado VisAttr, que pode ser configurado como uma dimensão ou uma métrica.
title: Atributos do cliente
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 83%

---

# Atributos do cliente

Os atributos do cliente são armazenados em um novo tipo de elemento chamado VisAttr, que pode ser configurado como uma dimensão ou uma métrica.

Para obter informações detalhadas sobre como fazer upload dos atributos do cliente, consulte a ajuda da [Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=pt-BR).

* Se for configurada como métrica, a VisAttr é exposta como métrica e &quot;dimensão&quot;.

  ![Captura de tela mostrando a métrica e os atributos do cliente da dimensão.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Comporta o mesmo detalhamento que uma eVar (qualquer item pode ser detalhado por qualquer coisa).
* A VisAttr é compatível com todas as métricas de eVar.
* A VisAttr como uma métrica suporta a &quot;compartimentalização&quot; (como Tempo no site: 0 a 30, 31 a 60…)
* A VisAttr está disponível como uma dimensão de segmentação.
