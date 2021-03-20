---
title: Término da vida útil das fontes de dados de processamento completo
description: Motivos para o fim da vida útil e comparações entre a API de inserção de dados em massa e as fontes de dados de processamento completo.
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 13%

---


# Término da vida útil das fontes de dados de processamento completo

Por vários anos, as Fontes de dados de processamento completo permitiram enviar dados a nível de ocorrência para a Adobe Analytics. Esses dados foram processados da mesma forma que os dados coletados por meio das bibliotecas JavaScript e do SDK do aplicativo móvel. Em 2020, o Adobe lançou a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), que executa as mesmas funções que as Fontes de dados de processamento completo, mas com recursos adicionais. Este tópico fornece detalhes sobre a funcionalidade adicional fornecida pela API de inserção de dados em massa e descreve as diferenças nos formatos de arquivo.

A partir de 25 de março de 2021, o Adobe impedirá a criação de novas conexões das Fontes de dados de processamento completo. As conexões existentes continuarão a ser compatíveis até que o serviço seja totalmente descontinuado. A descontinuação ocorrerá em 2021, embora uma data específica ainda não tenha sido determinada.

## Por que vamos acabar com esse recurso?

A API de inserção de dados em massa (BDIA) fornece funcionalidade adicional enquanto cobre todos os casos de uso compatíveis com o processamento completo. Acreditamos que você será mais bem servido usando a API de inserção de dados em massa.

## Principais diferenças entre as fontes de dados de processamento completo e a API de inserção de dados em massa

* A inserção de dados em massa permite o envio de vários arquivos que podem ser processados em paralelo. É possível usar Grupos de visitantes para garantir a continuidade do visitante e a atribuição do eVar.
* A inserção de dados em massa tem validação de dados, bem como recursos de tratamento de erros, removendo assim parte do trabalho administrativo de envio de dados de ocorrência.
* A inserção de dados em massa é compatível com várias opções para IDs de visitante. Você pode enviar a ID do Analytics e a ID do Marketing Cloud (consulte [Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/home.html) para saber mais). Além disso, você pode usar sua própria ID como uma [seed para gerar um ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* A inserção de dados em massa é compatível com as Variáveis de lista e de dados de contexto.
* A inserção de dados em massa não é compatível com dados de Activity Map.

## Principais diferenças no formato e conteúdo do arquivo

* A inserção de dados em massa tem alguns campos obrigatórios adicionais. Consulte a [documentação](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para obter detalhes.
* Para garantir a continuidade do visitante e a atribuição, a inserção de dados em massa requer que as linhas nos arquivos sejam classificadas em ordem cronológica. Consulte [Grupos de visitantes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) para saber mais sobre a ordem da atividade do Visitante em todos os arquivos.
* A inserção de dados em massa requer que os arquivos sejam compactados em .csv no formato .gzip.
* O BDIA usa &quot;carimbo de data e hora&quot; em vez de &quot;data&quot;.

Para obter mais detalhes, consulte a seguinte comparação dos valores de campo disponíveis em Inserção de dados em massa (BDIA) e Fontes de dados de processamento completo (FPDS).

## Comparação de valores de campo disponíveis em BDIA e FPDS

| BDIA, FPDS, Ambos | Variável BDIA | Variável de coluna do processamento completo | Descrição |
| --- | --- | --- | --- |
| BDIA | aamlh | Não suportado | Dica de localização do Adobe Audience Manager. Consulte valores de ID válidos na tabela de listagem de região AAM abaixo. |
| Ambos | browserHeight | browserHeight | Altura do navegador em pixels (por exemplo, 768) |
| Ambos | browserWidth | browserWidth | Largura do navegador em pixels (por exemplo, 1024) |
| Ambos | campaign | campanha | Código de rastreamento de campanha de conversão |
| Ambos | canal | canal | Sequência de caracteres de canal (por exemplo, seção de esportes) |
| Ambos | colorDepth | colorDepth | Profundidade de cores do monitor em bits (por exemplo, 24) |
| Ambos | connectionType | connectionType | Tipo de conexão do visitante (LAN ou modem) |
| BDIA | contextData.key | Não suportado | Os pares de valores-chave são especificados em, nomeando o cabeçalho &quot;contextData.product&quot; ou &quot;contextData.color&quot; |
| Ambos | cookiesEnabled | cookiesEnabled | `Y` ou  `N` se o visitante suporta cookies de sessão primária |
| Ambos | currencyCode | currencyCode | Código da moeda da receita (por exemplo, `USD`) |
| BDIA | customerID.[customerIDType].authState | Não suportado | O estado autenticado do visitante. Os valores suportados são: 0, 1, 2, UNKNOWN, AUTENTICATED, LOGGED_OUT ou &#39;&#39; (não diferencia maiúsculas de minúsculas). Duas aspas simples consecutivas (&#39;&#39;) fazem com que o valor seja omitido da string de consulta, o que significa 0 quando a ocorrência for feita. Observe que os valores numéricos authState suportados indicam o seguinte: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada diferencia maiúsculas de minúsculas. |
| BDIA | customerID.[customerIDType].id | Não suportado | A ID do cliente a ser usada. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada diferencia maiúsculas de minúsculas. |
| BDIA | customerID.[customerIDType].isMCSeed | Não suportado | Se essa é a propagação da ID de visitante do Marketing Cloud. Os valores suportados são: 0, 1, TRUE, FALSE, &#39;&#39; (não diferencia maiúsculas de minúsculas). Usar 0, FALSE ou duas aspas simples consecutivas (&#39;&#39;) faz com que o valor seja omitido da string de consulta. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada diferencia maiúsculas de minúsculas. |
