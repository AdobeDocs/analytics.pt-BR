---
title: Fim da vida útil do processamento completo de fontes de dados
description: Saiba mais sobre o anúncio do fim da vida útil para fontes de dados de processamento completo.
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 16%

---

# Fim da vida útil do processamento completo de fontes de dados

Historicamente, as fontes de dados de processamento completo permitiram que as organizações enviassem dados de nível de ocorrência para a Adobe Analytics. Esses dados foram processados da mesma forma que os dados coletados por meios tradicionais de coleta de dados, como o AppMeasurement. Em 2020, o Adobe lançou o [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), que executa as mesmas funções das fontes de dados de processamento completo, mas com recursos adicionais. Esta página fornece detalhes sobre a funcionalidade adicional fornecida pela API de inserção de dados em massa e descreve as diferenças nos formatos de arquivo.

Em 25 de março de 2021, o Adobe impediu a criação de novas conexões de fontes de dados de processamento completo. Em 31 de janeiro de 2022, todos os serviços de dados de processamento completo foram desativados.

## Principais diferenças entre as fontes de dados de processamento completo e a API de inserção de dados em massa

* A inserção de dados em massa permite enviar vários arquivos para processamento paralelo. Os Grupos de visitantes garantem a continuidade do visitante e a atribuição de eVar.
* A inserção de dados em massa tem recursos de validação de dados e tratamento de erros, removendo parte do trabalho administrativo de envio de dados de ocorrência.
* A inserção de dados em massa é compatível com vários métodos de identificação de ID de visitante.
* A inserção de dados em massa tem alguns campos obrigatórios adicionais: uma coluna de identificação do visitante, uma `pageName` (ou equivalente a link), `reportSuiteID`, `timestamp`, e `userAgent`.
* Para garantir a continuidade do visitante e a atribuição, a inserção de dados em massa requer que as linhas nos arquivos sejam classificadas em ordem cronológica. Consulte [Grupos de visitantes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) para saber mais sobre a ordem da atividade do visitante em todos os arquivos.
* A inserção de dados em massa requer que os arquivos sejam compactados em .csv no formato .gzip.
* BDIA usa `timestamp` em vez de `date`.

## Comparação variável entre BDIA e fontes de dados de processamento completo

As seguintes variáveis foram introduzidas na inserção de dados em massa, que antes não estava disponível nas fontes de dados de processamento completo:

* **`aamlh`**: Dica de localização do Adobe Audience Manager.
* **`contextData.key`**: [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: variáveis do serviço de ID do Experience Cloud. Inclui o `id`, `authState` e `isMCSeed`.
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=pt-BR) variáveis. Inclui `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`, e `wow64`.
* **`ipaddress`**: O endereço IP do visitante.
* **`language`**: A variável [Idioma](/help/components/dimensions/language.md) dimensão.
* **`list1`** - **`list3`**: [Variáveis da Lista](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: A Experience Cloud ID do visitante.
* **`tnta`**: Carga de dados de público alvo usada no [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR) integrações.
* **`trackingServer`**: A variável.[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)
* **`transactionID`**: A variável.[`transactionID`](/help/implement/vars/page-vars/transactionid.md)
* **`userAgent`**: a sequência de agente do usuário do dispositivo.

As seguintes variáveis não são compatíveis por meio da inserção de dados em massa:

* **`charSet`**: A variável. [`charSet`](/help/implement/vars/config-vars/charset.md) A inserção de dados em massa é compatível apenas com UTF-8.
* **`timezone`**: O deslocamento do fuso horário do visitante em relação ao GMT em horas.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: variáveis usadas na coleta de dados do Activity Map.
