---
description: 'null'
seo-description: 'null'
seo-title: Práticas recomendadas
title: Práticas recomendadas
uuid: 6 d 55 a 9 aa -030 e -4 e 4 d -963 c-ec 9 cc 38 e 1731
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Práticas recomendadas

## Preservar referências nas visualizações Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Quando você cria uma solicitação, ela sempre terá a mesma referência no Power BI. Mas caso exclua uma solicitação, a referência será usada por uma nova solicitação que for criada para a mesma dimensão.

Caso exclua uma solicitação da sua pasta de trabalho, tenha certeza de que não há uma visualização apontando para ela no Power BI, pois senão a visualização falhará.

* Se for possível, não exclua solicitações que você tenha criado no Construtor de relatórios
* Caso exclua solicitações no Construtor de relatórios, certifique-se também de excluir a visualização correspondente no Power BI.
* Caso não tenha certeza: exclua solicitações que não serão mais necessárias, republique-as e acesse o Power BI para ver quais visualizações foram quebradas

