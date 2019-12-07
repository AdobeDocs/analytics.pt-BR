---
description: Você pode personalizar o agendamento da entrega de relatórios. É possível interromper a entrega em determinado momento ou especificar o número de vezes que você deseja enviar um relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendar sua execução diariamente, você recebe um relatório dos últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático do calendário, você verá o mesmo relatório sempre que ele for enviado.
title: Gerenciador de programação
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gerenciador de programação

Você pode personalizar o agendamento da entrega de relatórios. É possível interromper a entrega em determinado momento ou especificar o número de vezes que você deseja enviar um relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendar sua execução diariamente, você recebe um relatório dos últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático do calendário, você verá o mesmo relatório sempre que ele for enviado.

## Gerenciador de programação {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Você pode personalizar o agendamento da entrega de relatórios. É possível interromper a entrega em determinado momento ou especificar o número de vezes que você deseja enviar um relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendar sua execução diariamente, você recebe um relatório dos últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático do calendário, você verá o mesmo relatório sempre que ele for enviado.

> [!NOTE] quando uma conta de usuário é desativada, qualquer entrega agendada de relatório que tenha sido criada por esse usuário é suspensa.

Para garantir que os itens de linha em um detalhamento sejam persistentes em relatórios salvos e programados, use o recurso **[!UICONTROL Editar itens]** no Criador [de](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) tabela para criar listas de dimensão fixas em detalhamentos.

>[!IMPORTANT]
>
>A Análise ad hoc permite que você defina e programe relatórios rapidamente para necessidades específicas, oportunas e de relatórios ad hoc. Ela não foi criada para exportações completas de dados com um grande número de linhas, colunas, avaliações métricas ou departamento extensivos usando extrações de dados.
>
>As limitações práticas para relatórios programados na Ad Hoc Analysis são baseadas no seguinte princípio: Se o seu relatório não foi criado dentro de dez minutos (o limite para Análises ad hoc), significa que ele provavelmente é muito complexo.
>
>Provavelmente, o seu relatório possui muitas métricas, muitos departamento de elementos da dimensão, muitas linhas ou colunas, ou outros extremos que tornam muito longo o processo de geração do relatório para a Ad Hoc Analysis. Esse tipo de relatório precisa ser executado no Data Warehouse, um recurso do Adobe Analytics criado para a extração completa de dados executada offline, com uma geração de relatórios que pode demorar horas ou dias.
>
>Por exemplo, a Ad Hoc Analysis pode lidar com 50.000 linhas de dados, mas detalhar os dados para dez tipos navegador significa 50.0000 vezes 10, um aumento exponencial que pode ser muito complexo para uma ferramenta de relatório ad hoc. Novamente, divisões adicionais aumentam as linhas de dados exponencialmente. A definição de departamento, colunas, linhas ou números reais para limitar os relatórios da Ad Hoc Analysis não pode ser definida em termos drásticos, mas é uma combinação de todos esses fatores.

## Programar um relatório para entrega {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Etapas que descrevem como agendar um relatório para entrega.

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. No [!UICONTROL Gerenciador de programação]**, clique em[!UICONTROL Novo.]**

## Opções de Entrega - Definições {#reference_CA49AC560258471AAE959BCA243F170C}

Definições para as configurações em Opções de entrega.

<!-- 

r_delivery_options.xml

 -->

Suas informações podem ser enviadas para o formato escolhido do modo que são exibidas no relatório atualmente selecionado. É possível enviá-lo de uma vez ou criar uma programação de entrega, e especificar o formato de arquivo preferido. Você também pode criar e enviar uma assinatura digital para garantir ao destinatário que o arquivo é autêntico. O arquivo pode ser enviado para um endereço de email ou carregado para um servidor FTP.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2"> <p> O nome configurável deste relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Informa o ID do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato do arquivo </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Gera seu relatório em uma planilha, incluindo todas as imagens. Editável no Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Gera seu relatório em Valores separados por vírgula. Editável em um editor de texto simples (como o Bloco de notas) ou em um editor de planilha (como o Excel). Não contém nenhuma imagem. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Gera seu relatório em Portable Document Format. Não é editável e visualizável no Adobe Acrobat ou no Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Gera seu relatório em um anexo em Hypertext Markup Language. Este é o formato do qual a maioria dos sites é composto. Não é editável a não ser que você esteja familiarizado com o código HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: Gera seu relatório em Rich Text Format, incluindo todas as imagens. Editável no Microsoft Word ou no WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avançado </p> </td> 
   <td colname="col2"> <p> See <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destino do arquivo </p> </td> 
   <td colname="col2"> <p>Email: Configurações para enviar por email. </p> <p>FTP: Configurações para carregar em um servidor FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de relatório e Programação de entrega </p> </td> 
   <td colname="col2"> <p>Especifica quando entregar o relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendar sua execução diariamente, você recebe um relatório dos últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático do calendário, você verá o mesmo relatório sempre que ele for enviado. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configurações avançadas de formato - Definições {#reference_F99B65BF7C9746638D8147EED147015B}

Definições para as configurações em Configurações avançadas de formato.

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definição </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome do arquivo </p> </td> 
   <td colname="col2"> <p>Um nome de arquivo definido pelo usuário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anexar ID ao nome de arquivo </p> </td> 
   <td colname="col2"> <p>Anexa automaticamente a ID do relatório ao nome de arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Anexar data ao nome de arquivo </p> </td> 
   <td colname="col2"> <p> Anexa automaticamente a data do relatório ao nome de arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Idioma </p> </td> 
   <td colname="col2"> <p> Permite que você selecione um idioma para o relatório. É possível enviar o relatório em qualquer um dos seguintes idiomas (independentemente do idioma que você usa) </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">Inglês </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">Espanhol </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">Chinês simplificado </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">Chinês tradicional </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">Francês </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">Alemão </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">Japonês </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">Português </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codificação </p> </td> 
   <td colname="col2"> <p>Especifica um tipo de codificação. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Enviar o Relatório como um Arquivo Compactado </p> </td> 
   <td colname="col2"> <p> Comprime o arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar arquivo de assinatura digital </p> </td> 
   <td colname="col2"> <p>Cria uma assinatura digital para enviar por email. </p> </td> 
  </tr> 
 </tbody> 
</table>

