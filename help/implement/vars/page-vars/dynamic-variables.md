---
title: Variáveis dinâmicas
description: Copie variáveis sem aumentar a duração da solicitação de imagem.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# Variáveis dinâmicas

As variáveis dinâmicas permitem copiar valores de uma variável para outra sem aumentar a duração da solicitação de imagem. Eles são úteis ao capturar os mesmos dados em várias variáveis.

Nas versões anteriores do Analytics, a duração da solicitação de imagem era importante para evitar dados truncados. As melhorias no AppMeasurement permitem sequências de consulta de solicitação de imagem muito mais longas, de modo que as variáveis dinâmicas normalmente não são necessárias.

As variáveis dinâmicas suportam parâmetros de sequência de caracteres de consulta ou cabeçalhos HTTP em uma solicitação de imagem. Consulte parâmetros [de consulta de coleta de](../../validate/query-parameters.md) dados para obter uma lista completa dos parâmetros disponíveis para referência. Consulte Campos [de solicitação](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) padrão na Wikipedia para obter uma lista completa dos campos de solicitação HTTP disponíveis para referência.

Quando a Adobe reconhece um prefixo de variável dinâmica, ela copia automaticamente a string de consulta ou o valor do cabeçalho HTTP no conjunto de relatórios. Essa ação ocorre antes de qualquer outro processamento, incluindo regras de processamento e regras VISTA.

> [!TIP] Considere os limites máximos de caracteres ao copiar variáveis. Por exemplo, se copiar `eVar1` para `prop1`, `prop1` pode ter um valor truncado, pois ele tem um limite de 100 bytes (enquanto `eVar1` tem um limite de 255 bytes).

## Variáveis dinâmicas no Adobe Experience Platform Launch

É possível usar variáveis dinâmicas em qualquer campo de dimensão que aceite uma string. Os valores de dimensão normalmente são definidos durante a configuração da extensão do Analytics (variáveis globais) ou em regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize o valor de dimensão desejado.

Coloque o prefixo da variável dinâmica no campo de texto, seguido pelo parâmetro da string de consulta ou pelo cabeçalho HTTP que você deseja referenciar. Por padrão, o prefixo da variável dinâmica é `D=`.

## Variáveis dinâmicas no AppMeasurement e no editor de código personalizado Iniciar

As variáveis dinâmicas são strings de texto atribuídas a outras variáveis. O prefixo da variável dinâmica padrão é `D=`. As variáveis dinâmicas fazem distinção entre maiúsculas e minúsculas.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

> [!NOTE] As variáveis dinâmicas aparecem como strings ao depurar sua implementação. Os valores são copiados do lado do servidor pelos servidores de coleta de dados da Adobe.
