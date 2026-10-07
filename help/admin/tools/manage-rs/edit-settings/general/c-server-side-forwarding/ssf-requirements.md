---
description: Você deve atender a esses requisitos de solução, serviço e código da CX Enterprise para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar versões de código e onde obter as bibliotecas de código mais recentes.
solution: Analytics
title: Requisitos do encaminhamento pelo lado do servidor
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 43%
---
# Requisitos do encaminhamento pelo lado do servidor

Você deve atender a esses requisitos de solução, serviço e código da CX Enterprise para implementar o encaminhamento pelo lado do servidor. Esses requisitos também incluem instruções sobre como verificar versões de código e onde obter as bibliotecas de código mais recentes.

## Requisitos da solução

O encaminhamento pelo lado do servidor funciona com o [Analytics](https://www.adobe.com/br/data-analytics-cloud/analytics.html) e o [Audience Manager](https://www.adobe.com/br/analytics/audience-manager.html) e/ou com o [Públicos-alvo](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=pt-BR).

## Requisitos de serviço

O encaminhamento pelo lado do servidor requer o [Serviço de identidade](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home). O Serviço de identidade fornece uma ID universal que identifica visitantes do site em todas as soluções da CX Enterprise. Você precisa implementar o serviço de ID para que o encaminhamento pelo lado do servidor funcione.

## Versões de código

O encaminhamento pelo lado do servidor exige a versão 1.5 (ou mais recente) das bibliotecas de código listadas abaixo. Como prática recomendada, recomendamos usar as versões mais recentes em vez dos mínimos necessários.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determine sua versão da biblioteca de códigos

Qualquer ferramenta que monitora as solicitações HTTP feitas por um navegador pode mostrar o número da versão do seu código AppMeasurement e Visitor API. O `AppMeasurement_Module_AudienceManagement.js` não contém ou retorna uma ID de versão. Os exemplos a seguir mostram a aparência das IDs de versão para os códigos `AppMeasurement.js` e `VisitorAPI.js`.

* `AppMeasurement.js`: A versão aparece na URL da solicitação após o tipo de resposta, como `/b/ss/examplersid/1/JS-X.X.X/s234234238479`. [Ferramentas de depuração](/help/implement/validate/debugging-tools.md) que decodificam solicitações podem usar um rótulo diferente, mas o valor sempre segue o padrão `JS-X.X.X`, onde `X` é um número de versão.
* `VisitorAPI.js`: Procure o parâmetro `d_visid_ver`. Ele mostrará o serviço de ID de visitante como este: `d_visid_ver: 1.5.5`. O código da API de visitante anterior à versão 1.5.2 não incluía um número de versão. Você provavelmente está usando uma biblioteca de código mais antiga (e precisa atualizar) se os resultados do monitoramento não retornarem um número de versão.
