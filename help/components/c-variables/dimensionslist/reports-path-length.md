---
description: Exibe, por porcentagem e contagem total, a profundidade de cada visita para o site. Em outras palavras, o relatório indica quantas páginas o visitante médio do site visualiza antes de sair.
title: Comprimento do caminho
topic: Reports
uuid: f1c29e78-279a-46a5-b758-d4f0da629239
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Comprimento do caminho

Exibe, por porcentagem e contagem total, a profundidade de cada visita para o site. Em outras palavras, o relatório indica quantas páginas o visitante médio do site visualiza antes de sair.

Links personalizados (s.tl calls) não são adicionados à extensão do caminho para páginas. Porém, eles são levados em conta na extensão do caminho para props (variáveis de tráfego).

Múltiplas instâncias do mesmo valor (recargas) não aumentam a extensão do caminho. Exemplos:

**[!UICONTROL Página A]** > **[!UICONTROL Página B]** > **[!UICONTROL Link personalizado]** > **[!UICONTROL Página B]** = Extensão do caminho de 2. (Observe que o link personalizado e a recarga da página B não contam na extensão do caminho).

**[!UICONTROL Prop A]** > **[!UICONTROL Link personalizado para Prop B]** > **[!UICONTROL Prop C]** = Extensão do caminho de 3. (Observe que o link personalizado para Prop B não conta na extensão do caminho).
