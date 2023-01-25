---
description: Você pode copiar o valor de uma eVar em um prop para ativar a definição de caminho.
subtopic: Processing rules
title: Determinar um caminho copiando um valor de eVar em uma propriedade
feature: Admin Tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

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
