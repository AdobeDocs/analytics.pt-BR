---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackDownLoadLinks

Defina como 'true' se você deseja rastrear links para arquivos do site que podem ser obtidos por download.

Se *`trackDownloadLinks`* for 'true' *`linkDownloadFileTypes`* será usado para determinar os links que são arquivos baixáveis.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

A variável *`trackDownloadLinks`* só deve ser definida como 'false' se não houver links para arquivos baixáveis no site ou se você não fizer questão de rastrear o número de cliques nos arquivos baixáveis. Se *`trackDownloadLinks`* for 'true', quando um link de download de arquivo for clicado, os dados serão enviados para o [!DNL Analytics]. Os dados enviados com um link de download incluem a URL de download do link e os dados do mapa de cliques do visitante para esse link. Se *`trackDownloadLinks`* é 'false', portanto, os dados do mapa de cliques do visitante para os arquivos baixáveis no site provavelmente serão reportados incorretamente.

## Sintaxe e valores possíveis

A variável *`trackDownloadLinks`* pode ser 'true' ou 'false'.

## Exemplos

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* Quando *`trackDownloadLinks`* é 'false', os links usados pelas pessoas para baixar arquivos no site provavelmente são reportados incorretamente no mapa de cliques do visitante.

* Quando *`trackDownloadLinks`* é 'true', os dados são enviados sempre que um visitante clicar em um link de download de arquivo.
