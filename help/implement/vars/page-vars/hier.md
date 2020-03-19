---
title: hier
description: Implemente variáveis de hierarquia no Adobe Analytics.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# hier

As variáveis de hierarquia são variáveis personalizadas que permitem visualizar a estrutura de um site.

> [!TIP] Essa variável era mais comum em versões anteriores do Adobe Analytics. A Adobe recomenda usar [eVars](evar.md) e classificações.

Essa variável é útil para sites que têm mais de três níveis em sua estrutura de site. Por exemplo, um site de mídia pode ter quatro níveis para a seção de Esportes: `Sports`, `Local Sports`, `Baseball`e `Team name`. Se alguém visitar a página Beisebol, as páginas Esportes, Esportes locais e Beisebol refletirão essa visita.

A Adobe oferece suporte a até 5 variáveis de hierarquia na sua implementação. No momento em que a hierarquia é ativada, escolha um delimitador para a variável e o número máximo de níveis para a hierarquia. Por exemplo, se o delimitador for uma vírgula, a hierarquia seria semelhante ao seguinte:

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

Verifique se nenhum dos nomes da sua seção inclui o delimitador. Por exemplo, se uma de suas seções for chamada `Coach Griffin, Jim`, escolha um delimitador diferente de vírgula. O limite total da variável é de 255 bytes. Os delimitadores podem consistir em vários caracteres, como `||` ou `/|\`, que têm menos probabilidade de aparecer em valores variáveis.

## Exemplos

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
