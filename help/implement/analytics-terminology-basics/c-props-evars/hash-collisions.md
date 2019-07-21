---
description: Descreve o que é uma colisão de hash e como ela pode ocorrer.
keywords: Implementação do Analytics; hash; colisão; prop; evar; hash
seo-description: Descreve o que é uma colisão de hash e como ela pode ocorrer.
seo-title: Colisões de hash
solution: Analytics
title: Colisões de hash
topic: Desenvolvedor e implementação
uuid: 7 dfd 6 e 64-4 a 62-4087-bc 28-fb 867 ec 2 b 1 b 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Colisões de hash

Descreve o que é uma colisão de hash e como ela pode ocorrer.

Por padrão, a Adobe considera valores prop e eVar como cadeias de caracteres, mesmo se o valor for um número. As cadeias de caracteres podem conter centenas de caracteres ou ser bem curtas. Para economizar espaço, melhorar o desempenho e garantir que tudo esteja dimensionado de maneira uniforme, as cadeias de caracteres não são usadas diretamente nas tabelas de processamento. Em vez disso, um hash de 32 bits ou 64 bits é calculado para cada valor. Todos os relatórios são executados nos valores com hash até que os dados sejam apresentados, o que faz com que cada hash seja substituído pelo texto original. Sem essa compressão, os relatórios podem demorar minutos para serem executados.

Para a maioria dos campos, a cadeia de caracteres é convertida inteiramente em letras minúsculas (reduzindo o número de valores únicos). Os valores são atribuídos a hashes mensalmente (na primeira vez que são vistos em cada mês). A cada mês, há uma pequena possibilidade de dois valores de variável exclusivos serem atribuídos ao mesmo valor de hash. Isso é conhecido como *colisão de hash*.

As colisões de hash aparecem nos relatórios da seguinte maneira:

* Se você estiver analisando as tendências de valores e observar um pico em cada mês, é provável que seja porque outros valores para aquela variável foram atribuídos a um hash com o mesmo valor sendo observado. 
* O mesmo ocorre para segmentos de um valor específico.

<p class="head"> <b>Exemplo de colisão de hash</b> </p>

A probabilidade de colisões de hash aumenta de acordo com o número de valores únicos em uma dimensão (eVar). Por exemplo, um dos valores que chegam no final do mês poderia ter o mesmo valor de hash que um valor recebido no início do mês. O seguinte exemplo pode ajudar na compreensão de como esse segmento causa as alterações nos resultados. Suponhamos que a eVar62 recebeu "valor 100" em 18 de fevereiro. O Analytics manterá uma tabela parecida com a seguinte:

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

Se você criar um segmento que procura por visitas onde eVar62="valor 500", o Analytics determina se "valor 500" contém um hash. Já que o "valor 500" não existe, nenhuma visita é retornada pelo Analytics. Em seguida, em 23 de fevereiro, o eVar62 recebeu o "valor 500", cujo hash também é 123. A tabela terá a seguinte aparência:

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

Quando o mesmo segmento é executado novamente, ele procura pelo hash de "valor 500", encontra 123, e o relatório retorna todas as visitas que contêm o hash 123. Agora, as visitas que ocorreram em 18 de fevereiro serão incluídas nos resultados.

Essa situação pode causar problemas ao usar o Analytics. A Adobe continua procurando por soluções que para reduzir a probabilidade das colisões de hash no futuro. Para evitar essa situação sugerimos que você encontre maneiras de espalhar os valores exclusivos entre as variáveis, remova valores desnecessários com regras de processamento ou reduza o número de valores por variável. 
