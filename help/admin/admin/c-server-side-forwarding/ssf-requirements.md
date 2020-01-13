---
description: Você deve atender a esses requisitos de solução, serviço e código da Experience Cloud para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar as versões de código e onde obter as bibliotecas de código mais recentes.
solution: Audience Manager
title: Requisitos do encaminhamento pelo lado do servidor
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Requisitos do encaminhamento pelo lado do servidor

Você deve atender a esses requisitos de solução, serviço e código da Experience Cloud para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar as versões de código e onde obter as bibliotecas de código mais recentes.

## Requisitos da solução

O encaminhamento pelo lado do servidor funciona com o [Analytics](https://www.adobe.com/br/data-analytics-cloud/analytics.html) e o [Audience Manager](https://www.adobe.com/br/data-analytics-cloud/audience-manager.html) e/ou com o [Públicos-alvo](https://marketing.adobe.com/resources/help/pt_BR/mcloud/audience_library.html).

## Requisitos de serviço

O encaminhamento pelo lado do servidor requer o [Serviço de identidade](https://marketing.adobe.com/resources/help/pt_BR/mcvid/). O Serviço de identidade fornece uma ID universal que identifica os visitantes do site em todas as soluções da Experience Cloud. Você precisa implementar o serviço de ID para que o encaminhamento pelo lado do servidor funcione.

## Versões de código

O encaminhamento pelo lado do servidor requer a versão 1.5 (ou mais recente) das bibliotecas de código listadas abaixo. Como prática recomendada, recomendamos usar as versões mais recentes em vez das versões mínimas necessárias.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determine sua versão da biblioteca de códigos

Qualquer ferramenta que monitora as solicitações HTTP feitas por um navegador pode mostrar o número da versão do seu código AppMeasurement e Visitor API. O `AppMeasurement_Module_AudienceManagement.js` não contém ou retorna uma ID de versão. Os exemplos a seguir mostram a aparência das IDs de versão para os códigos `AppMeasurement.js` e `VisitorAPI.js`.

* `AppMeasurement.js`: O [Adobe Debugger](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/debugger.html) retorna a versão do AppMeasurement da seguinte maneira: `Version of Code | JS-1.5.1`. Outras ferramentas podem usar um rótulo diferente, mas o valor sempre segue o padrão `JS-X.X.X`, onde `X` é um número de versão.
* `VisitorAPI.js`: Procure o parâmetro `d_visid_ver`. Ele mostrará o serviço de ID de visitante como este: `d_visid_ver: 1.5.5`. O código da API de visitante anterior à versão 1.5.2 não incluía um número de versão. Você provavelmente está usando uma biblioteca de código mais antiga (e precisa atualizar) se seus resultados de monitoramento não retornarem um número de versão.
