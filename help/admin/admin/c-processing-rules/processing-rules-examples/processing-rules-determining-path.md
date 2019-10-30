---
description: Você pode copiar o valor de uma eVar em um prop para ativar a definição de caminho.
seo-description: Você pode copiar o valor de uma eVar em um prop para ativar a definição de caminho.
seo-title: Determinar um caminho copiando um valor de eVar em uma propriedade
solution: Analytics
subtopic: Regras de processamento
title: Determinar um caminho copiando um valor de eVar em uma propriedade
topic: Ferramentas administrativas
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Determinar um caminho copiando um valor de eVar em uma propriedade

Você pode copiar o valor de uma eVar em um prop para ativar a definição de caminho.

Quando valores são definidos, a variável à esquerda recebe o valor da variável à direita (mesmo que esteja vazia).

| Conjunto de regras | Valor |
|---|---|
| Condição | Nenhuma (sempre excluir) |
| Ação | Substituir o valor de Prop1 por eVar1 |

É possível modificar essa regra para definir o valor de Prop1 apenas se ele ainda não tiver um valor, semelhante ao exposto a seguir:

| Conjunto de regras | Valor |
|---|---|
| Condição | Se Prop1 não estiver definido |
| Ação | Substituir o valor de Prop1 por eVar1 |

Por exemplo:

![](assets/overwrite-empty-prop.png)

