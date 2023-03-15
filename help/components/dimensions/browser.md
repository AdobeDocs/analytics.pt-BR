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

O &#39;[!UICONTROL Navegador]A dimensão &quot; informa o nome e a versão do navegador que envia a ocorrência. Essa dimensão é útil para entender os navegadores mais comuns que os visitantes usam. Ao testar novas versões do site, você pode executar esses testes nos navegadores principais nesta dimensão para maximizar os esforços de controle de qualidade.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem os nomes e as versões do navegador usadas. Diferentes versões do mesmo navegador são itens de dimensão separados.

Alguns itens de dimensão contêm `"(unknown version)"` em vez do número de versão. Esse item de dimensão faz referência a uma versão recente do navegador que a Adobe não adicionou às tabelas de pesquisa. Como os navegadores são atualizados com frequência, o `"(unknown version)"` para um determinado navegador é comum e temporário. A Adobe normalmente atualiza as tabelas de pesquisa durante as versões de manutenção mensais.

## Alterações da rotulagem e da definição

Abaixo está uma lista de alterações no modo como os navegadores são representados nos relatórios. Essas alterações podem afetar seus relatórios ou qualquer lógica, como segmentos, que dependa desses valores.

### Removendo empresa do navegador

A partir da versão 100 para navegadores Chrome, Edge e Firefox, o nome da empresa não será mais exibido antes do navegador. Isso pode afetar os usuários se eles tiverem definições de segmento baseadas no nome do navegador. Por exemplo, um segmento que inclui uma definição de que &quot;navegador contém &quot;Google&quot; não identificará mais navegadores Chrome a partir da versão 110.

Exemplos:

A versão 109 do Chrome será exibida como &quot;Google Chrome 109&quot;.
A versão 110 do Chrome será exibida como &quot;Chrome 109&quot;.

### Remoção da distinção entre dispositivos móveis e não móveis para o Chrome

A partir do Chrome 110, as versões móveis e não móveis do Chrome serão rotuladas da mesma forma. Atualmente, as versões móveis e não móveis são rotuladas separadamente. É importante observar que isso altera o significado do nome sem &quot;celular&quot;. &quot;Chrome 109&quot; é não móvel (ou seja, desktop) &quot;Chrome 110&quot; é móvel e não móvel. Novamente, se você tiver definições de segmento que fazem referência a &quot;móvel&quot; no nome do navegador, elas podem não funcionar mais conforme esperado. Você pode usar a segmentação móvel e detalhamentos para comparar o tráfego móvel com o não móvel.

Exemplos:

O Chrome 109 móvel aparecerá como &quot;Chrome Mobile 109&quot;.
O Chrome 109 não móvel será exibido como &quot;Chrome 109&quot;.

O Chrome 110 para dispositivos móveis será exibido como &quot;Chrome 110&quot;.
O Chrome 110 não móvel será exibido como &quot;Chrome 110&quot;.
