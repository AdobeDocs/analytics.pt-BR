---
title: Fim da vida útil do processamento completo de fontes de dados
description: Saiba mais sobre o anúncio do fim da vida útil para fontes de dados de processamento completo.
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/3NSbjRWl0GsomjsEXo8XczQ1RWOPGpqW4OM2YeUo3Wk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 8%

---

# Fim da vida útil do processamento completo de fontes de dados

Historicamente, as fontes de dados de processamento completo permitiram que as organizações enviassem dados de nível de ocorrência para a Adobe Analytics. Esses dados eram processados da mesma forma que os dados coletados por meios tradicionais de coleta de dados, como o AppMeasurement. Em 2020, o Adobe lançou a [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), que executa as mesmas funções das fontes de dados de processamento completo, mas com recursos adicionais. Esta página fornece detalhes sobre a funcionalidade adicional fornecida pela API de inserção de dados em massa e descreve as diferenças nos formatos de arquivo.

Em 25 de março de 2021, o Adobe impediu a criação de novas conexões de fontes de dados de processamento completo. Em 31 de janeiro de 2022, todos os serviços de dados de processamento completo foram desativados.

## Principais diferenças entre as fontes de dados de processamento completo e a API de inserção de dados em massa

* A inserção de dados em massa permite enviar vários arquivos para processamento paralelo. Os Grupos de visitantes garantem a continuidade do visitante e a atribuição do eVar.
* A inserção de dados em massa tem recursos de validação de dados e tratamento de erros, removendo parte do trabalho administrativo de envio de dados de ocorrência.
* A inserção de dados em massa é compatível com vários métodos de identificação de ID de visitante.
* A inserção de dados em massa tem alguns campos obrigatórios adicionais: Uma coluna de identificação de visitante, um `pageName` (ou equivalente a link), `reportSuiteID`, `timestamp` e `userAgent`.
* Para garantir a continuidade do visitante e a atribuição, a inserção de dados em massa requer que as linhas nos arquivos sejam classificadas em ordem cronológica. Consulte [Grupos de visitantes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) para saber mais sobre a ordem da atividade do visitante em todos os arquivos.
* A inserção de dados em massa requer que os arquivos sejam compactados em .csv no formato .gzip.
* O BDIA usa `timestamp` em vez de `date`.

## Comparação variável entre BDIA e fontes de dados de processamento completo

As seguintes variáveis foram introduzidas na inserção de dados em massa, que antes não estava disponível nas fontes de dados de processamento completo:

* **`aamlh`**: dica de localização do Adobe Audience Manager.
* **`contextData.key`**: [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: variáveis do serviço da Experience Cloud ID. Inclui o `id`, `authState` e `isMCSeed`.
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variáveis. Inclui `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion` e `wow64`.
* **`ipaddress`**: o endereço IP do visitante.
* **`language`**: A dimensão [Idioma](/help/components/dimensions/language.md).
* **`list1`** - **`list3`**: [Listar variáveis](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: a Experience Cloud ID do visitante.
* **`tnta`**: carga de dados de destino usada em integrações do [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR).
* **`trackingServer`**: A variável [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md).
* **`transactionID`**: A variável [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **`userAgent`**: a cadeia de caracteres do agente do usuário do dispositivo.

As seguintes variáveis não são compatíveis por meio da inserção de dados em massa:

* **`charSet`**: A variável [`charSet`](/help/implement/vars/config-vars/charset.md). A inserção de dados em massa é compatível apenas com UTF-8.
* **`timezone`**: O deslocamento do fuso horário do visitante de GMT em horas.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: Variáveis usadas na coleta de dados do Activity Map.
