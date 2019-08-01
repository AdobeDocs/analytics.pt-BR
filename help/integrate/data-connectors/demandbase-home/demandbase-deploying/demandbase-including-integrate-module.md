---
description: O código de integração requer que o módulo de integração exista na implantação do Adobe Analytics.
seo-description: O código de integração requer que o módulo de integração exista na implantação do Adobe Analytics.
seo-title: Inclusão do módulo Integrate
title: Inclusão do módulo Integrate
uuid: e 574 f 3 db -49 fa -4 f 72-bbcf-fd 98540 d 3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

O código de integração requer que o módulo de integração exista na implantação do Adobe Analytics.

Se você ainda não tiver o Módulo de integração como parte da implantação, conclua as etapas a seguir dependendo do tipo de implementação que você tiver.

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Unzip the AppMeasurement zip file that you downloaded from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager]**.

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >Cole o comentário antes do comentário NÃO ALTERE NADA ABAIXO DESTA LINHA no arquivo.

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Faça download do Módulo de integração na área «Recursos» na interface do usuário dos Conectores de dados (na guia Suporte).

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >Cole o comentário antes do comentário NÃO ALTERE NADA ABAIXO DESTA LINHA no arquivo.

