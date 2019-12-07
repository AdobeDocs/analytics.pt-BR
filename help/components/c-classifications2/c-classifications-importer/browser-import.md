---
description: É possível importar (upload) dados de classificações por meio do navegador. Esse método restringe o upload de seus dados de classificação a um único conjunto de relatórios
subtopic: Classifications
title: Importação de navegador
topic: Admin tools
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importação de navegador

É possível importar (upload) dados de classificações por meio do navegador. Esse método restringe o upload de seus dados de classificação a um único conjunto de relatórios

## Importação de navegador {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

É possível importar (upload) dados de classificações por meio do navegador. Esse método restringe o upload de seus dados de classificação a um único conjunto de relatórios

**[!UICONTROL Administração]** &gt; **[!UICONTROL Importador de classificação]**

## Importação do navegador de classificações - Descrições do campo {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Selecione o Conjunto de relatórios </td> 
   <td colname="col2"> <p>O conjunto de relatórios em que deseja importar os dados de classificações. O arquivo de dados de importação deve corresponder ao formato do conjunto de dados no conjunto de relatórios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conjunto de dados a ser classificado </td> 
   <td colname="col2"> <p>O conjunto de dados que receberá as classificações. A lista suspensa inclui todos os relatórios em seus conjuntos de relatórios configurados para classificação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Selecionar o arquivo para importar </td> 
   <td colname="col2"> <p>Permite navegar para localizar o arquivo de dados de importação que deseja fazer upload. </p> <p>Observação: o tamanho do arquivo para upload é de 1 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Substituir dados em conflito </td> 
   <td colname="col2"> <p>Substitui automaticamente dados existentes que estejam em conflito com os dados importados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fazer download automático do arquivo de classificação após a importação ser concluída </td> 
   <td colname="col2"> <p>Faz o download automático de um arquivo delimitado por tabulação que representa o conjunto de dados com os dados de classificações carregados recentemente. A Adobe gera este arquivo automaticamente para você se a importação criar IDs exclusivas ou se ocorrerem erros. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Importar classificações pelo navegador {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Clique em **[!UICONTROL Administração]** &gt; **[!UICONTROL Importador de classificação]**.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Configure os campos **[!UICONTROL Importação de navegador]**.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Observe as mensagens de processamento na janela de status.
1. (Condicional) Se você selecionou **[!UICONTROL Baixar automaticamente o arquivo de classificação quando a importação estiver concluída]**, especifique onde deseja armazenar o arquivo resultante depois que o processamento terminar.
>Uma importação bem-sucedida exibe imediatamente as alterações apropriadas em uma exportação. No entanto, as alterações de dados nos relatórios levam até quatro horas quando se usa uma importação de navegador e até 24 horas quando se usa uma importação FTP.

