---
description: Regras de processamento permitem alterar os dados com base em condições definidas. Quando atributos ou valores corresponderem às condições definidas, os valores poderão ser definidos e excluídos e os eventos poderão ser definidos.
subtopic: Processing rules
title: Como as regras de processamento funcionam
topic: Admin tools
uuid: 19c31f94-c8d8-47b1-97fa-29ed98c94e87
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Como as regras de processamento funcionam

Regras de processamento permitem alterar os dados com base em condições definidas. Quando atributos ou valores corresponderem às condições definidas, os valores poderão ser definidos e excluídos e os eventos poderão ser definidos.

As regras de processamento são aplicadas aos dados conforme são coletadas, e as regras são aplicadas a todos os dados que vêm por meio das bibliotecas do AppMeasurement e por meio da API inserção de dados. As regras de processamento também se aplicam às fontes de dados totais e de log. Essas fontes contêm dados que representam uma  *`hit`* ou uma ação que um usuário toma. Regras de processamento não se aplicam a outras fontes de dados.

## Conceitos importantes {#section_EB138775E7C64C74B0D1D3213F7A823C}

A tabela a seguir contém os principais conceitos de que você precisa compreender ao usar regras de processamento:

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Conceito </p> </th> 
   <th colname="col2" class="entry"> <p>Detalhes </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>As regras se aplicam a um único conjunto de relatórios. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Cópia das regras de processamento para outro conjunto de relatórios </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regras de processamento são aplicadas na ordem em que estão relacionadas. </p> </td> 
   <td colname="col2"> <p>Se uma ação alterar um valor, as condições subsequentes usarão o novo valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Depois de salvas, as regras de processamento são aplicadas imediatamente ao conjunto de relatórios. </p> </td> 
   <td colname="col2"> <p>As alterações das regras de processamento devem estar visíveis no conjunto de relatórios minutos após terem sido salvas. Ao testar as regras de processamento, recomendamos configurar  <a href="/help/admin/admin/realtime/t-realtime-admin.md"> Relatórios em tempo real</a> no conjunto de relatórios de teste, para que você possa visualizar rapidamente os resultados de uma regra de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regras de processamento são o único modo de acessar variáveis de dados de contexto. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiar uma variável de dados de contexto para uma eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regras de processamento são aplicadas antes das regras VISTA e das regras de Canal de marketing. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md"> Ordem de processamento </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ocorrências não podem ser excluídas. </p> </td> 
   <td colname="col2"> <p>É possível usar regras VISTA para excluir ocorrências. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sequência de caracteres de produto, referenciador e agente de usuário não podem ser alterados. </p> </td> 
   <td colname="col2"> <p>Referenciador e agente de usuário são somente leitura. A string do produto não fica disponível. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atributos e classificações de dispositivos móveis não ficam disponíveis. </p> </td> 
   <td colname="col2"> <p>A pesquisa de dispositivos móveis ocorre antes das regras de processamento, mas os atributos não ficam disponíveis nas regras de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Não é possível ler os parâmetros da sequência de consulta após os primeiros 255 caracteres de um URL se você estiver executando o JavaScript AppMeasurement H.25.2 ou versão anterior. O JavaScript AppMeasurement H.25.3 e versão posterior fornece o URL completo, incluindo todos os parâmetros da cadeia de caracteres de consulta para regras de processamento. </p> </td> 
   <td colname="col2"> <p>Atualização para H.25.3 ou versão posterior, ou leitura dos parâmetros da sequência de consulta de URLs longos do lado do cliente e valores de armazenamento nas variáveis de Dados de contexto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os valores de sequência de consulta precisam estar codificados em unicode ou UTF-8 para serem lidos pelas regras de processamento. </p> </td> 
   <td colname="col2"> <p>Isso pode afetar os caracteres com vários bytes passados por strings de consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Você está limitado a 150 regras, com 30 condições cada, para cada conjunto de relatórios. </p> </td> 
   <td colname="col2"> <p>Os limites da regra de processamento são por conjunto de relatórios, e não por empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>As regras de processamento precisam ser configuradas para receber variáveis de dados de contexto antes do envio dos dados. </p> </td> 
   <td colname="col2"> <p>As regras de processamento são aplicadas conforme as chamadas de servidor são enviadas. Os valores armazenados nas variáveis de dados de contexto são descartados se não forem copiados usando as regras de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>As comparações de valores na interface do usuário não distinguem letras maiúsculas de minúsculas. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Limpando valores em um relatório </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Os nomes da variável de dados de contexto podem conter somente caracteres alfanuméricos, sublinhados e pontos. Quaisquer caracteres adicionais são excluídos. </p> </td> 
   <td colname="col2"> <p>Por exemplo, a variável dos dados de contexto <code> login_page-home</code> torna-se automaticamente <code> login_pagehome</code>. Todos os dados enviados para a variável <code> login_page-home</code> são alocados em <code> login_pagehome</code> </p> <p>Não é possível adicionar variáveis de dados de contexto que contenham caracteres não suportados à interface das Regras de processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caret (^) é um caractere especial no sistema de processamento de regras. </p> </td> 
   <td colname="col2"> <p>Para que corresponda a um único caractere caret, use dois caracteres caret (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Condições das regras de processamento  {#section_387390EEE9BA4DA98698522A84326DB4}

As condições verificam as variáveis da página para ver se há um valor correspondente ou se um valor está presente. Várias condições podem ser adicionadas e você pode selecionar se todas as condições precisam ser satisfeitas.

É possível criar uma regra sem condições para que determinadas ações sempre sejam executadas.

Os valores das variáveis não são verificados automaticamente antes da ocorrência das ações. Por exemplo, Prop1 contém o valor "algo" e eVar1 está vazia. Se você definir Prop1 para ser igual a eVar1, ambos os valores ficarão vazios. Para impedir isso, adicione uma condição para verificar a presença de um valor.

## Ações das regras de processamento  {#section_E2285C9D008442C7BF136E52A9A4CC06}

As ações definem variáveis de página, excluem variáveis de página ou acionam eventos. As ações também podem concatenar valores para exibição em um relatório.

Por exemplo, talvez você queira exibir `category:product` concatenando duas variáveis.
