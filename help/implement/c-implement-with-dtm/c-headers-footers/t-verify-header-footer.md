---
description: Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: Verificar o código do cabeçalho e do rodapé
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Verificar o código do cabeçalho e do rodapé

Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.

1. Abra o site no navegador.
1. Abra o [!UICONTROL Console do desenvolvedor] clicando com o botão direito do mouse e selecionando **[!UICONTROL Inspecionar elemento]** &gt; **[!UICONTROL Console]**.
1. Pressione **[!UICONTROL Enter]**.

   Se o código foi instalado corretamente, você verá a tela *`true`* no console.

   Se o código não tiver sido instalado corretamente, você verá a mensagem:

   `_satellite is not defined`

   Se receber essa mensagem de erro, verifique se:

* Você incluiu o código do cabeçalho completo em cada página do site na seção [!DNL HEAD], o mais próximo possível da tag [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] tag o mais possível.
* Você não previu o surgimento de caracteres no trecho do código, possivelmente em resultado da ação de copiar e colar um documento formatado.

