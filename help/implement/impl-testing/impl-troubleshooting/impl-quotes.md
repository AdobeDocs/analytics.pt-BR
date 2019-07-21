---
description: Quando você insere valores em uma variável, deve seguir algumas práticas recomendadas.
keywords: Implementação do Analytics
seo-description: Quando você insere valores em uma variável, deve seguir algumas práticas recomendadas.
seo-title: Uso de aspas
solution: Analytics
subtopic: Solução de problemas
title: Uso de aspas
topic: Desenvolvedor e implementação
uuid: 9 f 09 c 48 b -7 ae 5-441 e -8635-fd 6 bdc 2 e 94 c 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso de aspas

Quando você insere valores em uma variável, deve seguir algumas práticas recomendadas.

Você pode usar aspas simples ou duplas, assegure-se de ser consistente. Se você estiver usando aspas simples, sempre use aspas simples. Se você estiver usando aspas duplas, sempre use aspas duplas. Ambos os exemplos abaixo estão corretos.

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Verifique se as aspas inteligentes estão desativadas. Se você estiver usando aspas simples e tiver um apóstrofo no valor da variável, o JavaScript interpretará o apóstrofo como aspas simples. Isso significa que esse será o fim da string. Considere o exemplo a seguir:

```js
s.pageName='John's Home Page'
```

Nesse caso, o JavaScript interpretaria o apóstrofo (que também é uma aspa simples) de "John's" como o fim da string. Como "'s Home Page" não tem significado em JavaScript, ocorrerá um erro que impede a realização da solicitação de imagem. Um dos exemplos a seguir funcionaria:

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

No primeiro exemplo, você pode driblar o apóstrofo e inserir uma barra invertida (\) imediatamente após ele. O JavaScript entenderá que o apóstrofo não está no fim da string, mas sim que faz parte dela. A string será encerrada então como pretendido, na aspa simples de fechamento. O segundo exemplo usa aspas duplas em toda a string. Nesse caso, uma aspa simples não pode indicar o fim da string. O mesmo se aplica se uma aspa dupla for parte da string. Um valor de s.pageName="Team Says "We Win!"" seria incorreto, devido ao uso de aspas duplas dentro da string, assim como a envolvendo. Essa string seria correta se tivesse sido inserida como s.pageName="Team Says \"We \"".
