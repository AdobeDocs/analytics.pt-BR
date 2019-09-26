---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkLeaveQueryString

Por padrão, as sequências de consulta são excluídas de todos os relatórios.

Para alguns links de saída e links de download, a parte importante do URL pode estar na string de consulta, como mostrado na seguinte URL de exemplo.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

O nome do arquivo de download pode ser definido na string de consulta e, consequentemente, a string de consulta será necessária para tornar o relatório [!UICONTROL Downloads de arquivos] mais preciso.

A variável *`linkLeaveQueryString`* determina se a string de consulta deve ou não ser incluída nos relatórios de [!UICONTROL Links de saída ]e [!UICONTROL Downloads de arquivo].

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|--- |--- |--- |--- |
| N/A | N/A | Exit Links File Downloads | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

## Sintaxe

```js
s.linkLeaveQueryString=[false/true]
```

## Exemplos

```js
s.linkLeaveQueryString=false
```

## Valores possíveis

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Configurações

Nenhuma configuração é necessária para essa variável.

## Armadilhas, dúvidas e dicas

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.
