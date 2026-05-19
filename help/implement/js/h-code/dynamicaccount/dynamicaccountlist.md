---
title: dynamicAccountList
description: Estabeleça lógica sobre como a implementação determina o conjunto de relatórios.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
TQID: https://experienceleague.adobe.com/qqkQoYsBWdTDOIkNfregm4k11CoDEl3dOJ3HNCMIo3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 89%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas AppMeasurement atuais ou com a Coleção de dados da Adobe Experience Platform.

A variável `s.dynamicAccountList` determina dinamicamente o valor de `s_account`. Se `dynamicAccountSelection` estiver definida como `true`, a variável `dynamicAccountMatch` será comparada com `dynamicAccountList`. Se uma correspondência for encontrada, a ID do conjunto de relatórios correspondente será usada.

## Sintaxe

Essa variável é uma cadeia de caracteres que é analisada automaticamente pelo arquivo JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

A entrada válida é uma lista separada por ponto e vírgula de pares de rsid e valor. Cada lista contém os seguintes itens:

* Uma ou mais IDs do conjunto de relatórios (separadas por vírgulas)
* Um sinal de igual
* Uma ou mais cadeias de caracteres para corresponder (separadas por vírgulas)

Somente caracteres ASCII padrão devem ser usados na cadeia de caracteres. Não inclua espaços.

## Exemplos

Em todos os exemplos a seguir, o URL da página é `https://example.com/path2/?prod_id=12345`, a variável `dynamicAccountSelection` é definida como `true`, e a `s_account` variável é definida como `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Armadilhas, dúvidas e dicas

* As regras listadas nesta variável são aplicadas em uma ordem da esquerda para a direita. Se a variável `dynamicAccountMatch` corresponder a mais de uma regra, a regra mais à esquerda será usada para determinar o conjunto de relatórios. Como resultado, mova mais genéricas para a direita na lista.
* Se nenhuma regra for correspondente, o conjunto de relatórios padrão em `s_account` será usado.
* Se a página for salva no disco rígido de uma pessoa ou traduzida por um mecanismo de tradução baseado na Web (como as páginas traduzidas do Google), a seleção de conta dinâmica provavelmente não funcionará.
* As regras `dynamicAccountSelection` se aplicam à seção do URL especificada em `dynamicAccountMatch`.
* Use o Adobe CX Enterprise Debugger para testar o conjunto de relatórios de destino.
