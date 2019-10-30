---
description: A colocação da chamada para o arquivo da biblioteca de JavaScript na parte superior da página garante que a imagem fique entre os primeiros elementos a serem baixados.
keywords: Implementação do Analytics
seo-description: A colocação da chamada para o arquivo da biblioteca de JavaScript na parte superior da página garante que a imagem fique entre os primeiros elementos a serem baixados.
seo-title: Localização e simultaneidade do arquivo JavaScript
solution: Analytics
subtopic: Solução de problemas
title: Localização e simultaneidade do arquivo JavaScript
topic: Desenvolvedor e implementação
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Localização e simultaneidade do arquivo JavaScript

A colocação da chamada para o arquivo da biblioteca de JavaScript na parte superior da página garante que a imagem fique entre os primeiros elementos a serem baixados.

A maioria dos navegadores da Web baixa imagens ao mesmo tempo. Geralmente, é possível baixar três a quatro imagens por vez.

Como a maioria dos navegadores da Web baixa elementos ao mesmo tempo, a barra de status de muitos navegadores comuns (incluindo o Internet Explorer) não reflete precisamente o elemento que o navegador está tentando baixar. Por exemplo, sua barra de status pode mostrar que o navegador está esperando o download da imagem 1. Os testes do pacote de rede mostram que seu navegador já recebeu a imagem 1 e está aguardando, simultaneamente, a imagem 2.

> [!NOTE] Como provedores de Auditoria de desempenho de internet de terceiros (como sistemas Keynote) baixam elementos de imagem da página sequencialmente e não simultaneamente, eles não simulam a experiência típica do usuário.

