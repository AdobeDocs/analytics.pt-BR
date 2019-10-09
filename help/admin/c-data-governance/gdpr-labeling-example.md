---
description: 'null'
seo-description: 'null'
seo-title: Exemplo de rotulagem
title: Exemplo de rotulagem
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: d2134271c4586d629c8b25f60c746902ba13683b

---


# Exemplo de rotulagem

## Dados de ocorrência de exemplo

Suponha que você tenha os seguintes dados de ocorrência:

* A primeira linha contém os rótulos para cada variável.
* A segunda linha é o nome da variável. Se tiver um rótulo de ID, ele conterá o namespace atribuído entre parênteses.
* Os dados de ocorrência começam na terceira linha.

| Rótulos | I2<br>ID-<br>PESSOAL-<br>PESSOA-PESSOA-PESSOA | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL | I2<br>DEL-<br>PERSONACC-PESSOA | I2<br>DEL-<br>DEVICEDEL-<br>PERSONACC-ALL | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL |
|---|---|---|---|---|---|
| **Nome**<br>**da variável (Namespace)** | **MyProp1**<br>**(usuário)** | **ID**<br>**do visitante (AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| Dados de ocorrência | Mary | 77 | Um | M | X |
|  | Mary | 88 | B | N | S |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | Um | N | Z |

## Exemplo de solicitação de acesso

Se uma solicitação de acesso for enviada, o arquivo de resumo conterá os valores indicados na tabela abaixo. Uma solicitação pode retornar somente um arquivo de dispositivo, somente um arquivo de pessoa ou um de cada. Dois arquivos de resumo são retornados somente se uma ID de pessoa for usada e expandIDs for verdadeiro.

| Valores da API | Valores da API | Tipo de arquivo retornado | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File | Data in <br>Summary Access File |
|--- |--- |--- |---|---|---|---|---|
| **Namespace/ID** | **expandIDs** |  | **MyProp1** | **Visitor ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | dispositivo | Variável não presente | 77 | Variável não presente | M, P | X, W |
| AAID=77 | true | dispositivo | Variável não presente | 77 | Variável não presente | M, P | X, W |
| user=Mary | false | contêiner de pessoa | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | contêiner de pessoa | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | dispositivo | não presente | 77, 88 | não presente | N, P | U, W |
| user=Mary AAID=66 | true | contêiner de pessoa | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary AAID=66 | true | dispositivo | não presente | 66, 77, 88 | não presente | N, P | U, W, Z |
| xyz=X | false | dispositivo | não presente | 55, 77 | não presente | M, R | X |
| xyz=X | true | dispositivo | não presente | 55, 77 | não presente | M, P, R | W, X |

Observe que a configuração de expandIDs não faz diferença para a saída quando uma ID de cookie é usada.

## Solicitação de exclusão de exemplo

Com uma solicitação de exclusão usando os valores da API na primeira linha da tabela, a tabela de ocorrências será atualizada para ser semelhante a esta:

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | Um | Privacidade-7398 | Privacidade-9152 |
| Mary | 88 | B | N | S |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacidade-1866 | Privacidade-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | Um | N | W |

>[!NOTE] Somente as células em linhas contendo AAID = 77 e um rótulo DEL-DEVICE são afetadas.

| user=<br>MaryspanIDs=false | user=<br>MaryspanIDs=false | user=<br>MaryspanIDs=false | user=<br>MaryspanIDs=false | user=<br>MaryspanIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacidade-0523 | 77 | Privacidade-1866 | Privacidade-3681 | X |
| Privacidade-0523 | 88 | Privacidade-2178 | Privacidade-1975 | S |
| Privacidade-0523 | 99 | Privacidade-9045 | Privacidade-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | Um | N | W |

>[!NOTE] Somente as células em linhas que contêm user=Mary e uma etiqueta DEL-PERSON são afetadas. Além disso, na prática, a variável que contém A_ID provavelmente seria uma prop ou eVar e seu valor de substituição seria uma string que começava com "Privacidade-", seguida por um número aleatório (GUID), em vez de substituir o valor numérico por um valor numérico diferente e aleatório.

| user=<br>MaryspanIDs=true | user=<br>MaryspanIDs=true | user=<br>MaryspanIDs=true | user=<br>MaryspanIDs=true | user=<br>MaryspanIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacidade-5782 | 09 | Privacidade-0859 | Privacidade-8183 | Privacidade-9152 |
| Privacidade-5782 | 16 | Privacidade-6104 | Privacidade-2911 | Privacidade-6821 |
| Privacidade-5782 | 83 | Privacidade-2714 | Privacidade-0219 | Privacidade-4395 |
| John | 09 | D | Privacidade-8454 | Privacidade-8216 |
| John | 16 | E | Privacidade-2911 | Privacidade-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | Um | N | W |

Observe o seguinte:

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2`A na quarta e na quinta linha é atualizada, pois essas linhas contêm os mesmos valores de ID de visitante que os da primeira e da segunda linha, portanto, a expansão de ID inclui esses valores para as exclusões a nível de dispositivo.
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3`O se comporta de maneira muito diferente em relação ao comportamento sem expansão de ID, porque neste caso, não há correspondência de `ID-DEVICES` Now `AAID` matches on the first five rows.
