---
description: 'null'
subtopic: Release notes
title: PHP
topic: Developer and implementation
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# PHP{#php}

> [!NOTE] Observação: para encontrar a versão atual da biblioteca, acione o log de depuração.

## Versão 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Data de lançamento: **agosto de 2014**

* Alterações internas para suportar recursos futuros.

## Versão 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Data de lançamento: **julho de 2012**

* Adição de uma verificação para o "off" retornado para o $_SERVER['HTTPS'] no IIS. Sem essa verificação, a conversão para booleano ((bool)$_SERVER['HTTPS']) retornou true no IE, independentemente se a solicitação foi feita por HTTP ou HTTPS. Isso resultou em páginas não seguras tentando fazer uma solicitação de imagem segura.

## Versão 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

A Biblioteca de avaliações do PHP 1.1 inclui as seguintes atualizações da versão 1.0:

* Maior precisão de geo-segmentação (quando `sendFromServer` está ativado).
* Correção de um erro para o usuário possa anexar na variável `userAgent`.
* O beacon de imagem é compatível com um número maior de navegadores móveis.
* A variável `imageDimensions` é remetida para 5x5 quando a exibição móvel é ativada.
* Lista refinada de detecção de bots.
* Adição de informações de depuração (cabeçalhos HTTP, resposta, erros e assim por diante) quando `debugTracking` e `sendFromServer` eram ativados.

* Adição da variável `debugFilename` (quando `sendFromServer` é ativado).

* A variável de pageName é padronizada como `$_SERVER['SCRIPT_NAME']` quando `pagename` e `pageURL` não estão definidos.

* Suporte total para implementações CGI de PHP.
* Aprimoramentos de desempenho.

