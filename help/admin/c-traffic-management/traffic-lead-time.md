---
description: A Adobe exige aviso prévio para novas configurações de conta, picos de tráfego e aumento de tráfego. O hardware deve ser alocado antecipadamente para minimizar a latência e possíveis impactos adversos no sistema geral.
title: Tempo de lead necessário para aumentos de tráfego
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Tempo de lead necessário para aumentos de tráfego

A Adobe exige aviso prévio para novas configurações de conta, picos de tráfego e aumento de tráfego. O hardware deve ser alocado antecipadamente para minimizar a latência e possíveis impactos adversos no sistema geral.

A alocação de hardware é realizada por alertas emitidos pela interface do usuário do Relatórios e análises.

>[!IMPORTANT] A Adobe não pode acomodar solicitações de alteração de tráfego de &quot;espaço reservado&quot;. Salvo indicação contrária, siga ao máximo o lead time sugerido, incluindo não enviar um alerta muito cedo. Consulte [Agendar um pico de tráfego](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) ou [Especificar aumento permanente de tráfego](/help/admin/c-traffic-management/t-traffic-permanent.md).

Use as seguintes diretrizes para determinar com que antecedência você deve enviar um alerta de tráfego:

## Lead Times de alocação de hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Estimativas diárias de tráfego (ocorrências) </th>
   <th colname="col2" class="entry"> <p>Lead time necessário (janeiro a outubro) </p> </th>
   <th colname="col3" class="entry"> <p>Lead time necessário (novembro a dezembro) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Até 1.000.000 </td>
   <td colname="col2"> Nenhum lead time necessário </td>
   <td colname="col3"> Nenhum lead time necessário </td>
  </tr>
  <tr>
   <td colname="col1"> 1.000.000 - 5.000.000 </td>
   <td colname="col2"> Dois dias ÚTEIS </td>
   <td colname="col3" morerows="3"> Os aumentos de tráfego direcionados para novembro e dezembro devem ser enviados até 1 de setembro. Isto proporciona o tempo necessário para que a capacidade adicional para acomodar o tráfego do feriado seja adquirida. </td>
  </tr>
  <tr>
   <td colname="col1"> 5.000.000 - 10.000.000 </td>
   <td colname="col2"> Uma semana </td>
  </tr>
  <tr>
   <td colname="col1"> 10.000.000 - 25.000.000 </td>
   <td colname="col2"> Duas semanas </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Acima de 25.000.000 </p> </td>
   <td colname="col2"> Um ou mais meses </td>
  </tr>
 </tbody>
</table>

Outros aspectos a serem considerados:

* Se você tiver vários conjuntos de relatórios iniciando ou aumentando que somam aos números listados acima, o lead time se aplica como uma soma do tráfego esperado para cada um deles.
* Tenha as seguintes informações disponíveis para enviar uma alteração de tráfego:

   * ID do conjunto de relatórios
   * Estimativa de ocorrências por dia
   * Data de ativação

* Os Alertas do cliente também são necessários quando o tráfego diminui ou um conjunto de relatórios está obsoleto.

## Cancelamento da alocação de hardware devido ao tráfego não realizado

O hardware para novas contas, picos de tráfego e aumentos de tráfego terá o alocamento cancelado se o tráfego projetado no alerta do cliente não ocorrer em 4 semanas a partir da &quot;data de ativação&quot;. Se o tráfego ainda for antecipado, é necessário gerar um novo alerta do cliente conforme o tráfego aumentar.
