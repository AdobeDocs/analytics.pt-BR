---
title: Perguntas frequentes sobre implementação
description: Perguntas frequentes sobre a implantação e links para mais informações.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 71%

---


# Perguntas frequentes sobre a implementação do Analytics

Perguntas frequentes sobre a implantação e links para mais informações.

## Qual é a diferença entre a ID de visitante da Experience Cloud e a ID de visitante do Analytics?

O Serviço de identidade atribui um identificador exclusivo e persistente que pode ser compartilhado entre outras soluções na Experience Cloud. A ID de visitante do Analytics é usada somente pelo Analytics. A Adobe recomenda usar o Serviço de ID de visitante da Experience Cloud na implementação.

## Como implementar o rastreamento de vídeo Heartbeat?

Consulte [Avaliação de áudio e vídeo no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/media-analytics/using/media-overview.html).

## Uma interrupção de serviço na Adobe pode afetar o desempenho?

Não. O arquivo JavaScript não fica hospedado nos servidores da Adobe, de forma que uma interrupção da Adobe não afete a biblioteca do AppMeasurement. Se você usar o Adobe Experience Platform Launch, o arquivo JavaScript será hospedado pelo Akamai ou em um local de servidor determinado pela organização.

## O envio de dados de um navegador para os serviços da Adobe pode reduzir o desempenho?

O AppMeasurement cria um objeto de imagem na página HTML e, em seguida, o navegador solicita o envio do objeto de imagem aos servidores de coleta de dados da Adobe. Caso os servidores de coleta de dados fiquem lentos e com pouca capacidade de resposta, o thread responsável pela solicitação será adiado até que a imagem volte ou o tempo limite seja atingido. Como os navegadores processam imagens com vários threads, uma interrupção da Adobe teria um impacto mínimo no tempo de carregamento da página, imobilizando um thread enquanto os outros continuariam a funcionar.

## Como invalidar ou remover uma implementação do Analytics?

Às vezes, uma organização quer remover uma implementação devido à expiração do contrato ou reduzir o número de chamadas do servidor.

* **Implementações usando o Launch**: desative ou desinstale a extensão do Adobe Analytics na guia [!UICONTROL Extensões] e, em seguida, publique.
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


## Executei o AppMeasurement por meio de um analisador de código, e ele sinalizou seu uso como `Math.random()` um risco potencial de segurança. É `Math.random()` usado com dados confidenciais?

Não. Os números que usam não `Math.random()` são usados para mascarar, enviar ou receber dados confidenciais. Os dados enviados para os servidores de coleta de dados do Adobe dependem da segurança da conexão HTTPS subjacente. <!-- AN-173590 -->

O AppMeasurement usa `Math.random()` três áreas principais:

* **Amostragem**: Dependendo da implementação, algumas informações podem ser coletadas para apenas uma pequena porcentagem de visitantes do site. `Math.random()` é usada para determinar se um determinado visitante deve enviar dados. A maioria das implementações não usa amostragem.
* **ID** do visitante de fallback: Se a ID do visitante não puder ser recuperada de cookies, uma ID de visitante aleatória será gerada. Esta parte do AppMeasurement usa duas chamadas para `Math.random()`.
* **Quebra** de cache: Um número aleatório é adicionado ao final dos URLs de solicitação de imagem para ajudar a impedir o cache do navegador.
