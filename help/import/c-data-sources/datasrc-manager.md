---
description: Crie, gerencie e visualize o uso de fontes de dados em um conjunto de relatórios.
seo-description: Crie, gerencie e visualize o uso de fontes de dados em um conjunto de relatórios.
seo-title: Gerenciador das Fontes de Dados
solution: Analytics
subtopic: Fontes de dados
title: Gerenciador das Fontes de Dados
topic: Desenvolvedor e implementação
uuid: ccfa 4 a 1 c -7 c 56-421 b -8 ee 6-a 42 b 334659 b 1
translation-type: tm+mt
source-git-commit: 887f48d2ea5f21b7db95a1a8f716f7da9cf43662

---


# Gerenciador das Fontes de Dados

Crie, gerencie e visualize o uso de fontes de dados em um conjunto de relatórios.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Fontes de dados]**.

## Guia Criar {#section_74603FDA3D8842E49F1A51624A06DE20}

A guia [!UICONTROL Criar] permite a configuração de uma nova fonte de dados para o conjunto de relatórios atualmente selecionado. Quando você ativa uma fonte de dados, o [!UICONTROL Assistente das fontes de dados] o orienta ao longo do processo de criação de um modelo de fontes de dados, e cria um local FTP para carregar os dados.

A seleção que você faz na guia Criar determina os campos iniciais do modelo criado. Consulte [Criação de um modelo de arquivo de importação](../../import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md#task_A2F150D9DC1A4D338E878534FA506267).

## Guia Gerenciar {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Opção </p> </th> 
   <th colname="col2" class="entry"> <p>Descrição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Reiniciar Processamento </p> </td> 
   <td colname="col2"> <p>Reinicia o processamento da fonte de dados que havia sido interrompido por erros ou avisos. O processamento continua até que o erro seguinte seja encontrado. As Fontes de dados somente interrompem o processamento do arquivo das Fontes de dados quando você seleciona <span class="uicontrol">Parar o processamento em caso de erros</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Concluir Processamento </p> </td> 
   <td colname="col2"> <p>Instrui as Fontes de Dados a fechar qualquer visita aberta no arquivo e finalizar o processamento do arquivo das Fontes de Dados como se estivesse completo. Isso é útil quando há visitas que abrangem múltiplos arquivos de Fontes de Dados. Isso se aplica somente ao <a href="../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> Processamento completo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desativar </p> </td> 
   <td colname="col2"> <p> A desativação de uma Fonte de Dados a excluirá. Se qualquer arquivo do servidor começou a ser processado, o processamento continuará até ser concluído. Os arquivos que ainda não começaram a ser processados não serão processados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parar o processamento em caso de erros / avisos </p> </td> 
   <td colname="col2"> <p> Instrui o Mecanismo de Processamento das Fontes de Dados a parar o processamento quando encontrar um erro. A fonte de dados não reinicia o processamento até que você selecione Reiniciar o Processamento. A interrupção do processamento no caso de avisos aplica-se apenas ao <a href="../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> Processamento completo</a>. </p> <p>Quando as Fontes de dados encontram um erro de arquivo, elas o notificam do erro. O sistema move o arquivo das Fontes de dados com o erro para uma pasta chamada <span class="filepath">files_with_errors</span> no servidor FTP. Após solucionar o problema, envie novamente o arquivo das Fontes de dados para processamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar </p> </td> 
   <td colname="col2"> <p>Permite modificar o modelo da fonte de dados, ou outras configurações específicas desta fonte de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informações de FTP </p> </td> 
   <td colname="col2"> <p>Exibe as informações de FTP desta fonte de dados. Use essas informações para acessar o modelo da fonte de dados, e envie os dados da Fonte de Dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome do arquivo </p> </td> 
   <td colname="col2"> <p>O nome do arquivo carregado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p> O status atual do arquivo. Os possíveis valores de status incluem: </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">Na fila (etapa 1 de 3): O arquivo existe, mas ainda não começou a ser processado. Se o arquivo não aparecer em 30 minutos, confirme se o arquivo <span class="filepath">.fin</span> associado está presente. </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">Preparando (etapa 2 de 3): O arquivo está sendo verificado em busca de erros ou avisos. </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">Processando (etapa 3 de 3): O arquivo está sendo processado. </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">Falha: O arquivo não foi processado por causa de erros. </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">Êxito: O arquivo foi completamente processado. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Guia Log de arquivo {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

O log de arquivo inclui um mecanismo de pesquisa que permite pesquisar informações por nome da fonte de dados, tipo da fonte de dados, nome do arquivo, data de recebimento ou status.
