---
description: Nem todos os segmentos criados no Construtor de segmentos são compatíveis com o Data Warehouse. Essa tabela lista as funções suportadas.
title: Compatibilidade de segmentos de Data Warehouse
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---


# Compatibilidade de segmentos de Data Warehouse

Nem todos os segmentos criados no Construtor de segmentos são compatíveis com o [!DNL Data Warehouse]. Essa tabela lista as funções suportadas.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>Excluir container</b> </td> 
   <td> Suportado em qualquer nível </td> 
   <td> Suportado somente em casos especiais no nível superior </td> 
  </tr> 
  <tr> 
   <td> <b>Segmentos sequenciais</b> </td> 
   <td> Suportado </td> 
   <td> Não suportado </td> 
  </tr> 
  <tr> 
   <td> <b>AND e OR podem ser combinados sem limites</b> </td> 
   <td> Suportado </td> 
   <td> Algumas limitações. Consulte *observação* abaixo da tabela. </td> 
  </tr> 
  <tr> 
   <td> <b>Contêineres aninhados</b> </td> 
   <td> Suportado </td> 
   <td> Algumas limitações (elas devem reduzir em escopo, por exemplo, visitantes podem conter ocorrências, mas não o contrário) </td> 
  </tr> 
  <tr> 
   <td> <b>Dimensões</b> </td> 
   <td>Arraste e solte uma dimensão no campo <span class="uicontrol">Definições</span> do Construtor de segmentos para descobrir mais sobre a compatibilidade do produto. Por exemplo, essas dimensões são suportadas somente na Analysis Workspace, no Reports &amp; Analytics e na Ad Hoc Analysis: 
    <ul> 
     <li>Servidor de entrada </li> 
     <li>Categoria de entrada </li> 
     <li>Data de entrada </li> 
     <li>Toda a classificação da página de pesquisa </li> 
    </ul> </td> 
   <td> Arraste e solte uma dimensão no campo <span class="uicontrol">Definições</span> do Construtor de segmentos para descobrir mais sobre a compatibilidade do produto. Por exemplo, essas dimensões são suportadas somente no Data Warehouse: 
    <ul> 
     <li>Endereço IP </li> 
     <li>URL da página </li> 
     <li>ID de visitante </li> 
     <li>ID de visitante da Experience Cloud </li> 
    </ul> <p>As seguintes dimensões <b>não podem</b> ser usadas em segmentos do Data Warehouse: </p> 
    <ul> 
     <li>Toda a classificação da página de pesquisa </li> 
     <li>AM/PM </li> 
     <li>Dia do mês </li> 
     <li>Dia da semana </li> 
     <li>Dia do ano </li> 
     <li>Unidade corporativa de entrada </li> 
     <li>Entrada (Todas as dimensões com Entrada, exceto Página de entrada) </li> 
     <li>Saída (Todas as dimensões com Saída, exceto Link de saída e Página de saída) </li> 
     <li>Hierarquia (Todas as dimensões com Hierarquia) </li> 
     <li>Profundidade da ocorrência </li> 
     <li>Tipo de ocorrência </li> 
     <li>Hora Dia </li> 
     <li>Mês do ano </li> 
     <li>Páginas não encontradas </li> 
     <li>Pesquisa paga </li> 
     <li>Trimestre do ano </li> 
     <li>Frequência de Retorno </li> 
     <li>Visitas em única página </li> 
     <li>Tempo antes do evento </li> 
     <li>Tempo gasto na página - Classificado </li> 
     <li>Tempo gasto por visita - Classificado </li> 
     <li>Motivo da desativação do rastreamento </li> 
     <li>Estados dos Estados Unidos </li> 
     <li>Dia da semana/Fim de semana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>Empilhamento de segmentos</b> </td> 
   <td> Suportado </td> 
   <td> Suportado </td> 
  </tr>
  <tr>
    <td><b>Operadores “É igual a um” e “Não é igual a um”</b></td>
    <td>Suportado</td>
    <td>Não suportado</td>
  </tr>
 </tbody> 
</table>

*Observação: o Data Warehouse não oferece suporte a todos os casos de uso de um contêiner`exclusion`ou`without`ao usar`AND/OR`. Ao usar essa combinação, somente os segmentos que podem ser regravados como `A AND NOT B` (ou **incluir essa característica** e **excluir essa característica**) são compatíveis com o Data Warehouse.*
