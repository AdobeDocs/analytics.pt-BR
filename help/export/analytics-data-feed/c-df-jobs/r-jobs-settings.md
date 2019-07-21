---
description: Ao configurar um feed, algumas configurações determinam a frequência com que as tarefas são processadas.
keywords: Feed de dados; tarefa; configurações; diariamente; por hora; Preenchimentos retroativos de dados para feeds de dados por hora; preenchimento retroativo
seo-description: Ao configurar um feed, algumas configurações determinam a frequência com que as tarefas são processadas.
seo-title: Configurações de tarefas
solution: Analytics
title: Configurações de tarefas
uuid: e 124 b 4 f 1-0168-4 eaa -8657-19207 b 2 f 263 f
translation-type: tm+mt
source-git-commit: b6169d2febded32d772f82d5917b1132695ab442

---


# Configurações de tarefas

Quando um feed é configurado, algumas configurações determinam a frequência com que as tarefas são processadas.

Use as configurações a seguir para configurar os tempos de processamento da tarefa. Essas configurações estão programadas no nível do feed, não no da tarefa.

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Diariamente </td> 
   <td colname="col2"> <p>Os dados para cada dia são entregues em um único arquivo zipado. Esse arquivo tem um limite de tamanho de 2GB. Se o arquivo tem dados não compactados maiores que 2GB, são criados arquivos adicionais. Você recebe uma única entrega de todos os arquivos para cada dia. </p> <p>Cada arquivo é nomeado no seguinte formato: </p> <p> <span class="filepath"><span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Por hora (Padrão) </td> 
   <td colname="col2"> <p>Os dados de cada hora são entregues em um único arquivo zipado que contém todos os dados recebidos durante a hora. Você recebe 24 entregas diferentes a cada dia, e cada arquivo é entregue depois que os dados daquela hora tiverem sido processados. </p> <p>O termo “por hora” descreve o período em que os dados são enviados em cada exportação de dados individual, e não o período em que ocorre a entrega. Os feeds de dados horários são processados e entregues da melhor forma. </p> <p>Nos feeds de dados por hora, a expectativa é de que em 95% das vezes o feed entregará dentro de 12 horas do término dos dados referentes à hora. Feed de dados para conjuntos de relatórios com alto volume de tráfego podem demorar mais para processamento e entrega. </p> <p>Receber um feed de dados por hora é diferente de receber feeds diários com entrega de vários arquivos. Ao receber feeds de dados por hora, os dados de cada dia são divididos em 24 arquivos com base nos dados coletados durante cada hora, e cada arquivo é entregue assim que é disponibilizado. Um feed diário entregue em vários arquivos é entregue uma vez por dia depois que os dados do dia anterior tiverem sido processados e é dividido em incrementos de 2 GB com base na quantidade de dados coletados. </p> <p>Cada arquivo é nomeado no seguinte formato: </p> <p> <span class="filepath"><span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> hour</span>.tar</span> </p> <p>Consulte <a href="../../../export/analytics-data-feed/c-df-contents/jobs-faq.md#concept_7C67A012CCF64B0C8DA33E5A6CF7FD9E" format="dita" scope="local">Perguntas frequentes sobre tarefas</a> para informações sobre fatores que podem impactar feeds por hora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Preenchimentos retroativos de dados para feeds de dados por hora </td> 
   <td colname="col2"> <p>Se você solicitar dados para datas anteriores durante a configuração de um novo feed de dados por hora, dados com mais de 60 dias podem ser entregues diariamente em vez de a cada hora. </p> <p>Nesse caso, você não receberá 24 entregas separadas durante esses dias. Em vez disso, você receberá uma única entrega com um carimbo de data/hora de meia-noite, contendo todos os dados do dia. Se você estiver solicitando este tipo de preenchimento retroativo, certifique-se de que seu ETL está configurado para processar entregas diárias. </p> </td> 
  </tr> 
 </tbody> 
</table>

