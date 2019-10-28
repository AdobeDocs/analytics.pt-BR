---
description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
keywords: Implementação do Analytics
seo-description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
seo-title: Exemplo de visita
solution: Analytics
subtopic: Visitantes
title: Exemplo de visita
topic: Desenvolvedor e implementação
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Exemplo de visita

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a [Documentação de cooperação do dispositivo da Adobe Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcdc/).

Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.

| Chamada do servidor | Ação | Cookie da ID do visitante | Variável da ID do visitante | ID efetiva do visitante | Número de página da visita | Número da visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Um visitante clica em um link em um email de marketing e visita seu site, usando seu computador pessoal. Esse visitante já visitou o site 7 outras vezes no passado. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita 7 páginas adicionais no seu site. | 1 | - | 1 | 2-8 | 8 |
| 9 | Autentifica no computador pessoal. | 1 | CID1 | CID1 | 9 <br>Este é o primeiro hit do CID1, por isso ele assume o controle e continua no perfil do visitante a partir da ID de visitante 1.</br> | 8 |
| 10 | Visita uma página adicional. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Abre o site em seu laptop, no escritório. O visitante não visitou o site antes de utilizar esse dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Autentifica em laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualiza 1 página adicional. | 2 | CID1 | CID1 | 2 | 9 |