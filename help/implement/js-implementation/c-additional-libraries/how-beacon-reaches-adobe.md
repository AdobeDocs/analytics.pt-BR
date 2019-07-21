---
description: Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web.
keywords: Implementação do Analytics; gateway; wap; i-mode; wbmp
seo-description: Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web.
seo-title: Gateway de rede de protocolo móvel
solution: Analytics
title: Gateway de rede de protocolo móvel
topic: Desenvolvedor e implementação
uuid: a 2 c 92 ce 2-53 a 9-4 b 5 b-be 1 a -89 d 9 f 1 bf 776 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gateway de rede de protocolo móvel

Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web.

Quando um dispositivo móvel solicita uma página de um servidor da Web, a solicitação é enviada por meio de um gateway, que converte a solicitação remota (geralmente no protocolo WAP ou I-Mode) em uma solicitação HTTP que é enviada a um servidor da Web. O servidor da Web responde ao gateway, que encaminha a solicitação para o telefone. Este gateway atua como um servidor proxy padrão. O gateway, no entanto, transmite a string do agente de usuário do dispositivo móvel no servidor da Web. Isso permite que o servidor Web responda com uma página que é criada especificamente para o dispositivo que a solicita.

Como o tamanho da tela em um dispositivo móvel WAP é limitado, as páginas móveis são muito leves, frequentemente contendo somente texto e uma imagem em cache. Quando a tag da imagem é adicionada às páginas, uma solicitação é enviada em todas as páginas para uma imagem dos servidores Adobe. Quando a imagem, uma WBMP, é retornada, os servidores Adobe instruem o navegador a não armazená-la em cache. Consequentemente, a imagem é solicitada novamente em páginas subsequentes. O número aleatório descrito acima deve ser usado para proteção contra navegadores que não obedecem as diretivas de não armazenamento em cache da Adobe.
