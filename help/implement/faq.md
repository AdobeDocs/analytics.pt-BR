---
title: Perguntas frequentes sobre implementação
description: Perguntas frequentes sobre a implantação e links para mais informações.
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/Hm9pIJE9P3jEljJAgB69k2M9-fTa9G0wsCjfvN4xH3E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c77ba355-6681-41fe-b719-563d3f507fdbid: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 1be0f3577403db7cf9bd40ef9e7c4bfcfa6c0b17
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 100%

---

# Perguntas frequentes sobre a implementação do Analytics

Perguntas frequentes sobre a implantação e links para mais informações.

## Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics?

O Serviço de identidade atribui um identificador exclusivo e persistente que pode ser compartilhado entre outras soluções na Experience Cloud. A ID de visitante do Analytics é usada somente pelo Analytics. A Adobe recomenda usar o Serviço de ID de visitante da Experience Cloud na implementação.

## Como implementar o rastreamento de vídeo Heartbeat?

Consulte [Avaliação de áudio e vídeo no Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-overview).

## Uma interrupção de serviço na Adobe pode afetar o desempenho?

Não. O arquivo JavaScript não fica hospedado nos servidores da Adobe, de forma que uma interrupção da Adobe não afete a biblioteca do AppMeasurement. Se você usar tags na Adobe Experience Platform, o arquivo JavaScript será hospedado pelo Akamai ou em um local de servidor determinado pela organização.

## O envio de dados de um navegador para os serviços da Adobe pode reduzir o desempenho?

O AppMeasurement cria um objeto de imagem na página HTML e, em seguida, o navegador solicita o envio do objeto de imagem aos servidores de coleta de dados da Adobe. Caso os servidores de coleta de dados fiquem lentos e com pouca capacidade de resposta, o thread responsável pela solicitação será adiado até que a imagem volte ou o tempo-limite seja atingido. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar.

## Como invalidar ou remover uma implementação do Analytics?

Às vezes, uma organização quer remover uma implementação devido à expiração do contrato ou reduzir o número de chamadas do servidor.

* **Implementações usando a Coleção de dados da Adobe Experience Platform**: desative ou desinstale a extensão do Adobe Analytics, o SDK da Web ou o SDK móvel aplicável na guia [!UICONTROL Extensões] e, em seguida, publique.
* **Implementações herdadas do AppMeasurement**: substitua todo o conteúdo do arquivo `s_code.js` pela seguinte linha de código:

```js
var s = new Object();
```

>[!WARNING]
>
>Não:
>
>* Altere o conjunto de relatórios para um valor inválido, pois uma carga desnecessária será criada nos servidores da Adobe.
>* Remova o arquivo `s_code.js` completamente, a menos que você também remova todas as referências ao arquivo em cada página.
>* Altere a variável `trackingServer` para apontar para longe da Adobe. O AppMeasurement ainda envia solicitações de imagem, que retornam erros 404.

## Executei o AppMeasurement por meio de um analisador de código, e ele sinalizou seu uso de `Math.random()` como um possível risco de segurança. O `Math.random()` é usado com algum dado confidencial?

Não. Os números que usam `Math.random()` não são usados para mascarar, enviar ou receber dados confidenciais. Os dados enviados para os servidores de coleção de dados da Adobe dependem da segurança da conexão HTTPS subjacente. <!-- AN-173590 -->

O AppMeasurement usa `Math.random()` em três áreas principais:

* **Amostragem**: dependendo da sua implementação, algumas informações podem ser coletadas apenas para uma pequena porcentagem de visitantes do site. `Math.random()` é usado para determinar se determinado visitante deve enviar dados. A maioria das implementações não usa a amostragem.
* **ID de visitante de fallback**: se a ID de visitante não puder ser recuperada dos cookies, uma ID de visitante aleatória será gerada. Essa parte do AppMeasurement usa duas chamadas para `Math.random()`.
* **Interrupção de cache**: um número aleatório é adicionado ao final dos URLs de solicitação de imagem para ajudar a impedir o armazenamento em cache do navegador.
