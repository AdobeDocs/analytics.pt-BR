---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# propN

As variáveis de propriedade (`prop`) são usadas para criar relatórios personalizados dentro do Módulo de Tráfego.

<!-- 

propN.xml

 -->

A variável props pode ser usada como contadores (para contar o número de vezes que uma exibição de página é enviada), para relatório de definição de caminho ou em relatórios de correlação.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | c1-c75 | Tráfego personalizado | "" |

**Sintaxe e valores possíveis**

```js
s.propN="value"
```

Não há limitações nas variáveis [!UICONTROL property] além das limitações padrão de variáveis.

**Exemplos**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Configurações**

Entre em contato com o Atendimento ao cliente da Adobe para saber como mostrar as métricas de Visita, Visitante e Caminho para variáveis `prop`.
