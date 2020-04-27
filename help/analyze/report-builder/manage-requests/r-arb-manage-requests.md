---
description: Descrições dos campos para gerenciar solicitações no Report Builder.
title: Gerenciar solicitações - definições
topic: Report builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gerenciar solicitações - definições

Descrições dos campos para gerenciar solicitações no Report Builder.

## Visão geral {#section_75C288C945FA4781A4EDF806711A5660}

The [!UICONTROL Request Manager] provides a detailed view of the status of all requests you have built for all sheets or just one sheet of the active workbook. You can also add, edit, refresh, and delete a request (functions typically associated with the [!UICONTROL Request Wizard] and [!UICONTROL Request Manager]) by right-clicking on an available cell in the Excel spreadsheet that contains previous requests.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE] O Adobe Report Builder aplica as dependências de solicitação somente na mesma planilha, não entre planilhas. Restringir às dependências em uma única planilha garante a oportunidade da execução.

## Definições {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Todas as planilhas </p> </td> 
   <td colname="col2"> <p>Exibe solicitações de todas as planilhas na pasta de trabalho ativa. Para exibir solicitações de planilhas específicas, desative esta opção. Se você desativar esta opção, deverá clicar em uma guia Planilha na parte inferior do relatório do Excel para exibir as solicitações associadas a essa planilha no <span class="wintitle">Gerenciador de solicitações</span>. O rótulo ao lado da caixa de seleção indica qual planilha da pata de trabalho está em foco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Planilha </p> </td> 
   <td colname="col2"> <p>Exibe o nome das planilhas em uma pasta de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Conjunto de relatórios </p> </td> 
   <td colname="col2"> <p>Exibe o nome do conjunto de relatórios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de datas </p> </td> 
   <td colname="col2"> <p>Exibe o intervalo de datas especificado do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularidade </p> </td> 
   <td colname="col2"> <p>Especifica a granularidade da solicitação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Última execução </p> </td> 
   <td colname="col2"> <p>Especifica a data em que a solicitação foi processada pela última vez no Report Builder. Uma mensagem de diagnóstico também é exibida nesta tabela na coluna <span class="wintitle">Última execução</span>, se aplicável. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adicionar </p> </td> 
   <td colname="col2"> <p>Exibe a caixa de diálogo do Assistente de solicitações. Consulte <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   >Criar uma solicitação de dados</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Editar </p> </td> 
   <td colname="col2"> <p> (Ou Editar várias) Edita uma solicitação selecionada. O sistema exibe a caixa de diálogo <span class="wintitle">Assistente de solicitações</span>. Consulte <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Editar várias solicitações</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Excluir </p> </td> 
   <td colname="col2"> <p>Exclui solicitações. Você pode excluir várias solicitações selecionadas. Também pode excluir uma solicitação na lista selecionando-a e pressionando Del no teclado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Selecionar Todas </p> </td> 
   <td colname="col2"> <p>Seleciona todas as solicitações. O <span class="wintitle">Gerenciador de solicitações</span> exibe o número de solicitações que você selecionou na parte inferior da lista de solicitações. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Da célula </p> </td> 
   <td colname="col2"> <p>Obtém dados para uma solicitação a partir da planilha. Se uma solicitação estiver associada à célula selecionada no momento na planilha ativa, a solicitação associada é selecionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Atualizar </p> </td> 
   <td colname="col2"> <p>Atualiza uma única solicitação ou uma seleção de solicitações. (Consulte <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Atualizar uma solicitação</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Atualizar Lista </p> </td> 
   <td colname="col2"> <p>Atualiza todas as solicitações exibidas. Quando você atualiza todas as solicitações, o tempo que leva para atualizar as informações do servidor no relatório é diretamente proporcional à complexidade das solicitações no relatório. Para relatórios muito grandes, atualizar todas as solicitações pode levar vários minutos. Por isso, você pode querer atualizar as solicitações mais urgentes individualmente e selecionar <span class="wintitle">Atualizar tudo</span> em outro momento menos urgente. </p> <p> <p>Observação: recomenda-se verificar os resultados com frequência no <span class="wintitle">Gerenciador de solicitações</span> se você atualizar uma planilha que contém várias solicitações. Se ocorrer uma falha da solicitação, a mensagem de erro na coluna de diagnóstico ajuda a identificar a fonte do erro. Embora muitas vezes uma mensagem de erro seja exibida quando há falhas de solicitação, observe que, às vezes, nenhuma mensagem é gerada. Você poderá notar que uma atualização não atualiza os dados em uma célula que contém uma referência, ou remove os dados da célula. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

