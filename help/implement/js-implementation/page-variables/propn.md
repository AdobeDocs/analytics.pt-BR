---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# propN

As variáveis de propriedade ([!UICONTROL prop]) são usadas para criar relatórios personalizados dentro do [!UICONTROL Módulo de Tráfego].

<!-- 

propN.xml

 -->

A variável props pode ser usada como contadores (para contar o número de vezes que uma exibição de página é enviada), para relatório de definição de caminho ou em relatórios de correlação.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | c1-c75 | Tráfego personalizado | "" |

**Sintaxe e valores possíveis** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

Não há limitações nas variáveis [!UICONTROL property] além das limitações padrão de variáveis.

**Exemplos** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Configurações** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Entre em contato com o Atendimento ao cliente da Adobe para saber como mostrar as métricas de [!UICONTROL Visita], [!UICONTROL Visitante] e [!UICONTROL Caminho] para variáveis [!UICONTROL prop].
