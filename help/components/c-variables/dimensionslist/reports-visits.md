---
description: Exibe o número de visitas realizadas em todo o site durante um período especificado.
seo-description: Exibe o número de visitas realizadas em todo o site durante um período especificado.
seo-title: Visitas
solution: Analytics
title: Visitas
topic: 'Relatórios  '
uuid: ff 65 bddf-fb 65-4 cf 0-8 aae -4 ab 59 c 2 bb 0 a 7 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visitas

Exibe o número de visitas realizadas em todo o site durante um período especificado.

**Propriedades de relatório**

* Uma visita é definida como uma sequência de exibições de página consecutivas sem um intervalo de 30 minutos, ou atividade contínua por 12 horas.
* Após uma visita expirar, uma nova visita é iniciada em qualquer solicitação de imagem subsequente.
* Geralmente, um visitante representa, no mínimo (mas provavelmente mais de uma), uma visita.
* O início de uma visita é a primeira solicitação de imagem vinda de um novo visitante, ou depois que uma visita de usuário existente expirar. Isso pode ser identificado como uma Página de Entrada.
* O final de uma visita é a última solicitação de imagem antes de uma visita expirar. Isso pode ser identificado como uma Página de Saída.

   Consulte [Relatórios de Entradas e Saídas](../../../components/c-variables/dimensionslist/reports-entries-exits.md#concept_C4AED2C1D62E43A48ACAA837327FCCF2).
* Os detalhamentos por hora são baseados na zona de tempo do conjunto de relatórios.
* Este relatório não contém itens de linha. A visualização só é possível no formato de tendência.
* A granularidade de hora, dia, semana, mês, trimestre e ano pode ser aplicada. Essas configurações de granularidade estão disponíveis dependendo do intervalo de datas informado.

Consulte [Acesse Métrica](../../../components/c-variables/c-metrics/metrics-visit.md#concept_9DA4D9EF8B964755BAC57378AD37911E) para obter mais informações sobre como a Experience Cloud processa essa métrica.

**Informações de Relatório Específico do Produto**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Produto </th> 
   <th colname="col2" class="entry"> Navegação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Métricas do site</span> &gt; <span class="uicontrol">Visitas</span> </p> <p>Você pode executar o <span class="wintitle">Relatório de visitas</span> na página selecionada. Visitas abrangendo além da meia-noite são contadas em ambos os dias em que a visita começou e terminou. No entanto, o total para esse intervalo de datas é desduplicado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Relatórios</span> &gt; <span class="uicontrol">Métricas do site</span> &gt; <span class="uicontrol">Visitas</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> Você pode dividir cada item neste relatório por quase todos os outros relatórios e variáveis, permitindo que você visualize os detalhamentos por qualquer granularidade. </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">Visitas abrangendo além da meia-noite são contadas em ambos os dias em que a visita começou e terminou. No entanto, o total para esse intervalo de datas é desduplicado. </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">Você pode utilizar todas as métricas de conversão e tráfego neste relatório, bem como utilizar alocação diferente para todas as métricas de conversão. </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">Este relatório pode usar múltiplos segmentos altamente avançados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

