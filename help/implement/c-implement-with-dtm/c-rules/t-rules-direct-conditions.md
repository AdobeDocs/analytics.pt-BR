---
description: Crie condições para as regras de chamada direta.
keywords: Gerenciamento dinâmico de tags;regra;criar regra;nova regra;regra de chamada direta
seo-description: Crie condições para as regras de chamada direta.
seo-title: Crie condições para as regras de chamada direta
solution: Experience Cloud,Analytics,Target,Gerenciamento dinâmico de tags
title: Crie condições para as regras de chamada direta
uuid: bab0e058-a5b8-4039-8333-5e8f3d06ade4
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Crie condições para as regras de chamada direta

Crie condições para as regras de chamada direta.

1. In the **[!UICONTROL Conditions]** dialog, specify the string that will be passed to `_satellite.track()` in your direct call, without quotes.

   ![](assets/conditions-direct-call.png)

   >[!NOTE]
   >
   >If you specify the string that will be passed to `_satellite.track()` in your direct call using the UI, as described above, do not use quotation marks. If you insert [customized page code](../../../implement/c-implement-with-dtm/c-aa-tool/customize-page-code.md#concept_7D6390823DFE4D29AF9505CCE1A79C3B) using the editor, you must use quotation marks.

