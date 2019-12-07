---
description: Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web.
keywords: Analytics Implementation;gateway;wap;i-mode;wbmp
title: Gateway de rede para protocolo móvel
topic: Developer and implementation
uuid: a2c92ce2-53a9-4b5b-be1a-89d9f1bf776f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gateway de rede para protocolo móvel

Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web.

Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web. O servidor da Web responde ao gateway, que encaminha a solicitação para o telefone. Este gateway atua como um servidor proxy padrão. O gateway, no entanto, transmite a string do agente de usuário do dispositivo móvel no servidor da Web. Isso permite que o servidor Web responda com uma página que é criada especificamente para o dispositivo que a solicita.

Como o tamanho da tela em um dispositivo móvel WAP é limitado, as páginas móveis são muito leves, frequentemente contendo somente texto e uma imagem em cache. Quando a tag da imagem é adicionada às páginas, uma solicitação é enviada em todas as páginas para uma imagem dos servidores Adobe. Quando a imagem, uma WBMP, é retornada, os servidores Adobe instruem o navegador a não armazená-la em cache. Consequentemente, a imagem é solicitada novamente em páginas subsequentes. O número aleatório descrito acima deve ser usado para proteção contra navegadores que não obedecem as diretivas de não armazenamento em cache da Adobe.
