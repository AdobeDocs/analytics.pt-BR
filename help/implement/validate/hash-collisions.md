---
title: Colisões de hash
description: Descreve o que é uma colisão de hash e como ela pode ocorrer.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 100%

---

# Colisões de hash

A Adobe considera valores prop e eVar como cadeias de caracteres, mesmo se o valor for um número. As cadeias de caracteres podem conter centenas de caracteres ou ser bem curtas. Para economizar espaço, melhorar o desempenho e garantir que tudo esteja dimensionado de maneira uniforme, as cadeias de caracteres não são usadas diretamente no processamento. Em vez disso, um hash de 32 bits ou 64 bits é calculado para cada valor. Todos os relatórios são executados nesses valores com hash, onde cada hash é substituído pelo texto original. Os hash aumentam drasticamente o desempenho dos relatórios do Analytics.

Para a maioria dos campos, a cadeia de caracteres é convertida inteiramente em letras minúsculas (reduzindo o número de valores únicos). Os valores são atribuídos a hashes mensalmente (na primeira vez que são vistos em cada mês). A cada mês, há uma pequena possibilidade de dois valores de variável exclusivos serem atribuídos ao mesmo valor. Isso é conhecido como *colisão de hash*.

As colisões de hash aparecem nos relatórios da seguinte maneira:

* Se você estiver analisando as tendências de valores e observar um pico em cada mês, é provável que seja porque outros valores para aquela variável foram atribuídos a um hash com o mesmo valor sendo observado.
* O mesmo ocorre para segmentos de um valor específico.

## Exemplo de colisão de hash

A probabilidade de colisões de hash aumenta de acordo com o número de valores únicos em uma dimensão. Por exemplo, um dos valores que chegam no final do mês poderia ter o mesmo valor de hash que um valor recebido no início do mês. O exemplo a seguir pode ajudar na compreensão de como esse segmento causa as alterações nos resultados. Suponhamos que a eVar62 recebeu &quot;valor 100&quot; em 18 de fevereiro. O Analytics manterá uma tabela parecida com a seguinte:

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor da cadeia de caracteres eVar62 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valor 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valor 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valor 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

Se você criar um segmento que procura por visitas onde eVar62=&quot;valor 500&quot;, o Analytics determina se &quot;valor 500&quot; contém um hash. Já que o &quot;valor 500&quot; não existe, nenhuma visita é retornada pelo Analytics. Em seguida, em 23 de fevereiro, o eVar62 recebeu o &quot;valor 500&quot;, cujo hash também é 123. A tabela terá a seguinte aparência:

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor da cadeia de caracteres eVar62 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valor 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valor 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valor 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valor 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Quando o mesmo segmento é executado novamente, ele procura pelo hash de &quot;valor 500&quot;, encontra 123, e o relatório retorna todas as visitas que contêm o hash 123. Agora, as visitas que ocorreram em 18 de fevereiro serão incluídas nos resultados.

Essa situação pode causar problemas ao usar o Analytics. A Adobe continua procurando por soluções que para reduzir a probabilidade das colisões de hash no futuro. Para evitar essa situação sugerimos que você encontre maneiras de espalhar os valores únicos entre as variáveis, remova valores desnecessários com regras de processamento ou reduza o número de valores por variável.
