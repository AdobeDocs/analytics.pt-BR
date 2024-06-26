---
description: É possível preencher uma variável usando um parâmetro da string de consulta.
subtopic: Processing rules
title: Preenchimento de uma ID de campanha a partir de um parâmetro da cadeia de caracteres de consulta
feature: Admin Tools
role: Admin
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%

---

# Preenchimento de uma ID de campanha a partir de um parâmetro da cadeia de caracteres de consulta

É possível preencher uma variável usando um parâmetro da string de consulta.

Na maioria dos casos, você usa um plug-in para preencher variáveis a partir da sequência de consulta. Se um erro de digitação ou problema semelhante impedir o preenchimento do valor, a variável poderá ser preenchida por regras de processamento.

Você deve sempre conferir se um valor está vazio ou se contém o valor esperado antes de sobrescrevê-lo.

| Conjunto de regras | Valor |
|---|---|
| Condição | A campanha não foi definida |
| Ação | Substitui o valor da campanha por um parâmetro da string de consulta cpid |

Por exemplo:

![](assets/set-campaign-conditionally.png)
