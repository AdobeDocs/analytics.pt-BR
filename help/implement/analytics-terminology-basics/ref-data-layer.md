---
description: Uma "camada de dados" é uma estrutura de objetos JavaScript que os desenvolvedores inserem nas páginas.
keywords: Implementação do Analytics; camada de dados; Digitaldata
seo-description: Uma "camada de dados" é uma estrutura de objetos JavaScript que os desenvolvedores inserem nas páginas. As camadas de dados podem ser usadas pelas ferramentas de rastreamento (incluindo sistemas de Tag Management como Dynamic Tag Management) para preencher relatórios.
seo-title: Camada de dados
solution: Analytics
title: Camada de dados
topic: Desenvolvedor e implementação
uuid: dedb 2 a 50-06 f 3-4354-8993-a 25 d 4952 ce 1 e
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# Camada de dados

A _data layer_ is a framework of JavaScript objects that developers insert into pages. As camadas de dados podem ser usadas por ferramentas de rastreamento (incluindo sistemas de gerenciamento de tags como o Adobe Experience Platform Launch e Gerenciamento dinâmico de tags) para preencher relatórios.

A implementação de uma camada de dados no site fornece controle e flexibilidade definitivos sobre sua implementação e facilita a manutenção em fases futuras. Os nomes desses objetos JavaScript são teoricamente arbitrários, mas a prática recomendada é usar algo consistente e previsível. Os desenvolvedores podem já ter uma camada de dados ou uma preferência para o formato. Existem alguns padrões diferentes que a comunidade de rastreamento criou como ponto de partida. O documento de especificação [Camada de dados para a implementação do Analytics](assets/datalayer-documentation.pdf) usa o objeto "digitalData" padrão do W3C, que é aceito pela grande maioria das tecnologias de rastreamento, caso haja necessidade de usar a camada de dados para mais do que essa implementação do DTM.
