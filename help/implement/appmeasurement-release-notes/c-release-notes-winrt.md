---
description: 'null'
seo-description: 'null'
seo-title: WinRT para Windows 8
solution: Analytics, Marketing Cloud
subtopic: Notas de versão
title: WinRT para Windows 8
topic: Desenvolvedor e implementação
uuid: cec 19 d 63-114 c -4 ef 6-a 55 e-db 6 aad 4 e 948 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# WinRT para Windows 8{#winrt-for-windows}

>[!NOTE]
>
>Para encontrar a versão atual da biblioteca, ative o registro de depuração.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL WinRT] for [!DNL Windows] 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E) SDK. Não haverá mais nenhum desenvolvimento neste SDK.

## Versão 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Data de lançamento: **17 de junho de 2014**

A nova versão com novos recursos inclui localização geográfica, valor do tempo de vida, ações programadas e suporte para participação.

## Versão 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Data de lançamento: **22 de maio de 2014**

Correções de bug e melhorias de desempenho.

## Versão 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Data de lançamento: **17 de outubro de 2013**

* [!DNL Windows] Compatibilidade com 8.1

## Versão 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Data de lançamento: **18 de abril de 2013**

* Solucionado o problema que fazia com que a duração de uma sessão anterior fosse calculada incorretamente algumas vezes.

## Versão 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Data de lançamento: **21 de março de 2013**

* `ADMS_Measurement.visitorID` agora são preenchidas automaticamente com o valor padrão.
* Solucionado o problema com a recuperação de informações do dispositivo.

## Versão 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Data de lançamento: **21 de fevereiro de 2013**

* Não é mais necessário desaprovar `offlineThrottleDelay` como configuração devido à otimização de discussão. A configuração ainda existe para preservar a compatibilidade anterior, mas não tem mais efeito.
* `DayOfWeek` agora tem por base 1 a partir de domingo para corresponder aos valores coletados em outras plataformas.
* Assinatura automática adicionada a escuta de evento no TrackingHelper.js para simplificar o rastreamento de ciclo de vida.

## Versão 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Data de lançamento: **novembro de 2012**

* A resolução da tela agora está sendo coletada de maneira precisa para as plataformas C#, C++ e HTML5/WinJS.
* `ADMS_Churn` agora é interna. Para usar as práticas recomendadas para o monitoramento do ciclo de vida do aplicativo, use as chamadas a seguir:

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Added `public double maxSessionLength` variable to `ADMS_Measurement` to allow you to set a maximum session length for the previous user session. Se a duração da sessão registrada exceder o valor máximo, a duração máxima da sua sessão será enviada. Default `maxSessionLength` is 3600 (seconds).
* Adição de uma variável de configuração `lifecycleSessionTimeout` a qual permite que você especifique a duração, em segundos, entre a inicialização do aplicativo antes que possa ser considerada uma nova sessão.
* Nova métrica de tamanho de sessão anterior adicionada às medições de ciclo de vida.
* O TrackingHelper foi atualizado para fins de clareza.
* Bug do módulo de mídia corrigido.

## Versão 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**Outubro de 2012**

Versão inicial.
