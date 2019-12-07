---
description: A Adobe oferece algumas práticas recomendadas para atualizar seu código do Analytics.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Substituição de seu código do Analytics
topic: Developer and implementation
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Substituição de seu código do Analytics

A Adobe oferece algumas práticas recomendadas para atualizar seu código do Analytics.

Frequentemente, os clientes usam o [!UICONTROL Gerenciador de código] da Adobe para substituir seu código pela versão mais recente. Essa prática é boa, desde que você leve em conta alguns fatores.

## Uso da ID incorreta do servidor de coleta de dados {#section_1726CEB1ABEC408492569B06664410C8}

Ocasionalmente, os arquivos [!DNL s_code.js] que não foram gerados no Gerenciador de códigos da Adobe são enviados para quem está implementando código em seu site. Como resultado, a ID incorreta do servidor de coleta de dados (como mostrado na variável [!UICONTROL s.dc]) é usada para essa conta. É melhor gerar um novo código diretamente do [!UICONTROL Gerenciador de código] para um conjunto de relatórios específico que reutilizar o código de um conjunto de relatórios diferente. Essa é a melhor forma de garantir que a variável [!UICONTROL s.dc] seja preenchida corretamente.

## Plug-ins {#section_53650E52D6A54A4795F95E491E7548D1}

Alguns clientes implementam plug-ins para aprimorar a experiência na Adobe. Quando você substituir seu código, não esqueça que tem plug-ins como parte do código. O código criado no [!UICONTROL Gerenciador de códigos] não tem nenhum código de plug-in com ele, portanto todos os plug-ins devem migrar manualmente para a base de código mais recente. Faça uma cópia do código existente para usar caso algo ocorra e você precise reverter para o código anterior.
