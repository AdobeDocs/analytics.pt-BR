---
description: Mostra exemplos de como rotular dados de hit, solicitações de acesso, solicitações de exclusão
title: Exemplo de rotulagem
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 3ff221b8715ecde6923310b6818904c697a2b003
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 87%

---

# Exemplo de rotulagem

## Dados de ocorrência de exemplo

Suponha que você tenha os seguintes dados de ocorrência:

* A primeira linha contém os rótulos para cada variável.
* A segunda linha é o nome da variável. Se tiver um rótulo de ID, ele conterá o namespace atribuído entre parênteses.
* Os dados de ocorrência começam na terceira linha.

| Rótulos | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Nome da variável** <br> **(Namespace)** | **MyProp1** <br> **(usuário)** | **ID de visitante** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| Dados de ocorrência | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77º | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Exemplo de solicitação de acesso

Se eu enviar uma solicitação de acesso, o arquivo de resumo conterá os valores indicados na tabela abaixo. Uma solicitação pode retornar somente um arquivo de dispositivo, somente um arquivo de pessoa ou um de cada. Dois arquivos de resumo são retornados somente se uma ID de pessoa for usada e expandIDs for verdadeiro.

<table>
  <tr>
    <th colspan="2" style="text-align:center">Valores da API</th>
    <th rowspan="2">Tipo de arquivo retornado<br></th>
    <th colspan="5" style="text-align:center">Dados no Arquivo de acesso do resumo</th>
  </tr>
  <tr>
    <th>Namespace/ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>ID de visitante</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>false</td>
    <td>dispositivo</td>
    <td>não presente</td>
    <td>77º</td>
    <td>não presente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>não presente</td>
    <td>77º</td>
    <td>não presente</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>pessoa</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>pessoa</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>dispositivo</td>
    <td>não presente</td>
    <td>77, 88</td>
    <td>A,B,C</td>
    <td>N, P</td>
    <td>U, W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>pessoa</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A,B,C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>dispositivo</td>
    <td>não presente</td>
    <td>66, 77, 88</td>
    <td>A,B,C</td>
    <td>N, P</td>
    <td>U, W, Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>dispositivo</td>
    <td>não presente</td>
    <td>55, 77</td>
    <td>não presente</td>
    <td>M, R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>dispositivo</td>
    <td>não presente</td>
    <td>55, 77</td>
    <td>não presente</td>
    <td>M, P, R</td>
    <td>W, X</td>
  </tr>
</table>

Observe que a configuração de expandIDs não faz diferença para a saída quando uma ID de cookie é usada.

## Solicitações de exclusão de exemplo

Com uma solicitação de exclusão usando os valores da API na primeira linha da tabela, a tabela de ocorrências será atualizada para ser semelhante a esta:

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(o valor expandIDs não importa)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacy-7398</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42º</td>
    <td>D</td>
    <td>Privacy-1866</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44º</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66º</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Apenas células em linhas que contêm AAID = 77 e um rótulo DEL-DEVICE são afetadas.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary<br>expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>77º</td>
    <td>Privacy-1866</td>
    <td>Privacy-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>88</td>
    <td>Privacy-2178</td>
    <td>Privacy-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>99</td>
    <td>Privacy-9045</td>
    <td>Privacy-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77º</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44º</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66º</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Apenas células em linhas que contêm user=Mary e um rótulo DEL-PERSON são afetadas. Além disso, na prática, a variável que contém A_ID provavelmente seria uma prop ou eVar e seu valor de substituição seria uma sequência de caracteres iniciada com &quot;Privacy-&quot;, seguida por um número aleatório (GUID), em vez de substituir o valor numérico por um diferente e aleatório.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary<br>expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>09</td>
    <td>Privacy-0859</td>
    <td>Privacy-8183</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>16</td>
    <td>Privacy-6104</td>
    <td>Privacy-2911</td>
    <td>Privacy-6821</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>83</td>
    <td>Privacy-2714</td>
    <td>Privacy-0219</td>
    <td>Privacy-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacy-8454</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16º</td>
    <td>E</td>
    <td>Privacy-2911</td>
    <td>Privacy-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44º</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66º</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

Observe o seguinte:

* As células em linhas que contêm `user=Mary` e um rótulo `DEL-DEVICE` ou `DEL-PERSON` são afetadas, bem como as células com um rótulo `DEL-DEVICE` em linhas que contêm qualquer ID de visitante (AAID) que ocorreu em uma linha que contém `user=Mary`.
* A configuração expandIDs não expande a chamada para incluir valores presentes em MyEvar3, que tem um rótulo ID-DEVICE, quando `user=Mary`. Expandir IDs só se expande para incluir IDs de visitante (AAIDs neste exemplo, mas também a ECID) em linhas nas quais `user=Mary`.
* `MyEvar2`A na quarta e na quinta linha é atualizada, pois essas linhas contêm os mesmos valores de ID de visitante que os da primeira e da segunda linha, portanto, a expansão de ID inclui esses valores para as exclusões a nível de dispositivo.
* Os valores de `MyEvar2` nas linhas dois e cinco correspondem a antes e depois da exclusão, mas após a exclusão, eles não corresponderão mais ao valor N existente na última linha, pois tal linha não foi atualizada como parte da solicitação de exclusão.
* `MyEvar3`O se comporta de maneira muito diferente em relação ao comportamento sem expansão de ID, porque neste caso, não há correspondência de `ID-DEVICES`. Agora, `AAID` corresponde nas cinco primeiras linhas.
