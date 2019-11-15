---
description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Exemplo de visita
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Exemplo de visita

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a Documentação [do Device Co-op da](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

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
