---
description: Você deve atender a esses requisitos de solução, serviço e código da Experience Cloud para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar as versões de código e onde obter as bibliotecas de código mais recentes.
solution: Analytics
title: Requisitos do encaminhamento pelo lado do servidor
feature: Server-Side Forwarding
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: ht
source-wordcount: '315'
ht-degree: 100%

---

# Requisitos do encaminhamento pelo lado do servidor

Você deve atender a esses requisitos de solução, serviço e código da Experience Cloud para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar as versões de código e onde obter as bibliotecas de código mais recentes.

## Requisitos da solução

O encaminhamento pelo lado do servidor funciona com o [Analytics](https://www.adobe.com/br/data-analytics-cloud/analytics.html) e o [Audience Manager](https://www.adobe.com/br/analytics/audience-manager.html) e/ou com o [Públicos-alvo](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR).

## Requisitos de serviço

O encaminhamento pelo lado do servidor requer o [Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). O Serviço de identidade fornece uma ID universal que identifica os visitantes do site em todas as soluções da Experience Cloud. Você precisa implementar o serviço de ID para que o encaminhamento pelo lado do servidor funcione.

## Versões de código

O encaminhamento pelo lado do servidor requer a versão 1.5 (ou mais recente) das bibliotecas de código listadas abaixo. Como prática recomendada, recomendamos usar as versões mais recentes em vez das versões mínimas necessárias.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determine sua versão da biblioteca de códigos

Qualquer ferramenta que monitora as solicitações HTTP feitas por um navegador pode mostrar o número da versão do seu código AppMeasurement e Visitor API. O `AppMeasurement_Module_AudienceManagement.js` não contém ou retorna uma ID de versão. Os exemplos a seguir mostram a aparência das IDs de versão para os códigos `AppMeasurement.js` e `VisitorAPI.js`.

* `AppMeasurement.js`: O [Adobe Debugger](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html?lang=pt-BR) retorna a versão do AppMeasurement da seguinte maneira: `Version of Code | JS-1.5.1`. Outras ferramentas podem usar um rótulo diferente, mas o valor sempre segue o padrão `JS-X.X.X`, onde `X` é um número de versão.
* `VisitorAPI.js`: Procure o parâmetro `d_visid_ver`. Ele mostrará o serviço de ID de visitante como este: `d_visid_ver: 1.5.5`. O código da API de visitante anterior à versão 1.5.2 não incluía um número de versão. Você provavelmente está usando uma biblioteca de código mais antiga (e precisa atualizar) se seus resultados de monitoramento não retornarem um número de versão.
