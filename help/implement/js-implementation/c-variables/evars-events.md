---
description: 'Se quiser rastrear informações adicionais, mas não tiver variáveis suficientes para fazer isso, agora você tem acesso a eVars adicionais e eventos bem-sucedidos '
keywords: Analytics Implementation;evars;events;evars number;how many evars;how many events
title: eVars e eventos adicionais
topic: Developer and implementation
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# eVars e eventos adicionais

Se quiser rastrear informações adicionais, mas não tiver variáveis suficientes para fazer isso, agora você tem acesso a eVars adicionais e eventos bem-sucedidos:

> [!NOTE] O código H JavaScript não é compatível com essas eVars e eventos adicionais.

## Qualificações para dimensões e eventos personalizados {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Produto Adobe Analytics |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 props | 200 eVars | 1000 eventos |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 props | 200 eVars | 1000 eventos |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 props | 200 eVars | 1000 eventos |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 props | 250 eVars | 1000 eventos |

## Variáveis e eventos de preenchimento {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* As variáveis podem ser preenchidas na biblioteca de coleta de dados se você estiver utilizando essas versões do [!DNL AppMeasurement]:

   * AppMeasurement para JavaScript versão 1.4+
   * AppMeasurement para Flash versão 3.9+
   * AppMeasurement para Java versão 1.2.8+
   * AppMeasurement para Silverlight/.NET versão 1.4.2+
   * AppMeasurement para PHP versão 1.2.2+

* Se você tiver uma versão anterior do código, ou no JavaScript H.*, é possível preencher dados de contexto e utilizar regras de processamento para preencher variáveis.
* Todas as versões do código de coleta de dados podem preencher eventos de 101-1000.
* As regras de processamento podem ser utilizadas para preencher as eVars 76-250 com base nos dados de contexto ou outras variáveis.

## Perguntas frequentes {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **Todas as interfaces do Adobe Analytics têm acesso imediato a estas novas variáveis?** Essas interfaces terão acesso imediato: [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], [!UICONTROL Report Builder], [!UICONTROL Ad Hoc Analysis], APIs e [!UICONTROL Data Workbench].

* **As eVars e os eventos adicionais aparecem automaticamente nos feeds de dados?** Os feeds de dados terão acesso às novas variáveis e aos eventos depois de ativados. As novas colunas de eVar não aparecerão até você optar por incluí-las. No entanto, novos eventos aparecerão na coluna event_list assim que estiverem ativados e a tabela de pesquisa de eventos conterá os nomes de eventos para essas IDs de eventos. Não ative novos eventos a não ser que você esteja pronto para consumi-los em Feeds de dados.

* **Como faço para solicitar novas colunas do feed de dados?** Para solicitar novas colunas, consulte [Configuração dos feeds de dados](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html).

* **E se eu for um cliente Analytics Ultimate que deseja voltar para o Analytics Prime e tiver mais de 200 eVars ativadas?** A Adobe não desativará as eVars existentes, mas você não poderá ativar mais. Se você desativar as eVars, não poderá ativá-las novamente até que esteja abaixo do limite do Analytics Prime de 200 eVars ativadas.

