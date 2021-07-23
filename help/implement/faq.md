---
title: Perguntas frequentes sobre implementação
description: Perguntas frequentes sobre a implantação e links para mais informações.
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 91%

---

# Perguntas frequentes sobre a implementação do Analytics

Perguntas frequentes sobre a implantação e links para mais informações.

## Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics?

O Serviço de identidade atribui um identificador exclusivo e persistente que pode ser compartilhado entre outras soluções na Experience Cloud. A ID de visitante do Analytics é usada somente pelo Analytics. A Adobe recomenda usar o Serviço de ID de visitante da Experience Cloud na implementação.

## Como implementar o rastreamento de vídeo Heartbeat?

Consulte [Avaliação de áudio e vídeo no Adobe Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=pt-BR).

## Uma interrupção de serviço na Adobe pode afetar o desempenho?

Não. O arquivo JavaScript não fica hospedado nos servidores da Adobe, de forma que uma interrupção da Adobe não afete a biblioteca do AppMeasurement. Se você usar tags no Adobe Experience Platform, o arquivo JavaScript será hospedado pela Akamai ou em um local de servidor determinado pela organização.

## O envio de dados de um navegador para os serviços da Adobe pode reduzir o desempenho?

O AppMeasurement cria um objeto de imagem na página HTML e, em seguida, o navegador solicita o envio do objeto de imagem aos servidores de coleta de dados da Adobe. Caso os servidores de coleta de dados fiquem lentos e com pouca capacidade de resposta, o thread responsável pela solicitação será adiado até que a imagem volte ou o tempo limite seja atingido. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar.

## Como invalidar ou remover uma implementação do Analytics?

Às vezes, uma organização quer remover uma implementação devido à expiração do contrato ou reduzir o número de chamadas do servidor.

* **Implementações que usam tags no Adobe Experience Platform**: Desative ou desinstale a extensão Adobe Analytics na guia   Extensões e, em seguida, publique.
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
