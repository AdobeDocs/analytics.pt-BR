---
description: Muitos navegadores da Web não exibem o conteúdo de uma tabela antes de o navegador compilar completamente a tabela.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Tabela
topic: Developer and implementation
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tabela

Muitos navegadores da Web não exibem o conteúdo de uma tabela antes de o navegador compilar completamente a tabela.

Se todo o conteúdo da página estiver dentro de uma grande tabela, o navegador deverá compilar todo o conteúdo da página antes que tudo seja exibido.

A inserção da chamada para o arquivo da biblioteca de JavaScript fora das tags da tabela garante que a chamada para os servidores do Analytics não afete a exibição do conteúdo da página.

> [!NOTE] O arquivo deve ser colocado em uma posição legal para imagens e deve ser exibido entre a tag de abertura <body> e o fechamento </body> TAG.

