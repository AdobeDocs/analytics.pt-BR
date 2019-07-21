---
description: Muitos navegadores da Web não exibem o conteúdo de uma tabela antes de o navegador compilar completamente a tabela.
keywords: Implementação do Analytics
seo-description: Muitos navegadores da web não exibem o conteúdo de uma tabela antes de o navegador compilar completamente a tabela.
seo-title: Tabela
solution: Analytics
subtopic: Solução de problemas
title: Tabela
topic: Desenvolvedor e implementação
uuid: f 72 d 7894-38 bd -4926-bce 4-0 c 6 af 7278 c 63
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Tabela

Muitos navegadores da Web não exibem o conteúdo de uma tabela antes de o navegador compilar completamente a tabela.

Se todo o conteúdo da página estiver dentro de uma grande tabela, o navegador deverá compilar todo o conteúdo da página antes que tudo seja exibido.

A inserção da chamada para o arquivo da biblioteca de JavaScript fora das tags da tabela garante que a chamada para os servidores do Analytics não afete a exibição do conteúdo da página.

>[!NOTE]
>
>O arquivo deve ser colocado em uma posição legal para imagens e deve ser exibido entre a abertura <body> tag e o fechamento </body> tag.

