---
description: A análise de página em tempo real (modo Online) permite obter resultados com granularidade mínima em tempo real.
seo-description: A análise de página em tempo real (modo Online) permite obter resultados com granularidade mínima em tempo real.
seo-title: Análise de página em tempo real (Live)
solution: Analytics
title: Análise de página em tempo real (Live)
topic: Activity Map
uuid: a 3 faa 9 bd -73 d 8-48 b 3-be 2 b-f 818 ed 7456 fb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Análise de página em tempo real (Live)

A análise de página em tempo real (modo Online) permite obter resultados com granularidade mínima em tempo real.

O Activity Map agora exibe dados analíticos em incrementos de 1 a 15 minutos para monitorar a popularidade do link com base nas microtendências das páginas selecionadas. Isso é muito importante para a publicação de empresas, para rastrear e responder ao aumento ou diminuição do interesse em histórias e para monitorar o fluxo de tráfego em tempo real.

Como proprietário de conteúdo em um site, parte de seu trabalho é compreender quando promover e remover o conteúdo e manter a experiência constantemente relevante. Os dados em tempo real são fundamentais para essa responsabilidade. Se você compreender quais as tendências dos links e conteúdo, é possível agir rapidamente e decisivamente para manter os leitores e clientes envolvidos com a sua marca.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

Depois que a integração A4T for habilitada no Adobe Target, haverá de 5 a 10 minutos adicionais de latência no Adobe Analytics. O aumento dessa latência permite que os dados do Analytics e Target sejam armazenados no mesmo hit, permitindo dividir os testes por página e seção do site.

Este aumento é refletido em todos os serviços e ferramentas do Adobe Analytics, incluindo a transmissão ao vivo e os relatórios em tempo real e aplicam-se nas seguintes situações:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para os dados atuais sobre as métricas de conversão, dados finalizados e feeds de dados, todos os hits são atrasados de 5 a 7 minutos.

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
