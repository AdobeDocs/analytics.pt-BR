---
description: A Adobe exige um aviso prévio para novas configurações da conta, picos e aumento de tráfego. O hardware deve ser alocado antes para minimizar a latência e os possíveis problemas no sistema geral.
title: Tempo de lead necessário para aumentos de tráfego
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 726e5ee71be60838e48bb682d7fd48bfc1f96ec3
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# Tempo de lead necessário para aumentos de tráfego

A Adobe exige um aviso prévio para novas configurações da conta, picos e aumento de tráfego. O hardware deve ser alocado antes para minimizar a latência e os possíveis problemas no sistema geral.

>[!IMPORTANT]
>
> A Adobe não pode acomodar solicitações de alteração de tráfego de &quot;espaço reservado&quot;. Salvo indicação contrária, siga ao máximo o lead time sugerido, incluindo não enviar um alerta muito cedo.

Use as diretrizes a seguir para determinar com quanta antecedência você deve enviar um alerta de tráfego:

## Prazo para alocação do hardware


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo de alteração de tráfego </th>
   <th colname="col2" class="entry"> Tempo de espera necessário </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Nova configuração de conta </td>
   <td colname="col2"> <ul><li>3 dias úteis</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Pico de tráfego ou aumento repentino do tráfego permanente de até 25% em volume diário médio em comparação com os últimos 30 dias</td>
   <td colname="col2"> <ul><li>Conjuntos de relatórios com &lt; 100 milhões de ocorrências/dia: nenhuma notificação necessária</li><li>Conjuntos de relatórios com &gt; 100 milhões de ocorrências/dia: 5 dias úteis</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Pico de tráfego ou aumento súbito de tráfego permanente superior a 25% em volume diário médio em comparação com os últimos 30 dias</td>
   <td colname="col2"> <ul><li>5 dias úteis</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Eventos de feriado de outubro a dezembro </td>
   <td colname="col2"> <ul><li>Um mês</li></ul> </td>
  </tr>
 </tbody>
</table>

Outros itens que devem ser considerados:

* Se você tiver vários conjuntos de relatórios começando a aumentar que sejam somados aos números listados acima, o lead time é aplicado como o total do tráfego previsto para cada um deles.
* Tenha as seguintes informações em mãos ao enviar uma alteração de tráfego:

   * ID do conjunto de relatórios
   * Estimativa de ocorrências por dia
   * Data de ativação

* Os Alertas do cliente também são necessários quando o tráfego é reduzido ou um conjunto de relatórios é substituído.

## Cancelamento da alocação de hardware devido ao tráfego não realizado

O hardware para novas contas, picos de tráfego e aumentos de tráfego terá o alocamento cancelado se o tráfego projetado no alerta do cliente não ocorrer em 4 semanas a partir da &quot;data de ativação&quot;. Se o tráfego ainda for antecipado, é necessário gerar um novo alerta do cliente conforme o tráfego aumentar.
