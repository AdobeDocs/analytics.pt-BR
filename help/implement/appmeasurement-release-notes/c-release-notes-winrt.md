---
description: 'null'
solution: Analytics,Experience Cloud
subtopic: Release notes
title: WinRT para Windows 8
topic: Developer and implementation
uuid: cec19d63-114c-4ef6-a55e-db6aad4e948b
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# WinRT para Windows 8{#winrt-for-windows}

>[!NOTE]
>
>Observação: para encontrar a versão atual da biblioteca, acione o log de depuração.

Os [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) da biblioteca móvel estão disponíveis na [!DNL Developer Connection].

>[!NOTE]
>
>O [!DNL WinRT] para [!DNL Windows] 8 SDK foi substituído pelo [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK. Não haverá mais nenhum desenvolvimento neste SDK.

## Versão 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Data de lançamento: **17 de junho de 2014**

A nova versão com novos recursos inclui localização geográfica, valor do tempo de vida, ações programadas e suporte para participação.

## Versão 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Data de lançamento: **22 de maio de 2014**

Correções de bug e melhorias de desempenho.

## Versão 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Data de lançamento: **17 de outubro de 2013**

* [!DNL Windows]Compatibilidade com 8.1

## Versão 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Data de lançamento: **18 de abril de 2013**

* Solucionado o problema que fazia com que a duração de uma sessão anterior fosse calculada incorretamente algumas vezes.

## Versão 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Data de lançamento: **21 de março de 2013**

* O`ADMS_Measurement.visitorID` agora fica pré-preenchido com o valor padrão.
* Solucionado o problema com a recuperação de informações do dispositivo.

## Versão 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Data de lançamento: **21 de fevereiro de 2013**

* Não é mais necessário desaprovar `offlineThrottleDelay` como configuração devido à otimização de discussão. A configuração ainda existe para preservar a compatibilidade anterior, mas não tem mais efeito.
* `DayOfWeek` agora tem por base 1 a partir de domingo para corresponder aos valores coletados em outras plataformas.
* Assinatura automática adicionada a escuta de evento no TrackingHelper.js para simplificar o rastreamento de ciclo de vida.

## Versão 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Data de lançamento: **novembro de 2012**

* A resolução da tela agora está sendo coletada de maneira precisa para as plataformas C#, C++ e HTML5/WinJS.
* A classe`ADMS_Churn` agora é interna. Para usar as práticas recomendadas para o monitoramento do ciclo de vida do aplicativo, use as chamadas a seguir:

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Adicionada a variável `public double maxSessionLength` ao `ADMS_Measurement` para permitir que você defina uma duração máxima da sessão para a sessão do usuário anterior. Se a duração da sessão registrada exceder o valor máximo, a duração máxima da sua sessão será enviada. O padrão para `maxSessionLength` é 3600 (segundos).
* Adição de uma variável de configuração `lifecycleSessionTimeout` a qual permite que você especifique a duração, em segundos, entre a inicialização do aplicativo antes que possa ser considerada uma nova sessão.
* Nova métrica de tamanho de sessão anterior adicionada às medições de ciclo de vida.
* O TrackingHelper foi atualizado para fins de clareza.
* Bug do módulo de mídia corrigido.

## Versão 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**Outubro de 2012**

Versão inicial.
