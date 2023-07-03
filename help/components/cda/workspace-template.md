---
title: Modelo do CDA Workspace
description: Descreve cada campo no modelo CDA no Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 96%

---

# Modelo do CDA Workspace

A Adobe oferece um modelo para ver dados essenciais de desempenho entre dispositivos.

1. Navegue até [experience.adobe.com](https://experiencecloud.adobe.com) e faça logon usando as credenciais da Adobe ID.
1. Clique no ícone de 9-grid na parte superior e clique em Analytics.
1. Clique em [!UICONTROL Workspace] na parte superior e em seguida em [!UICONTROL Criar novo projeto].
1. Localize o modelo “Análise entre dispositivos” e clique em [!UICONTROL Criar].
1. Se solicitado, altere o conjunto de relatórios para um compatível com CDA.

É criado um projeto do Analysis Workspace com vários painéis. Na parte superior, um índice e uma introdução são mostrados, permitindo o contexto do relatório e a navegação para relatórios individuais. Clique em um link dentro do índice ou expanda a tabela de um painel para visualizar esses relatórios.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identificação de usuários**: mostra a frequência com que os visitantes do site são identificados usando métodos com base na Análise entre dispositivos.
* **Medição do tamanho do público-alvo**: mostra uma comparação entre &quot;Dispositivos únicos&quot; e &quot;Pessoas&quot;. A proporção desses dois números é conhecida como &quot;compactação entre dispositivos&quot;, uma métrica calculada visível neste painel. Essa métrica de compactação depende de vários fatores:
   * Taxa de logon: quanto mais usuários entrarem no site, mais a Adobe poderá identificar e compilar visitantes entre dispositivos. Os sites com uma taxa de logon baixa também têm taxas de compactação baixas.
   * Cobertura da Experience Cloud ID: somente os visitantes com uma ECID podem ser compilados. Uma porcentagem menor de visitantes do site que usam uma ECID está correlacionada a taxas de compactação mais baixas.
   * Uso de vários dispositivos: se os visitantes do site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
   * Granularidade do relatório: a compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, a filtragem ou o uso de dimensões de detalhamento também podem mostrar uma taxa de compactação menor.
* **Segmentos com base em pessoas**: contém uma lista suspensa de segmentos que permite visualizar dados específicos do dispositivo. Esse painel incentiva a experimentação com segmentos para ver como a inclusão ou exclusão de tipos de dispositivos afetam os relatórios.
* **Análise da jornada entre dispositivos**: fornece relatórios de fluxo e fallout de acordo com o tipo de dispositivo.
* **Atribuição entre dispositivos**: combine os recursos de Journey IQ e Attribution IQ.
* **Outras dicas e truques**: tópicos úteis sobre o CDA que permitem que você o aproveite ao máximo.
