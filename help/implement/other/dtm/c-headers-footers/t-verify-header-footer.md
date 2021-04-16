---
description: Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.
keywords: Implementação do Analytics, método de implementação, Dynamic Tag Management, dtm, código, código de página, código de cabeçalho, código de rodapé, código de incorporação, código de verificação, código de cabeçalho de verificação, código de rodapé de verificação, guia incorporar, incorporar
title: Verificar o código do cabeçalho e do rodapé
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---

# Verificar o código do cabeçalho e do rodapé

Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.

1. Abra o site no navegador.
1. Abra o [!UICONTROL Console do desenvolvedor] clicando com o botão direito do mouse e selecionando **[!UICONTROL Inspecionar elemento]** > **[!UICONTROL Console]**.
1. Pressione **[!UICONTROL Enter]**.

   Se o código foi instalado corretamente, você verá a tela *`true`* no console.

   Se o código não tiver sido instalado corretamente, você verá a mensagem:

   `_satellite is not defined`

   Se receber essa mensagem de erro, verifique se:

* Você incluiu o código do cabeçalho completo em cada página do site na seção [!DNL HEAD], o mais próximo da tag `<head>` possível.
* Você não previu o surgimento de caracteres no trecho do código, possivelmente em resultado da ação de copiar e colar um documento formatado.
