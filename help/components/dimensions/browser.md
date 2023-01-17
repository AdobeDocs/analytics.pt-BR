---
title: Navegador
description: O nome e a versão do navegador usado.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 39f1ac66fb6374c62f790f9a38a52fba3bf9bda1
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# Navegador

O &quot;[!UICONTROL Navegador]A dimensão &#39; informa o nome e a versão do navegador que está enviando a ocorrência. Essa dimensão é útil para entender os navegadores mais comuns que os visitantes usam. Ao testar novas versões do site, você pode executar esses testes nos navegadores principais nesta dimensão para maximizar os esforços de controle de qualidade.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem os nomes e as versões do navegador usadas. Diferentes versões do mesmo navegador são itens de dimensão separados.

Alguns itens de dimensão contêm `"(unknown version)"` em vez do número de versão. Esse item de dimensão faz referência a uma versão recente do navegador que a Adobe não adicionou às tabelas de pesquisa. Como os navegadores são atualizados com frequência, o `"(unknown version)"` para um determinado navegador é comum e temporário. A Adobe normalmente atualiza as tabelas de pesquisa durante as versões de manutenção mensais.

## Alterações na rotulagem e definição

Abaixo está uma lista de alterações em como os navegadores são representados nos relatórios. Essas alterações podem afetar seus relatórios ou qualquer lógica, como segmentos, que depende desses valores.

### Remoção da empresa do navegador

A partir da versão 100 para navegadores Chrome, Edge e Firefox, o nome da empresa não será mais exibido antes do navegador. Isso pode afetar os usuários se eles tiverem definições de segmento baseadas no nome do navegador. Por exemplo, um segmento que inclui uma definição de que &quot;o navegador contém &quot;Google&quot; não identificará mais os navegadores Chrome a partir da versão 110.

Exemplos:

A versão 109 do Chrome será exibida como &quot;Google Chrome 109&quot;.
A versão 110 do Chrome será exibida como &quot;Chrome 109&quot;.

### Remoção da distinção entre móvel e não móvel para Chrome

A partir do Chrome 110, as versões para dispositivos móveis e não móveis do Chrome serão rotuladas da mesma maneira. Atualmente, as versões móveis e não móveis são rotuladas separadamente. Importante: isso altera o significado do nome sem &quot;dispositivo móvel&quot;. O &quot;Chrome 109&quot; é móvel e não móvel (ou seja, desktop), o &quot;Chrome 110&quot; é móvel e não móvel. Novamente, se você tiver definições de segmento que fazem referência a &quot;dispositivos móveis&quot; no nome do navegador, elas podem não funcionar mais como esperado. Você pode usar a segmentação e os detalhamentos móveis para comparar o tráfego móvel ao não móvel.

Exemplos:

O Mobile Chrome 109 será exibido como &quot;Chrome Mobile 109&quot;.
O Chrome 109 não móvel será exibido como &quot;Chrome 109&quot;.

O Mobile Chrome 110 será exibido como &quot;Chrome 110&quot;.
O Chrome 110 não móvel será exibido como &quot;Chrome 110&quot;.
