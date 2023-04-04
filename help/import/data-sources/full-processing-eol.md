---
title: Fim da vida útil para fontes de dados de processamento completo
description: Saiba mais sobre o anúncio de fim de vida útil de fontes de dados de processamento completo.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 16%

---

# Fim da vida útil para fontes de dados de processamento completo

As fontes de dados de processamento completo historicamente permitiram que as organizações enviassem dados a nível de ocorrência para a Adobe Analytics. Esses dados foram processados da mesma forma que os dados coletados por meios tradicionais de coleta de dados, como o AppMeasurement. Em 2020, o Adobe lançou o [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), que executa as mesmas funções que fontes de dados de processamento completo, mas com recursos adicionais. Esta página fornece detalhes sobre a funcionalidade adicional fornecida pela API de inserção de dados em massa e descreve as diferenças nos formatos de arquivo.

Em 25 de março de 2021, o Adobe impediu a criação de novas conexões de fontes de dados de processamento completo. Em 31 de janeiro de 2022, todos os serviços de processamento de dados foram desativados.

## Principais diferenças entre as fontes de dados de processamento completo e a API de inserção de dados em massa

* A inserção de dados em massa permite enviar vários arquivos para processamento paralelo. Grupos de visitantes garantem a continuidade do visitante e a atribuição do eVar.
* A inserção de dados em massa tem recursos de validação de dados e tratamento de erros, removendo parte do trabalho administrativo de envio de dados de ocorrência.
* A inserção de dados em massa suporta vários métodos de identificação de ID de visitante.
* A inserção de dados em massa tem alguns campos obrigatórios adicionais: Uma coluna de identificação de visitante, uma `pageName` (ou equivalente de link), `reportSuiteID`, `timestamp`e `userAgent`.
* Para garantir a continuidade do visitante e a atribuição, a inserção de dados em massa requer que as linhas nos arquivos sejam classificadas em ordem cronológica. Consulte [Grupos de visitantes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) para saber mais sobre a ordem da atividade do visitante em todos os arquivos.
* A inserção de dados em massa requer que os arquivos sejam compactados em .csv no formato .gzip.
* O BDIA usa `timestamp` em vez de `date`.

## Comparação de variáveis entre BDIA e fontes de dados de processamento completo

As variáveis a seguir foram introduzidas na inserção de dados em massa, antes indisponíveis em fontes de dados de processamento completo:

* **`aamlh`**: Dica de localização do Adobe Audience Manager.
* **`contextData.key`**: [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: Variáveis do serviço de Experience Cloud ID. Inclui o `id`, `authState` e `isMCSeed`.
* **`hints`**: [Dica do cliente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=pt-BR) variáveis. Inclui `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`e `wow64`.
* **`ipaddress`**: O endereço IP do visitante.
* **`language`**: O [Idioma](/help/components/dimensions/language.md) dimensão.
* **`list1`** - **`list3`**: [Variáveis da Lista](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: A Experience Cloud ID do visitante.
* **`tnta`**: Carga de dados do Target usada em [Analytics para Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR) integrações.
* **`trackingServer`**: A variável.[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)
* **`transactionID`**: A variável.[`transactionID`](/help/implement/vars/page-vars/transactionid.md)
* **`userAgent`**: A sequência de agente do usuário do dispositivo.

As seguintes variáveis não são compatíveis com a inserção de dados em massa:

* **`charSet`**: A variável. [`charSet`](/help/implement/vars/config-vars/charset.md) A inserção de dados em massa suporta apenas UTF-8.
* **`timezone`**: O deslocamento do fuso horário do visitante em relação ao GMT em horas.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: Variáveis usadas na coleta de dados do Activity Map.
