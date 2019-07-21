---
description: As variáveis e funções a seguir permitem que você armazene chamadas de medição quando o aplicativo está offline.
keywords: Implementação do Analytics
seo-description: As variáveis e funções a seguir permitem que você armazene chamadas de medição quando o aplicativo está offline.
seo-title: Rastreamento offline
solution: Analytics
title: Rastreamento offline
topic: Desenvolvedor e implementação
uuid: f 7 c 55 aef -28 a 4-4 f 2 f -8 f 47-792 a 05 f 9525 b
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Rastreamento offline

As variáveis e funções a seguir permitem que você armazene chamadas de medição quando o aplicativo está offline.

>[!NOTE]
>
>Para ativar o rastreamento offline, o conjunto de relatórios deve estar habilitado para carimbo de data e hora. Se o carimbo de data e hora estiver ativado no conjunto de relatórios, sua propriedade de configuração `trackOffline` *deve* ser verdadeira. Caso o conjunto de relatórios não tenha um carimbo de data e hora, sua propriedade de configuração `trackOffline` *deve* ser false. Se isso não for configurado corretamente, os dados serão perdidos. Se você não tem certeza se um conjunto de relatórios tem um carimbo de data e hora, [entre em contato com o Atendimento ao cliente](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

Quando ativado, o AppMeasurement offline se comporta da seguinte maneira:

* O aplicativo envia uma chamada de servidor, mas a transmissão de dados falha.
* O AppMeasurement gera um registro de data e hora para o hit atual.
* O AppMeasurement armazena os dados do hit em buffer e faz o backup dos dados de hits em buffer no armazenamento persistente para evitar a perda de dados.

Em cada ocorrência subsequente ou no intervalo definido por `offlineThrottleDelay`, o AppMeasurement tenta enviar os dados de ocorrÊncia em buffer, mantendo a ordem de ocorrência original. Caso a transmissão de dados falhe, a armazenagem de dados em buffer continuará (Enquanto o dispositivo estiver offline).

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Propriedade ou método </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>Padrão: falso </p> <p>Ativa ou desativa o rastreamento offline para a biblioteca de medição. </p> <p> <b>Exemplos:</b> </p> 
    <code class="syntax c">s. trackoffline = true; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>Padrão: sem limite </p> <p>O número máximo de ocorrências offline armazenada na fila.  </p> <p> <b>Exemplos:</b> </p> 
    <code class="syntax c">s. offlinehitlimit = 100; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>Padrão: 0 </p> <p>Especifica uma cadência (ou atraso), em milissegundos, para enviar dados de ocorrência armazenados em buffer quando o AppMeasurement detecta uma conexão de rede ativa. Essa ação reduz o impacto no desempenho do envio de várias ocorrências no aplicativo. </p> <p>Por exemplo, se offlineThrottleDelay=1000, e são necessários 300 ms para enviar os dados da ocorrência, o AppMeasurement aguarda 700 ms antes de enviar a próxima ocorrência armazenada em buffer. </p> 
    <code class="syntax c">s. offlinethrottledelay = 1000; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> Define manualmente o estado online ou offline do objeto de medição. A biblioteca detecta automaticamente quando um dispositivo está online ou offline. Estes métodos serão necessários apenas quando você quiser forçar a medição offline. <code> forceOnline</code> é usado para retornar ao estado online após ter sido alterado manualmente para offline. </p> <p>Quando a medição está offline: </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> Se <code>trackOffline</code> for verdadeiro: as ocorrências são armazenadas até a medição estar online. </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> Se <code>trackOffline</code> for falso: as ocorrência são descartadas. </li> 
    </ul> <p> <b>Exemplos:</b> </p> 
    <code class="syntax c">s. forceoffline ();

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
