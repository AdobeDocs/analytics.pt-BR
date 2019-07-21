---
description: Um contador armazena (e às vezes exibe) o número de vezes que um evento ou processo específico ocorreu.
keywords: Implementação do Analytics; props; s. prop; tráfego personalizado; contadores
seo-description: Um contador armazena (e às vezes exibe) o número de vezes que um evento ou processo específico ocorreu.
seo-title: Uso de props como contadores
solution: Analytics
title: Uso de props como contadores
topic: Desenvolvedor e implementação
uuid: ab 83 bd 7 e -10 d 9-49 f 9-b 9 e 7-c 50397 e 95 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso de props como contadores

Um contador armazena (e às vezes exibe) o número de vezes que um evento ou processo específico ocorreu.

Você pode usar um prop para contar o número de vezes que um evento ocorre. Por exemplo, você quer rastrear o uso do Real Player em comparação ao Windows Media Player em seu site. Cada página contém o [!UICONTROL Código para colar], em que você pode ver as variáveis [!UICONTROL s.prop]. Use [!UICONTROL s.prop] 1 para rastrear os players. Para a página A, insira o valor em [!UICONTROL s.prop]1 para representar o Real Player.

```js
s.prop1="RealPlayer"
```

Na página B, insira um valor semelhante no [!UICONTROL s.prop]1 para o Windows Media Player, como mostrado abaixo.

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

Quando os visitantes vão ao seu site e vistam as páginas contendo o Real Player ou o Windows Media Player, o [!DNL Analytics] pode segmentar os usuários com base nas páginas visitadas. O relatório [!UICONTROL Tráfego personalizado] mostra então o número de visitas em cada página.

>[!NOTE]
>
>The name of the [!UICONTROL Custom Traffic] report can be customized. Por exemplo, é possível renomear o relatório de [!UICONTROL Tráfego personalizado] como "Relatório de tipos de players".

