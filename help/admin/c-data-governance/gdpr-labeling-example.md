---
description: 'null'
seo-description: 'null'
seo-title: Exemplo de rotulagem
title: Exemplo de rotulagem
uuid: a 9 a 5 b 937-dbde -4 f 0 f-a 171-005 ef 4 c 79 df 9
translation-type: tm+mt
source-git-commit: fe1d2eb0bae02ee9eeb59e1689519836f8acf8db

---


# Exemplo de rotulagem

## Dados de ocorrência de exemplo {#section_94DE6BC0026F46D7AD7061C5625C8D52}

Suponha que você tenha os seguintes dados de ocorrência:

* A primeira linha contém os rótulos para cada variável.
* A segunda linha é o nome da variável. Se tiver um rótulo de ID, ele conterá o namespace atribuído entre parênteses.
* Os dados de ocorrência começam na terceira linha.

<!-- Meike, I converted html tables for fix elusive validation error. Bob -->

| Rótulos | I2<br>ID-CUSTOMDEL<br>-CUSTOMACC<br>-PERSON | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL | I 2<br>DEL-CUSTOMACC<br>-PERSON | I 2<br>DEL-DEVICEDEL<br>-CUSTOMACC<br>-ALL | I 2<br>ID-DEVICEDEL<br>-DEVICEACC<br>-ALL |
|---|---|---|---|---|---|
| Nome da variável<br>(Namespace) | Myprop 1<br>(usuário) | ID do visitante<br>(AAID) | MyEvar1 | MyEvar2 | Myevar 3<br>(xyz) |
| Dados de ocorrência | Mary | 77 | Um | M | X |
|  | Mary | 88 | B | N | S |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | Um | N | Z |


## Exemplo de solicitação de acesso {#section_BDA817FD2415420DAAC835825484BA9D}

Se uma solicitação de acesso for enviada, o arquivo de resumo conterá os valores indicados na tabela abaixo. Uma solicitação pode retornar somente um arquivo de dispositivo, somente um arquivo de pessoa ou um de cada. Dois arquivos de resumo são retornados somente se uma ID de pessoa for usada e expandIDs for verdadeiro.

| Valores da API | Valores da API | Tipo de arquivo retornado | Data in <br>Summary Access File </br> | Data in <br>Summary Access File</br> | Data in <br>Summary Access File</br> | Data in <br>Summary Access File</br> | Data in <br>Summary Access File</br> |
|--- |--- |--- |---|---|---|---|---|
| Namespace/ID | expandIDs |  | MyProp1 | Visitor ID | MyEvar1 | MyEvar2 | MyEvar3 |
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

## Solicitação de exclusão de exemplo {#section_6C75F70F5D574BE7AA540981E8B7EA26}

Com uma solicitação de exclusão usando os valores da API na primeira linha da tabela, a tabela de ocorrências será atualizada para ser semelhante a esta:

| AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> | AAID=77 expandIDs value<br>does not matter</br> |
|---|---|---|---|---|
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| Mary | 42 | Um | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | S |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | Um | N | W |

>[!NOTE]
>
>Somente células em linhas contendo AAID = 77 e uma etiqueta DEL-DEVICE são afetadas.

| user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> | user = maryexpandids<br>= false</br> |
|--- |---|---|---|---|
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | S |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | Um | N | W |

>[!NOTE]
>
>Somente células em linhas contendo usuário = Mary e uma etiqueta DEL-PERSON são afetadas. Além disso, na prática, a variável que contém A_ID provavelmente seria uma prop ou eVar e seu valor de substituição seria uma sequência de caracteres iniciada com “GDPR-”, seguida por um número aleatório (GUID), em vez de substituir o valor numérico por um diferente e aleatório.

| user=Mary<br>expandIDs=true</br> | user = maryexpandids<br>= true</br> | user = maryexpandids<br>= true</br> | user = maryexpandids<br>= true</br> | user = maryexpandids<br>= true</br> |
|--- |---|---|---|---|
| MyProp1 | AAID | MyEvar1 | MyEvar2 | MyEvar3 |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | Um | N | W |

Observe o seguinte:

* As células em linhas que contenham user=Mary e um rótulo de DEL-DEVICE ou DEL-PERSON são afetadas, assim como as células com um rótulo de DEL-DEVICE em linhas que contenham qualquer ID de visitante presente em uma linha com user=Mary.
* A MyEvar2 na quarta e na quinta linha é atualizada, pois essas linhas contêm os mesmos valores de ID de visitante que os da primeira e da segunda linha, portanto, a expansão de ID inclui esses valores para as exclusões a nível de dispositivo.
* Os valores de MyEvar2 nas linhas dois e cinco correspondem a antes e depois da exclusão, mas após a exclusão, eles não corresponderão mais ao valor N existente na última linha, pois tal linha não foi atualizada como parte da solicitação de exclusão.
* O MyEvar3 se comporta de maneira muito diferente em relação ao comportamento sem expansão de ID, porque neste caso, não há correspondência de ID-DEVICES. Agora, AAID corresponde nas cinco primeiras linhas.
