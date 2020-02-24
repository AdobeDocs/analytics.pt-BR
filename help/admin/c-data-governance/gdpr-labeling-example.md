---
description: 'null'
title: Exemplo de rotulagem
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Exemplo de rotulagem

## Dados de ocorrência de exemplo

Suponha que você tenha os seguintes dados de ocorrência:

* A primeira linha contém os rótulos para cada variável.
* A segunda linha é o nome da variável. Se tiver um rótulo de ID, ele conterá o namespace atribuído entre parênteses.
* Os dados de ocorrência começam na terceira linha.

| Rótulos | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Nome da variável**<br>**(Namespace)** | **MyProp1**<br>**(usuário)** | **ID de visitante**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| Dados de ocorrência | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | S |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Exemplo de solicitação de acesso

Se uma solicitação de acesso for enviada, o arquivo de resumo conterá os valores indicados na tabela abaixo. Uma solicitação pode retornar somente um arquivo de dispositivo, somente um arquivo de pessoa ou um de cada. Dois arquivos de resumo são retornados somente se uma ID de pessoa for usada e expandIDs for verdadeiro.

| Valores da API | Valores da API | Tipo de arquivo retornado | Dados no <br>Arquivo de acesso do resumo | Dados no <br>Arquivo de acesso do resumo | Dados no <br>Arquivo de acesso do resumo | Dados no <br>Arquivo de acesso do resumo | Dados no <br>Arquivo de acesso do resumo |
|--- |--- |--- |---|---|---|---|---|
| **Namespace/ID** | **expandIDs** |  | **MyProp1** | **Visitor ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | dispositivo | Variável não presente | 77 | Variável não presente | M, P | X, W |
| AAID=77 | true | dispositivo | Variável não presente | 77 | Variável não presente | M, P | X, W |
| user=Mary  | false | contêiner de pessoa | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
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
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | S |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE] Apenas células em linhas que contêm AAID = 77 e um rótulo DEL-DEVICE são afetadas.

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | S |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE] Apenas células em linhas que contêm user=Mary e um rótulo DEL-PERSON são afetadas. Além disso, na prática, a variável que contém A_ID provavelmente seria uma prop ou eVar e seu valor de substituição seria uma sequência de caracteres iniciada com &quot;Privacy-&quot;, seguida por um número aleatório (GUID), em vez de substituir o valor numérico por um diferente e aleatório.

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Observe o seguinte:

* As células nas linhas que contêm `user=Mary` e um rótulo `DEL-DEVICE` ou `DEL-PERSON` são afetadas, bem como as células com um rótulo `DEL-DEVICE` nas linhas que contêm qualquer ID de visitante que ocorreu em uma linha que contém `user=Mary`.
* `MyEvar2`A na quarta e na quinta linha é atualizada, pois essas linhas contêm os mesmos valores de ID de visitante que os da primeira e da segunda linha, portanto, a expansão de ID inclui esses valores para as exclusões a nível de dispositivo.
* Os valores de `MyEvar2` nas linhas dois e cinco correspondem a antes e depois da exclusão, mas após a exclusão, eles não corresponderão mais ao valor N existente na última linha, pois tal linha não foi atualizada como parte da solicitação de exclusão.
* `MyEvar3`O se comporta de maneira muito diferente em relação ao comportamento sem expansão de ID, porque neste caso, não há correspondência de `ID-DEVICES`. Agora, `AAID` corresponde nas cinco primeiras linhas.
