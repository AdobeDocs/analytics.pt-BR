---
description: 'null'
seo-description: 'null'
seo-title: PHP
solution: Analytics
subtopic: Notas de versão
title: PHP
topic: Desenvolvedor e implementação
uuid: 65 a 644 ef -8 e 50-406 b -8 b 12-0582495 d 130 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# PHP{#php}

>[!NOTE]
>
>Para encontrar a versão atual da biblioteca, ative o registro de depuração.

## Versão 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Data de lançamento: **agosto de 2014**

* Alterações internas para suportar recursos futuros.

## Versão 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Data de lançamento: **julho de 2012**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. Isso resultou em páginas não seguras tentando fazer uma solicitação de imagem segura.

## Versão 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

A Biblioteca de avaliações do PHP 1.1 inclui as seguintes atualizações da versão 1.0:

* Maior precisão de geo-segmentação (quando `sendFromServer` está ativado).
* Correção de um erro para o usuário possa anexar na variável `userAgent`.
* O beacon de imagem é compatível com um número maior de navegadores móveis.
* A variável `imageDimensions` é remetida para 5x5 quando a exibição móvel é ativada.
* Lista refinada de detecção de bots.
* Adição de informações de depuração (cabeçalhos HTTP, resposta, erros e assim por diante) quando `debugTracking` e `sendFromServer` eram ativados.

* `debugFilename` Adicionada a variável (quando `sendFromServer` está ativada).

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set.

* Suporte total para implementações CGI de PHP.
* Aprimoramentos de desempenho.

