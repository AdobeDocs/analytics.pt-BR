---
title: Variáveis dinâmicas
description: Copie variáveis sem aumentar a duração da solicitação de imagem.
feature: Variables
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 82%

---

# Variáveis dinâmicas

As variáveis dinâmicas permitem copiar valores de uma variável para outra sem aumentar a duração da solicitação de imagem. Elas são úteis quando é necessário capturar os mesmos dados em muitas variáveis.

Nas versões anteriores do Analytics, a duração da solicitação de imagem era importante para evitar dados truncados. As melhorias no AppMeasurement permitem strings de consulta de solicitação de imagem muito mais longas, de modo que as variáveis dinâmicas normalmente não são necessárias.

As variáveis dinâmicas suportam strings de consulta como parâmetro ou cabeçalhos HTTP em uma solicitação de imagem. Consulte [Parâmetros de consulta de coleta de dados](../../validate/query-parameters.md) para obter uma lista completa dos parâmetros disponíveis para referência. Consulte [Campos padrão de solicitação](https://pt.wikipedia.org/wiki/Lista_de_campos_de_cabeçalho_HTTP) na Wikipedia para obter uma lista completa dos campos de solicitação HTTP disponíveis para referência.

Quando a Adobe reconhece um prefixo de variável dinâmica, ela copia automaticamente a string de consulta ou o valor do cabeçalho HTTP no conjunto de relatórios. Essa ação ocorre antes de qualquer outro processamento, incluindo regras de processamento e regras VISTA.

>[!TIP]
>
>Considere os limites máximos de caracteres ao copiar variáveis. Por exemplo, se copiar `eVar1` para `prop1`, `prop1` pode ter um valor truncado, pois tem um limite de 100 bytes (enquanto `eVar1` tem um limite de 255 bytes).

## Variáveis dinâmicas que usam o SDK da Web

Use o mapeamento da sequência de dados para enviar dados para várias variáveis do Analytics a partir de um único campo XDM.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Datastreams]** no painel esquerdo.
1. Clique no fluxo de dados desejado.
1. Clique em **[!UICONTROL Editar mapeamento]** à direita.
1. Mapear o desejado [!UICONTROL Campo de origem] ao desejado [!UICONTROL Campo de destino]. Um único campo de origem pode mapear para qualquer número de campos de destino.

## Variáveis dinâmicas usando a extensão Adobe Analytics

É possível usar variáveis dinâmicas em qualquer campo de dimensão que aceite uma string. Os itens de dimensão normalmente são definidos durante a configuração da extensão do Analytics (variáveis globais) ou em regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize o item de dimensão desejado.

Coloque o prefixo da variável dinâmica no campo de texto, seguido pelo parâmetro da string de consulta ou pelo cabeçalho HTTP que você deseja referenciar. Por padrão, o prefixo da variável dinâmica é `D=`.

## Variáveis dinâmicas no AppMeasurement e no editor de código personalizado da extensão do Analytics

As variáveis dinâmicas são strings de texto atribuídas a outras variáveis. O prefixo padrão da variável dinâmica é `D=`. As variáveis dinâmicas fazem distinção entre maiúsculas e minúsculas.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>As variáveis dinâmicas aparecem como strings ao depurar sua implementação. No lado do servidor, os valores são copiados pelos servidores de coleta de dados da Adobe.
