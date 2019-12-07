---
description: Uma "camada de dados" é uma estrutura de objetos JavaScript que os desenvolvedores inserem nas páginas.
keywords: Analytics Implementation;data layer;digitalData
title: Camada de dados
topic: Developer and implementation
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Camada de dados

Uma _camada de dados_ é uma estrutura de objetos JavaScript que os desenvolvedores inserem nas páginas. As camadas de dados podem ser usadas pelas ferramentas de rastreamento (incluindo os sistemas de rastreamento de tags, como o Adobe Experience Platform Launch e o Dynamic Tag Management) para preencher relatórios.

A implementação de uma camada de dados no site fornece controle e flexibilidade definitivos sobre sua implementação e facilita a manutenção em fases futuras. Os nomes desses objetos JavaScript são teoricamente arbitrários, mas a prática recomendada é usar algo consistente e previsível. Os desenvolvedores podem já ter uma camada de dados ou uma preferência pelo formato. Existem alguns padrões diferentes que a comunidade de rastreamento criou como ponto de partida. O documento de especificação [Camada de dados para a implementação do Analytics](assets/datalayer-documentation.pdf) usa o objeto "digitalData" padrão do W3C, que é aceito pela grande maioria das tecnologias de rastreamento, caso haja necessidade de usar a camada de dados para mais do que essa implementação do DTM.
