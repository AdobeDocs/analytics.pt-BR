---
description: O tamanho das variáveis do Analytics pode afetar o tamanho do snippet do código HTML, arquivo da biblioteca de dados e solicitação de imagem.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Tamanho da variável
topic: Developer and implementation
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tamanho da variável

O tamanho das variáveis do Analytics pode afetar o tamanho do snippet do código HTML, arquivo da biblioteca de dados e solicitação de imagem.

Se um cliente tem muitas variáveis longas (60 caracteres ou mais), os valores poderão ser substituídos por identificadores mais curtos. As classificações de dados ou regras do VISTA podem ser usadas para traduzir identificadores para nomes amigáveis.

> [!NOTE] A maioria das variáveis do Analytics tem no máximo 100 caracteres (eVars têm no máximo 255). O Internet Explorer permite um máximo geral de 2.048 caracteres em uma URL de solicitação de imagem GET. O limite de solicitação de imagem se aplica não somente às variáveis, mas também a informações sobre os plug-ins de navegador, sistema operacional e navegador (somente Netscape/Mozilla).

