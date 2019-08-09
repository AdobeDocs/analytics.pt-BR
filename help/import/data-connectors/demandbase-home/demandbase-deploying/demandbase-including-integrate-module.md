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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Inclusão do módulo Integrate{#including-the-integrate-module}

O código de integração requer que o módulo de integração exista na implantação do Adobe Analytics.

Se você ainda não tiver o Módulo de integração como parte da implantação, conclua as etapas a seguir dependendo do tipo de implementação que você tiver.

## Para appmeasurement v 1.0 + {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Descompacte o arquivo zip do appmeasurement que você baixou do **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL codemanager]**.

1. Abra o arquivo chamado [!DNL AppMeasurement_Module_Integrate.js].
1. Copie e cole o conteúdo desse arquivo no [!DNL AppMeasurement.js] arquivo principal.

   >[!NOTE]
   >
   >Cole o comentário antes do comentário NÃO ALTERE NADA ABAIXO DESTA LINHA no arquivo.

## Para código herdado (código H) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Faça download do Módulo de integração na área «Recursos» na interface do usuário dos Conectores de dados (na guia Suporte).

   ![](assets/h_code.png)

1. Copie e cole o conteúdo desse arquivo em seu [!DNL s_code] arquivo.

   >[!NOTE]
   >
   >Cole o comentário antes do comentário NÃO ALTERE NADA ABAIXO DESTA LINHA no arquivo.

