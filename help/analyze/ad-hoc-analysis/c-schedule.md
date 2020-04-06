---
description: Você pode personalizar o agendamento do delivery para relatórios. Você pode interromper o delivery em um determinado momento ou especificar o número de vezes que deseja enviar um relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendá-lo para execução diária, você receberá um relatório para os últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático a partir do calendário, você verá o mesmo relatório toda vez que ele for enviado.
title: Gerenciador de programação
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gerenciador de programação

Você pode personalizar o agendamento do delivery para relatórios. Você pode interromper o delivery em um determinado momento ou especificar o número de vezes que deseja enviar um relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendá-lo para execução diária, você receberá um relatório para os últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático a partir do calendário, você verá o mesmo relatório toda vez que ele for enviado.

## Gerenciador de programação {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Você pode personalizar o agendamento do delivery para relatórios. Você pode interromper o delivery em um determinado momento ou especificar o número de vezes que deseja enviar um relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendá-lo para execução diária, você receberá um relatório para os últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático a partir do calendário, você verá o mesmo relatório toda vez que ele for enviado.

>[!NOTE] quando uma conta de usuário é desativada, qualquer entrega agendada de relatório que tenha sido criada por esse usuário é suspensa.

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>A Ad Hoc Analysis permite definir e programar relatórios para necessidades de relatórios ad hoc, pontuais e específicas rapidamente. Ele não foi projetado para exportações completas de dados com um grande número de linhas, colunas, avaliações de métricas ou detalhamentos extensos usando extrações de dados.
>
>As restrições práticas para o relatórios programado na Análise Ad Hoc são baseadas neste princípio: Se seu relatório não for criado dentro de dez minutos (o tempo limite para a Análise ad hoc), é provável que seu relatório seja muito complexo.
>
>Provavelmente, seu relatório tem muitas métricas, muitos detalhamentos de elementos de dimensão, muitas linhas ou colunas, ou outros extremos que fazem dele um processo de geração de relatório muito longo para a Análise ad hoc. Esse tipo de relatório precisa ser executado no Data Warehouse, um recurso do Adobe Analytics criado para uma extração completa de dados que está sendo executada offline com geração de relatórios que pode levar várias horas ou dias.
>
>Por exemplo, a Análise Ad Hoc pode lidar com 50.000 linhas de dados, mas detalhar esses dados para dez tipos de navegador significa 50.0000 vezes 10, um aumento exponencial que pode ser muito complexo para uma ferramenta de relatórios ad hoc. Análises adicionais aumentam novamente as linhas de dados exponencialmente. Não é possível definir o número real de linhas, colunas e detalhamentos para restringir o relatórios de Análise ad hoc em termos drásticos, mas é uma combinação de todos esses fatores.

## Programar um relatório para entrega {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Etapas que descrevem como agendar um relatório para entrega.

<!-- 

t_schedule_delivery.xml

 -->

1. Clique em **[!UICONTROL Tools]**, em seguida, clique em **[!UICONTROL Schedule Manager]**.
1. Na página [!UICONTROL Schedule Manager], clique em **[!UICONTROL New.]**

## Opções de Entrega - Definições {#reference_CA49AC560258471AAE959BCA243F170C}

Definições para as configurações em Opções de Delivery.

<!-- 

r_delivery_options.xml

 -->

Você pode enviar suas informações, conforme exibido no relatório selecionado no momento, para o formato selecionado. Você pode enviá-lo uma vez ou configurar um agendamento de delivery e especificar o formato de arquivo preferido. Você pode criar e enviar uma assinatura digital para garantir ao receptor do arquivo que ele é autêntico. Você pode enviar o arquivo para um endereço de email ou carregá-lo para um servidor FTP.

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
   <td colname="col2"> <p>Informa a ID do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato do arquivo </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Gera seu relatório em uma planilha, incluindo todas as imagens. Editável no Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Gera seu relatório em Valores separados por vírgula. Editável em um editor de texto simples (como o Bloco de notas) ou em um editor de planilhas (como o Excel). Não contém imagens. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Gera seu relatório no formato Portable Documento. Não editável e visualizável no Adobe Acrobat ou Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Gera seu relatório em um anexo de Linguagem de marcação de hipertexto. Esse formato é o composto pela maioria dos sites. Não é editável, a menos que você esteja familiarizado com o código HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: Gera seu relatório no formato Rich Text, incluindo todas as imagens. Editável no Microsoft Word ou no WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avançado </p> </td> 
   <td colname="col2"> <p> Consulte <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >Configurações avançadas de formatação</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destino do arquivo </p> </td> 
   <td colname="col2"> <p>Email: Configurações para enviar por email. </p> <p>FTP: Configurações para fazer upload em um servidor FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de relatórios e agendamento de Delivery </p> </td> 
   <td colname="col2"> <p>Especifica quando entregar o relatório. Os novos agendamentos usam o intervalo de datas definido no relatório. Por exemplo, se você criar um relatório para os últimos 90 dias e agendá-lo para execução diária, você receberá um relatório para os últimos 90 dias a cada dia. Se você criar um relatório com um intervalo de datas estático a partir do calendário, você verá o mesmo relatório toda vez que ele for enviado. </p> </td> 
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
   <td colname="col2"> <p>Anexa automaticamente a ID do relatório ao nome do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Anexar data ao nome do arquivo </p> </td> 
   <td colname="col2"> <p> Anexa automaticamente a data do relatório ao nome do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Idioma </p> </td> 
   <td colname="col2"> <p> Permite selecionar um idioma para o relatório. Você pode enviar o relatório em qualquer um dos seguintes idiomas, independentemente do idioma usado </p> 
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
   <td colname="col1"> <p> Enviar relatório como um arquivo compactado </p> </td> 
   <td colname="col2"> <p> Comprime o arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar arquivo de assinatura digital </p> </td> 
   <td colname="col2"> <p>Cria uma assinatura digital para enviar com o email. </p> </td> 
  </tr> 
 </tbody> 
</table>

