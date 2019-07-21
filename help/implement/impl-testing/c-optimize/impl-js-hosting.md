---
description: A colocação da chamada para o arquivo da biblioteca de JavaScript na parte superior da página garante que a imagem fique entre os primeiros elementos a serem baixados.
keywords: Implementação do Analytics
seo-description: A colocação da chamada para o arquivo da biblioteca de JavaScript na parte superior da página garante que a imagem fique entre os primeiros elementos a serem baixados.
seo-title: Localização e concurrência do arquivo javascript
solution: Analytics
subtopic: Solução de problemas
title: Localização e concurrência do arquivo javascript
topic: Desenvolvedor e implementação
uuid: ed 5118 a 8-b 142-4 fab -8 aa 1-92 d 931 cc 1439
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Localização e concurrência do arquivo javascript

A colocação da chamada para o arquivo da biblioteca de JavaScript na parte superior da página garante que a imagem fique entre os primeiros elementos a serem baixados.

A maioria dos navegadores da Web baixa imagens ao mesmo tempo. Geralmente, é possível baixar três a quatro imagens por vez.

Como a maioria dos navegadores da Web baixa elementos ao mesmo tempo, a barra de status de muitos navegadores comuns (incluindo o Internet Explorer) não reflete precisamente o elemento que o navegador está tentando baixar. Por exemplo, sua barra de status pode mostrar que o navegador está esperando o download da imagem 1. Os testes do pacote de rede mostram que seu navegador já recebeu a imagem 1 e está aguardando, simultaneamente, a imagem 2.

>[!NOTE]
>
>Como provedores de Auditoria de desempenho de Internet de terceiros (como Sistemas Keynote) fazem download de elementos da imagem da página sequencialmente, e não simultaneamente, não simulam a experiência típica do usuário.

