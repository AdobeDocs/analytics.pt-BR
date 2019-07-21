---
description: É possível preencher uma variável usando um parâmetro da string de consulta
seo-description: É possível preencher uma variável usando um parâmetro da string de consulta
seo-title: Preencher uma ID de campanha a partir de um parâmetro da string de consulta
solution: Analytics
subtopic: Regras de processamento
title: Preencher uma ID de campanha a partir de um parâmetro da string de consulta
topic: Ferramentas administrativas
uuid: 2 bc 61 f 9 f-d 8 d 2-41 b 7-bd 39-4 a 9 df 30 ff 013
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Preencher uma ID de campanha a partir de um parâmetro da string de consulta

É possível preencher uma variável usando um parâmetro da string de consulta

Na maioria dos casos, você usa um plug-in para preencher variáveis a partir da string de consulta. Se um erro de digitação ou problema semelhante impedir o preenchimento do valor, a variável poderá ser preenchida por regras de processamento.

Você deve sempre conferir se um valor está vazio ou se contém o valor esperado antes de sobrescrevê-lo.

| Conjunto de regras | Valor |
|---|---|
| Condição | A campanha não foi definida |
| Ação | Substitui o valor da campanha por um parâmetro da string de consulta cpid |

Por exemplo:

![](assets/set-campaign-conditionally.png)

