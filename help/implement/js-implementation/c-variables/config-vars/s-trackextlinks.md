---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.trackExternalLinks

Se for 'true',  e serão usados para determinar se qualquer link clicado é um link de saída.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

A variável *`trackExternalLinks`* só deve ser definida como 'false' se não houver links no site ou se você não fizer questão de rastrear o número de cliques nos links de saída. Um link de saída é qualquer link que leva um visitante para fora do site. Se *`trackExternalLinks`* é 'true', portanto, quando você clicar no link de saída, o rastreamento de dados será enviado imediatamente. Os dados enviados com um link de saída incluem o URL do link, o nome do link e os dados do mapa de cliques para esse link. Se *`trackExternalLinks`* é 'false', portanto, o mapa de cliques do visitante para links de saída provavelmente serão reportados incorretamente.

## Sintaxe e valores possíveis

A variável *`trackExternalLinks`* pode ser 'true' ou 'false'.

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

Nenhum

## Armadilhas, dúvidas e dicas

* Quando *`trackExternalLinks`* é 'false', os links que afastam as pessoas do site provavelmente serão reportados incorretamente no mapa de cliques do visitante.

* Quando *`trackExternalLinks`* é 'true', os dados são enviados sempre que um visitante clicar em um link de saída (antes do carregamento do público alvo de saída).
