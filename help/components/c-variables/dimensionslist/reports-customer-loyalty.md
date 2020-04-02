---
description: A Fidelidade do cliente exibe os padrões de compra dos clientes.
title: Fidelidade do Cliente
topic: Reports
uuid: 7dc30b57-7b18-4228-a6ab-6eb66b3d9402
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fidelidade do Cliente

A Fidelidade do cliente exibe os padrões de compra dos clientes.

O relatório exibe os padrões de compra dos clientes com base em quatro categorias de fidelidade:

* Não é um cliente
* Novo cliente
* Cliente Recorrente
* Cliente fidelizado

Embora as métricas de não-compra seja visualizadas neste relatório (tais como eventos personalizados, eventos de carrinho de compras e assim por diante), as categorias são sempre baseadas no número de pedidos colocados. Por exemplo: um visitante pode adicionar um evento personalizado intitulado Buscas Internas ao relatório. O item de linha [!UICONTROL Cliente recorrente] mostraria o número de pesquisas internas realizadas por visitantes que já fizeram duas compras, não o número de visitantes que fizeram duas pesquisas internas.

**Processamento de fidelidade do cliente**

As tabelas a seguir definem como a Analysis Workspace, o Reports &amp; Analytics, a Ad Hoc Analysis e o Data Warehouse processam atualmente a Fidelidade do cliente:

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Após 19 de maio de 2016 </p> </th> 
   <th colname="col3" class="entry"> <p>Entre 21 de abril e 19 de maio de 2016 </p> <p>(não aplicável ao Data Warehouse) </p> </th> 
   <th colname="col4" class="entry"> <p>Antes de 21 de abril de 2016 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Não é um cliente </p> </td> 
   <td colname="col2"> <p>Visitantes que nunca compraram </p> </td> 
   <td colname="col3"> <p>Visitantes que efetuaram zero compra até o final de uma visita. </p> </td> 
   <td colname="col4"> <p>Não disponível. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Novo cliente </p> </td> 
   <td colname="col2"> <p>Visitantes que efetuaram uma só compra </p> </td> 
   <td colname="col3"> <p>Visitantes que efetuaram uma compra até o final de uma visita. </p> <p>(Se tiver havido compra, o status do cliente aparecerá atualizado na visita seguinte à compra.) </p> </td> 
   <td colname="col4"> <p>Visitantes que efetuaram zero compra até o final dessa visita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente recorrente </p> </td> 
   <td colname="col2"> <p>Visitantes que efetuaram duas compras </p> </td> 
   <td colname="col3"> <p>Visitantes que efetuaram duas compras até o final da visita que gerou a segunda compra. </p> <p>(Se tiver havido compra, o status do cliente aparecerá atualizado na visita seguinte à compra.) </p> </td> 
   <td colname="col4"> <p>Visitantes que efetuaram uma compra até o final da visita que gerou essa compra. </p> <p>(Se tiver havido compra, o status do cliente aparecerá atualizado na visita seguinte à compra.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente fidelizado </p> </td> 
   <td colname="col2"> <p>Visitantes que efetuaram mais de três compras </p> </td> 
   <td colname="col3"> <p>Visitantes que efetuaram mais de três compras até o final da visita que gerou a compra mais recente. </p> <p>(Se tiver havido compra, o status do cliente aparecerá atualizado na visita seguinte à compra.) </p> </td> 
   <td colname="col4"> <p>Visitantes que efetuaram mais de duas compras até o final da visita que gerou a compra mais recente. </p> <p>(Se tiver havido compra, o status do cliente aparecerá atualizado na visita seguinte à compra.) </p> </td> 
  </tr> 
 </tbody> 
</table>

| Fidelidade do cliente na versão 14 (Atual) |
|---|
| Novo cliente | 1 visita e 1 compra |
| Cliente recorrente | Mais de 1 visita e 2 compras |
| Cliente fidelizado | Mais de 1 visita e mais de 3 compras |

O estado de fidelização imediatamente se altera após o evento de compra dentro da mesma visita. Por exemplo, um novo cliente (1 compra) realiza uma compra e se registra em um boletim informativo na mesma visita após a compra. O evento de cadastramento de newsletter é considerado uma interação de Retorno de Cliente, pois o estado de fidelidade do cliente visitante foi alterado imediatamente após a compra.
