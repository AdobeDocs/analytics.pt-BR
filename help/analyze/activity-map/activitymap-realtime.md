---
description: A análise de página em tempo real (modo Online) permite obter resultados com granularidade mínima em tempo real.
title: Análise de página em tempo real (Online)
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 71%

---


# Análise de página em tempo real (modo Online)

A análise de página em tempo real (modo Online) permite obter resultados com granularidade mínima em tempo real.

O Activity Map agora exibe dados analíticos em incrementos de 1 a 15 minutos para monitorar a popularidade do link com base nas microtendências das páginas selecionadas. Isso é muito importante para a publicação de empresas, para rastrear e responder ao aumento ou diminuição do interesse em histórias e para monitorar o fluxo de tráfego em tempo real.

Como proprietário de conteúdo em um site, parte de seu trabalho é compreender quando promover e remover o conteúdo e manter a experiência constantemente relevante. Os dados em tempo real são fundamentais para essa responsabilidade. Se você compreender quais as tendências dos links e conteúdo, é possível agir rapidamente e decisivamente para manter os leitores e clientes envolvidos com a sua marca.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Se você quiser verificar qual elemento é mais clicado no modo Online:

1. Selecione o período na linha de tendência **[!UICONTROL Modo Online]** da Barra de Ferramentas que deseja analisar.
1. Clique no ícone &quot;Olho&quot; na barra de ferramentas para acessar a Tabela de relatórios de links.
1. Ordenar a tabela pelo Link.

## Latência dos dados como resultado da configuração A4T

Depois que a [A4T integration](https://docs.adobe.com/content/help/pt-BR/target/using/integrate/a4t/a4t.html) for ativada no Adobe Target, haverá de 5 a 10 minutos adicionais de latência no Adobe Analytics. O aumento dessa latência permite que os dados do Analytics e Target sejam armazenados no mesmo hit, permitindo dividir os testes por página e seção do site.

Este aumento é refletido em todos os serviços e ferramentas do Adobe Analytics, incluindo a transmissão ao vivo e os relatórios em tempo real e aplicam-se nas seguintes situações:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para os dados atuais sobre as métricas de conversão, dados finalizados e feeds de dados, todos os hits são atrasados de 5 a 7 minutos.

Esteja ciente de que o aumento da latência começa após a implementação do [Identity Service](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html), mesmo que essa integração não tenha sido integralmente implementada.

Mais informações [aqui](/help/analyze/activity-map/activitymap-standard-live.md).