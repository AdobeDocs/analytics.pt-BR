---
title: AppMeasurement para JavaScript
description: Saiba como implementar o Adobe Analytics usando JavaScript sem um sistema de gerenciamento de tags.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 100%

---


# AppMeasurement para JavaScript

O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics. No entanto, com a crescente popularidade dos sistemas de gerenciamento de tags, é recomendado usar o [Adobe Experience Platform Launch](../launch/overview.md).

## Fluxo de trabalho geral envia dados para a Adobe usando o JavaScript

1. Carregue o arquivo `AppMeasurement.js`. Esse arquivo contém as bibliotecas necessárias para enviar dados para a Adobe.

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. Defina as variáveis de configuração em `AppMeasurement.js`. Quando o objeto do Analytics é instanciado, essas variáveis garantem que as configurações de coleta de dados estejam corretas. Consulte [Variáveis de configuração](../vars/config-vars/configuration-variables.md) para obter uma lista completa de variáveis que podem ser definidas.

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. Defina variáveis de nível de página no código de página do site. Essas variáveis determinam dimensões e métricas específicas enviadas para a Adobe. Consulte [Variáveis de página](../vars/page-vars/page-variables.md) para obter uma lista completa de variáveis que podem ser definidas.

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. Quando todas as variáveis de nível de página forem definidas, envie os dados para a Adobe usando o método `t()`. Consulte [t](../vars/functions/t-method.md) para obter mais informações.

   ```js
   s.t();
   ```
