---
description: O Data Warehouse fornece um recurso que permite a extração de uma lista de IDs do visitante. Essas IDs não são IDs de cookie, mas IDs capturadas em uma de suas variáveis de conversão. Embora existam outras maneiras de obter essas informações, o exemplo a seguir é um atalho para gerar uma solicitação de Data Warehouse.
seo-description: O Data Warehouse fornece um recurso que permite a extração de uma lista de IDs do visitante. Essas IDs não são IDs de cookie, mas IDs capturadas em uma de suas variáveis de conversão. Embora existam outras maneiras de obter essas informações, o exemplo a seguir é um atalho para gerar uma solicitação de Data Warehouse.
seo-title: Caso de uso - Extraindo IDs de visitantes
solution: Analytics
title: Caso de uso - Extraindo IDs de visitantes
topic: Ferramentas administrativas
uuid: ed 228334-619 c -43 d 7-b 781-a 18 af 73 b 00 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caso de uso - Extraindo IDs de visitantes

O Data Warehouse fornece um recurso que permite a extração de uma lista de IDs do visitante. Essas IDs não são IDs de cookie, mas IDs capturadas em uma de suas variáveis de conversão. Embora existam outras maneiras de obter essas informações, o exemplo a seguir é um atalho para gerar uma solicitação de Data Warehouse.

Por exemplo, considera que seus negócios enviam emails de marketing a clientes e compradores em potencial. Cada um desses destinatários de email tem uma ID exclusiva em seu sistema de email (como *`EMAIL Contact ID`*). Você configura seus emails para que um contato ao receber um email e clicar em um de seus links, o visitante possa chegar no site com uma ID da campanha e uma ID de contato de EMAIL exclusiva. Por exemplo, seu link de email pode resolver:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

Configurá-los em variáveis de conversão (eVars) permite que você veja o desempenha de cada email (pela ID da campanha) e quão frequentemente cada destinatário de email visitou o site (pela ID de contato de EMAIL).

Considere que você está capturando essas IDs. A maioria dos que trabalham com marketing querem segmentar o comportamento de seus sites e ver se conseguem fazer novamente o marketing para aqueles que atender a determinados critérios. Por exemplo, você pode querer enviar um email com novo marketing para todos os destinatários de email que vieram até site pelo email e exibiram (ou preencheram) um formulário do site. Para fazer isso, encontre uma maneira de identificar as ID de contato de EMAIL daqueles que preenchem o formulários específico.

Uma maneira de fazer isso é usar um relatório de Sub-relação de conversão para detalhar a o valor da eVar da ID do formulário pela eVar da ID do contato de EMAIL. No entanto, um recurso pré-integrado está disponível para isso usando um Data Warehouse. Esse recurso permite que você informe qual eVar armazena suas IDs de usuário exclusivas (neste caso, ID de contato de EMAIL) e permite que você extraia facilmente essas IDs usando um data warehouse. Por meio desse recurso você pode criar automaticamente uma solicitação de data warehouse que puxa as IDs de visitante único nas quais tem interesse.
