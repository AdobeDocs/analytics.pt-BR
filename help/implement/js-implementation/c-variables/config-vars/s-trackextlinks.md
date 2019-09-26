---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackExternalLinks

Se for 'true' e forem usados para determinar se qualquer link clicado é um link de saída.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

The *`trackExternalLinks`* variable should only be set to 'false' if there are no exit links on your site, or if you don't care to track the number of clicks on those exit links. Um link de saída é qualquer link que leva um visitante para fora do site. Se *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. Os dados enviados com um link de saída incluem o URL do link, o nome do link e os dados do mapa de cliques para esse link. Se *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

## Sintaxe e valores possíveis

A variável *`trackExternalLinks`pode ser 'true' ou 'false'.*

```
js
s.trackExternalLinks=true|false
```

## Exemplos

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.

* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).
