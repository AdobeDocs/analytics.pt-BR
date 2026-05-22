---
description: Você deve atender a esses requisitos de solução, serviço e código do CX Enterprise para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar versões de código e onde obter as bibliotecas de código mais recentes.
solution: Analytics
title: Requisitos do encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c354699e-6555-4397-8706-1a9a89984069
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 52%

---

# Requisitos do encaminhamento pelo lado do servidor

Você deve atender a esses requisitos de solução, serviço e código do CX Enterprise para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar versões de código e onde obter as bibliotecas de código mais recentes.

## Requisitos da solução

O encaminhamento pelo lado do servidor funciona com o [Analytics](https://www.adobe.com/br/data-analytics-cloud/analytics.html) e o [Audience Manager](https://www.adobe.com/br/analytics/audience-manager.html) e/ou com o [Públicos-alvo](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR).

## Requisitos de serviço

O encaminhamento pelo lado do servidor requer o [Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). O Identity Service fornece uma ID universal que identifica visitantes do site em todas as soluções do CX Enterprise. Você precisa implementar o serviço de ID para que o encaminhamento pelo lado do servidor funcione.

## Versões de código

O encaminhamento pelo lado do servidor exige a versão 1.5 (ou mais recente) das bibliotecas de código listadas abaixo. Como prática recomendada, recomendamos usar as versões mais recentes em vez dos mínimos necessários.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determine sua versão da biblioteca de códigos

Qualquer ferramenta que monitora as solicitações HTTP feitas por um navegador pode mostrar o número da versão do seu código AppMeasurement e Visitor API. O `AppMeasurement_Module_AudienceManagement.js` não contém ou retorna uma ID de versão. Os exemplos a seguir mostram a aparência das IDs de versão para os códigos `AppMeasurement.js` e `VisitorAPI.js`.

* `AppMeasurement.js`: O [Adobe Debugger](/help/implement/validate/debugger.md) retorna a versão do AppMeasurement da seguinte maneira: `Version of Code | JS-1.5.1`. Outras ferramentas podem usar um rótulo diferente, mas o valor sempre segue o padrão `JS-X.X.X`, onde `X` é um número de versão.
* `VisitorAPI.js`: Procure o parâmetro `d_visid_ver`. Ele mostrará o serviço de ID de visitante como este: `d_visid_ver: 1.5.5`. O código da API de visitante anterior à versão 1.5.2 não incluía um número de versão. Você provavelmente está usando uma biblioteca de código mais antiga (e precisa atualizar) se os resultados do monitoramento não retornarem um número de versão.
