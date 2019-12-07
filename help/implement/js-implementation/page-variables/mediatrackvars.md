---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# media.trackVars

A variável identifica quais variáveis devem ser enviadas com uma ocorrência de mídia.


<!-- 

media_trackVars.xml

 -->

Ela só é aplicável com JavaScript e [!UICONTROL ActionSource].

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackVars="None" |

**Sintaxe e valores possíveis** {#section_7374684A7EB34AE685E8C40A66CFD289}

Nomes de variáveis, como [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`* e assim por diante.

**Exemplos** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Armadilhas, dúvidas e dicas** {#section_615AE1B696124B00B78F651B03813EAB}

* Mesmo se eVar3 for especificada no [!UICONTROL trackVars], ela será enviada com a ocorrência de mídia.

## dispositivo móvel {#concept_0CEE045F57B444138C0EAA015FC7EA70}

A variável controla a ordem em que os cookies e as IDs do assinante são usados para identificar visitantes.

<!-- 

mobile.xml

 -->

Consulte [Protocolos de rede móvel](/help/implement/js-implementation/c-additional-libraries/network-protocols.md).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | /5/ ou /1/ no caminho do url da imagem | N/D | Nenhum |

**Sintaxe e valores possíveis** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Armadilhas, dúvidas e dicas** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Use a identificação entre visitantes para atenuar possíveis picos no tráfego de visitantes, ao usar a variável *`s.mobile`* com a implementação do cookie JavaScript.
