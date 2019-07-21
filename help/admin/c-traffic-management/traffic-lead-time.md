---
description: A Adobe exige um aviso prévio para novas configurações da conta, picos e aumento de tráfego. O hardware deve ser alocado antes para minimizar a latência e os possíveis problemas no sistema geral.
seo-description: A Adobe exige um aviso prévio para novas configurações da conta, picos e aumento de tráfego. O hardware deve ser alocado antes para minimizar a latência e os possíveis problemas no sistema geral.
seo-title: Lead time necessário para aumentos de tráfego
solution: Analytics
title: Lead time necessário para aumentos de tráfego
topic: Ferramentas administrativas
uuid: aa 3 fb 882-51 b 0-458 f -917 b -7 c 54 d 5659623
translation-type: tm+mt
source-git-commit: e373297bcf1c9ae0f421ed246125204f31c39cc3

---


# Lead time necessário para aumentos de tráfego

A Adobe exige um aviso prévio para novas configurações da conta, picos e aumento de tráfego. O hardware deve ser alocado antes para minimizar a latência e os possíveis problemas no sistema geral.

A alocação de hardware é realizada por alertas emitidos pela interface do usuário dos Reports &amp; Analytics.

> [!IMPORTANT] A Adobe não pode acomodar solicitações de alteração de tráfego de «espaço reservado». Salvo indicação contrária, acesse o lead time sugerido o mais próximo possível, incluindo não enviar um alerta muito cedo. See [Schedule a traffic spike](../../admin/c-traffic-management/t-traffic-schedule-spike.md) or [Specify permanent traffic increase](../../admin/c-traffic-management/t-traffic-permanent.md).

Use as diretrizes a seguir para determinar com quanta antecedência você deve enviar um alerta de tráfego:

## Prazo para alocação do hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Estimativas DIÁRIAS de tráfego (ocorrências) </th>
   <th colname="col2" class="entry"> <p>Lead time necessário (janeiro - outubro) </p> </th>
   <th colname="col3" class="entry"> <p>Lead time necessário (novembro - dezembro) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Até 1.000.000 </td>
   <td colname="col2"> Não requer lead time </td>
   <td colname="col3"> Não requer lead time </td>
  </tr>
  <tr>
   <td colname="col1"> 1,000,000 - 5,000,000 </td>
   <td colname="col2"> Dois dias ÚTEIS </td>
   <td colname="col3" morerows="3"> Todos os aumentos de tráfego direcionados para novembro de December… devem ser enviados até 1 de setembro. Isto proporciona o tempo necessário para que a capacidade adicional para acomodar o tráfego do feriado seja adquirida. </td>
  </tr>
  <tr>
   <td colname="col1"> 5,000,000 - 10,000,000 </td>
   <td colname="col2"> Uma semana </td>
  </tr>
  <tr>
   <td colname="col1"> 10,000,000 - 25,000,000 </td>
   <td colname="col2"> Duas semanas </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Acima de 25.000.000 </p> </td>
   <td colname="col2"> Um ou mais meses </td>
  </tr>
 </tbody>
</table>

Outros itens que devem ser considerados:

* Se você tiver vários conjuntos de relatórios começando a aumentar que sejam somados aos números listados acima, o lead time é aplicado como o total do tráfego previsto para cada um deles.
* Tenha as seguintes informações em mãos ao enviar uma alteração de tráfego:

   * ID do conjunto de relatórios
   * Estimativa de ocorrências por dia
   * Data de ativação

* Os Alertas do cliente também são necessários quando o tráfego é reduzido ou um conjunto de relatórios fica obsoleto.

## Cancelamento da alocação de hardware devido ao tráfego não realizado

O hardware para novas contas, picos de tráfego e aumentos de tráfego terá o alocamento cancelado se o tráfego projetado no alerta do cliente não ocorrer em 4 semanas a partir da "data de ativação". Se o tráfego ainda for antecipado, é necessário gerar um novo alerta do cliente conforme o tráfego aumentar.
