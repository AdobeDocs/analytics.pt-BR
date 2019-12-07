---
description: Quando você insere valores em uma variável, deve seguir algumas práticas recomendadas.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Uso de aspas
topic: Developer and implementation
uuid: 9f09c48b-7ae5-441e-8635-fd6bdc2e94c7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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
