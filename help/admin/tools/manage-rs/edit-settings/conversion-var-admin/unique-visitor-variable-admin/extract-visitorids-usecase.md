---
description: O Data Warehouse fornece um recurso que permite extrair uma lista de IDs de visitante. Essas IDs não são IDs de cookie, mas IDs que você captura em uma de suas variáveis de conversão. Embora existam outras maneiras de obter essas informações, o exemplo a seguir é um atalho para gerar uma solicitação Data Warehouse.
title: Caso de uso - Extraindo IDs de visitantes
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
TQID: https://experienceleague.adobe.com/CUpKcu-jVNn77bkWM2mJvlLxYMyvfpRt4o-maC7tUBA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 19%

---

# Caso de uso - Extraindo IDs de visitantes

O Data Warehouse fornece um recurso que permite extrair uma lista de IDs de visitante. Essas IDs não são IDs de cookie, mas IDs que você captura em uma de suas variáveis de conversão. Embora existam outras maneiras de obter essas informações, o exemplo a seguir é um atalho para gerar uma solicitação Data Warehouse.

Por exemplo, considera que seus negócios enviam emails de marketing a clientes atuais e potenciais. Cada um desses destinatários de email tem uma ID exclusiva em seu sistema de email (como *`EMAIL Contact ID`*). Você configura seus e-mails para que, quando os contatos receberem um e-mail e clicarem em um de seus links, o visitante chegue ao seu site com uma ID da campanha e uma ID de contato de E-MAIL exclusiva. Por exemplo, seu link de email pode resolver para:

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

Definir esses parâmetros nas variáveis de conversão (eVars) permite que você veja como cada email foi executado (por meio da ID da campanha) e com que frequência cada destinatário de email visitou o site (por meio da ID de contato de EMAIL).

Suponha que você esteja capturando essas IDs. A maioria dos profissionais de marketing quer segmentar o comportamento do site e, em seguida, ver se podem fazer o remarketing para aqueles que atendem a determinados critérios. Por exemplo, talvez você queira enviar um email de remarketing para todos os destinatários de email que vieram do email para o seu site e visualizaram (ou preencheram) um formulário de site. Para fazer isso, encontre uma maneira de identificar as IDs de contato de EMAIL daqueles que preenchem o formulário específico.

Uma maneira de fazer isso é usar um relatório de Sub-relação de Conversão para detalhar o valor de eVar da ID de formulário pelo eVar da ID de contato de EMAIL. No entanto, um recurso pré-criado está disponível para fazer isso usando o Data Warehouse. Esse recurso permite que você informe qual eVar armazena suas IDs de usuário exclusivas (neste caso, ID de contato de EMAIL) e permite que você extraia facilmente essas IDs usando um Data warehouse. Por meio desse recurso você pode criar automaticamente uma solicitação de Data warehouse que puxa as IDs de visitante único nas quais tem interesse.
