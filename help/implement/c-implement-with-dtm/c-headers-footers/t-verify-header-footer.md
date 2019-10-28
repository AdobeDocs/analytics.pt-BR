---
description: Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.
keywords: Implementação do Analytics, método de implementação, Dynamic Tag Management, dtm, código, código de página, código de cabeçalho, código de rodapé, código de incorporação, código de verificação, código de cabeçalho de verificação, código de rodapé de verificação, guia incorporar, incorporar
seo-description: Verifique se sua biblioteca de Dynamic Tag Management é carregada corretamente no site.
seo-title: Verificar o código do cabeçalho e do rodapé
solution: Analytics
title: Verificar o código do cabeçalho e do rodapé
topic: Desenvolvedor e implementação
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

* Você incluiu o código do cabeçalho completo em cada página do site na seção [!DNL HEAD], o mais próximo possível da tag [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">]
* Você não previu o surgimento de caracteres no trecho do código, possivelmente em resultado da ação de copiar e colar um documento formatado.

