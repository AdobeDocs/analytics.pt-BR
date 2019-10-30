---
description: Os caracteres e strings que nunca são permitidos em variáveis JavaScript.
keywords: Implementação do Analytics
seo-description: Os caracteres e strings que nunca são permitidos em variáveis JavaScript.
seo-title: Caracteres JavaScript inválidos
solution: Analytics
subtopic: Variáveis
title: Caracteres JavaScript inválidos
topic: Desenvolvedor e implementação
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Caracteres JavaScript inválidos

Os caracteres e strings que nunca são permitidos em variáveis JavaScript.

* Tabulação (0x09)
* Retorno de carro (0x0D)
* Nova linha (0x0A)
* Caracteres ASCII com códigos acima de 127 (a menos que caracteres de vários bytes estejam ativados e *`charSet`* esteja preenchido adequadamente)
* Marcas HTML (por exemplo, <b></b> ou &amp;#153)

Muitas variáveis, mais notavelmente produtos, hierarquia e eventos, têm limitações adicionais ou requisitos de sintaxe. Para obter as limitações individuais de variáveis e os requisitos de sintaxe, consulte a seção correspondente aos parâmetros da variável *`s_account`*.
