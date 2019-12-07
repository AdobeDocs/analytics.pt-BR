---
description: Os caracteres e strings que nunca são permitidos em variáveis JavaScript.
keywords: Analytics Implementation
subtopic: Variables
title: Caracteres JavaScript inválidos
topic: Developer and implementation
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Caracteres JavaScript inválidos

Os caracteres e strings que nunca são permitidos em variáveis JavaScript.

* Tabulação (0x09)
* Retorno de carro (0x0D)
* Nova linha (0x0A)
* Caracteres ASCII com códigos acima de 127 (a menos que caracteres de vários bytes estejam ativados e *`charSet`* esteja preenchido adequadamente)
* Marcas HTML (por exemplo, <b></b> ou &amp;#153)

Muitas variáveis, mais notavelmente produtos, hierarquia e eventos, têm limitações adicionais ou requisitos de sintaxe. Para obter as limitações individuais de variáveis e os requisitos de sintaxe, consulte a seção correspondente aos parâmetros da variável *`s_account`*.
