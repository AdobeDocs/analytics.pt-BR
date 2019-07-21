---
description: Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.
keywords: Implementação do Analytics; método de implementação; gerenciamento dinâmico de tags; dtm; code; código de página; código do cabeçalho; código do rodapé; código incorporado; verificar o código; verificar o código do cabeçalho; verificar o código do rodapé; tabulação incorporada; embed
seo-description: Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.
seo-title: Verificar o código do cabeçalho e do rodapé
solution: Analytics
title: Verificar o código do cabeçalho e do rodapé
topic: Desenvolvedor e implementação
uuid: d 395 a 417-0 c 61-41 a 6-a 124-d 2 f 400 f 4626 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Verificar o código do cabeçalho e do rodapé

Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.

1. Abra o site no navegador.
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   Se o código não tiver sido instalado corretamente, você verá a mensagem:

   `_satellite is not defined`

   Se receber essa mensagem de erro, verifique se:

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] possível.
* Você não previu o surgimento de caracteres no trecho do código, possivelmente em resultado da ação de copiar e colar um documento formatado.

