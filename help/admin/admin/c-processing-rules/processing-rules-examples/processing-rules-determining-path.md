---
description: Você pode copiar o valor de uma eVar em um prop para ativar a definição de caminho.
subtopic: Processing rules
title: Determinar um caminho copiando um valor de eVar em uma propriedade
topic: Admin tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

