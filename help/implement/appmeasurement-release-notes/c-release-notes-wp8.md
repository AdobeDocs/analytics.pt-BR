---
description: 'null'
solution: Analytics,Experience Cloud
subtopic: Release notes
title: Windows Phone 8
topic: Developer and implementation
uuid: 7378969a-d219-42bf-9750-141acc9e4b7d
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Windows Phone 8{#windows-phone}

> [!NOTE] Observação: para encontrar a versão atual da biblioteca, acione o log de depuração.

Os [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) da biblioteca móvel estão disponíveis na [!DNL Developer Connection].

> [!NOTE] O [!DNL Windows] Phone 8 SDK foi substituído pelo [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK. Não haverá mais nenhum desenvolvimento neste SDK.

## Versão 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

Data de lançamento: **21 de agosto de 2013**

* As chaves de contexto de dados agora permitem sublinhados.

## Versão 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

Data de lançamento: **22 de maio de 2013**

* Correções de bug e melhorias de desempenho.

## Versão 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

Data de lançamento: **18 de abril de 2013**

* Solucionado o problema que fazia com que a duração de uma sessão anterior fosse calculada incorretamente algumas vezes.

## Versão 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

Data de lançamento: **21 de março de 2013**

* Corrigido um problema de localização com os objetos `DateTime`.

## Versão 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

Data de lançamento: **26 de fevereiro de 2013**

* O`ADMS_Measurement.visitorID` agora fica pré-preenchido com o valor padrão.
* Solucionado um problema que às vezes gerava respostas automáticas do cache.

## Versão 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

Data de lançamento: **21 de fevereiro de 2013**

* Não é mais necessário desaprovar `offlineThrottleDelay` como configuração devido à otimização de discussão. A configuração ainda existe para preservar a compatibilidade anterior, mas não tem mais efeito.
* `DayOfWeek` agora tem por base 1 a partir de domingo para corresponder aos valores coletados em outras plataformas.
* Correção do problema do armazenamento offline que causava falhas ocasionais no aplicativo.

