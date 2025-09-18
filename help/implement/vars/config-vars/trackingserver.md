---
title: trackingServer
description: O domínio usado para enviar dados para o Adobe por HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# trackingServer

>[!IMPORTANT]
>
>Essa variável está obsoleta. Com a prevalência de HTTPS, use [`trackingServerSecure`](trackingserversecure.md).

A variável `trackingServer` determina o domínio que o AppMeasurement usa para enviar dados para o Adobe por HTTP. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

Antes do [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home), essa variável também determinava onde os cookies de terceiros eram definidos. A Adobe recomenda usar o serviço de ID em todas as implementações, quando possível.

O AppMeasurement usa `trackingServer` como um fallback se [`trackingServerSecure`](trackingserversecure.md) não estiver definido. Muitas implementações mais antigas não definem `trackingServerSecure`, usando `trackingServer` como um fallback em páginas seguras. Com a prevalência de HTTPS, a Adobe recomenda usar `trackingServerSecure` quando possível.
