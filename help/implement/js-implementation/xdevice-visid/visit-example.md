---
description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
keywords: Implementação do Analytics
seo-description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
seo-title: Exemplo de visita
solution: Analytics
subtopic: Visitantes
title: Exemplo de visita
topic: Desenvolvedor e implementação
uuid: bc 5 f 8 f 56-52 e 3-42 d 8-af 1 a -7 f 5 c 7 b 9496 c 0
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Exemplo de visita

>[!IMPORTANT]
>
>Não é mais recomendado este método de identificação de visitantes em dispositivos. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.

| Chamada do servidor | Ação | Cookie da ID do visitante | Variável da ID do visitante | ID efetiva do visitante | Número de página da visita | Número da visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Um visitante clica em um link em um email de marketing e visita seu site, usando seu computador pessoal. Esse visitante já visitou o site 7 outras vezes no passado. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita 7 páginas adicionais no seu site. | 1 | - | 1 | 2-8 | 8 |
| 9 | Autentifica no computador pessoal. | 1 | CID1 | CID1 | 9 <br>This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br> | 8 |
| 10 | Visita uma página adicional. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Abre o site em seu laptop, no escritório. O visitante não visitou o site antes de utilizar esse dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Autentifica em laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualiza 1 página adicional. | 2 | CID1 | CID1 | 2 | 9 |