---
title: Perguntas frequentes sobre implementação
description: Perguntas frequentes sobre a implantação e links para mais informações.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 67%

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

Às vezes, uma organização gostaria de remover uma implementação devido à expiração do contrato ou reduzir o número de chamadas do servidor.

* **Implementações usando o Launch**: Desative ou desinstale a extensão do Adobe Analytics na guia [!UICONTROL Extensões] e, em seguida, publique.
* **Implementações** herdadas do AppMeasurement: Substitua todo o conteúdo do `s_code.js` arquivo pela seguinte linha de código:

```js
var s = new Object();
```

>[!WARNING]
>
>Não:
>
>* Altere o conjunto de relatórios para um valor inválido, pois isso cria carga desnecessária nos servidores do Adobe.
>* Remova o `s_code.js` arquivo completamente, a menos que você também remova todas as referências ao arquivo em cada página.
>* Altere a `trackingServer` variável para apontar para longe de Adobe. O AppMeasurement ainda envia solicitações de imagem, que retornam 404 erros.

