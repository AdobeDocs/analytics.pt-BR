---
description: Um contador armazena (e às vezes exibe) o número de vezes que um evento ou processo específico ocorreu.
keywords: Analytics Implementation;props;s.prop;custom traffic;counters
title: Uso de props como contadores
topic: Developer and implementation
uuid: ab83bd7e-10d9-49f9-b9e7-c50397e95c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

> [!NOTE] A Adobe oferece até 75 variáveis [!UICONTROL s.prop] para você usar.

Quando os visitantes vão ao seu site e vistam as páginas contendo o Real Player ou o Windows Media Player, o [!DNL Analytics] pode segmentar os usuários com base nas páginas visitadas. O relatório [!UICONTROL Tráfego personalizado] mostra então o número de visitas em cada página.

> [!NOTE] O nome do relatório [!UICONTROL Tráfego personalizado] pode ser personalizado. Por exemplo, é possível renomear o relatório de [!UICONTROL Tráfego personalizado] como "Relatório de tipos de players".

