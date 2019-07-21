---
description: Os caracteres e strings que nunca são permitidos em variáveis JavaScript.
keywords: Implementação do Analytics
seo-description: Os caracteres e strings que nunca são permitidos em variáveis JavaScript.
seo-title: Caracteres javascript inválidos
solution: Analytics
subtopic: Variáveis
title: Caracteres javascript inválidos
topic: Desenvolvedor e implementação
uuid: 04 e 3 b 4 b 4-7 ff 5-4673-8060-34302 b 6 ee 545
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caracteres javascript inválidos

Os caracteres e strings que nunca são permitidos em variáveis JavaScript.

* Tabulação (0x09)
* Retorno de carro (0x0D)
* Nova linha (0x0A)
* Caracteres ASCII com códigos acima de 127 (a menos que caracteres de vários bytes estejam ativados e *`charSet`* esteja preenchido adequadamente)
* HTML tags (e.g. <b></b> or &amp;#153)

Muitas variáveis, mais notavelmente produtos, hierarquia e eventos, têm limitações adicionais ou requisitos de sintaxe. Para obter as limitações individuais de variáveis e os requisitos de sintaxe, consulte a seção correspondente aos parâmetros da variável *`s_account`*.
