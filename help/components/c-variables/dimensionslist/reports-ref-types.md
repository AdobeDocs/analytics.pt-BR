---
description: Ao rastrear e registrar os sites de referência dos visitantes para cada visita, você pode determinar como os visitantes descobriram o site em cada visita.
title: Tipo de referenciador
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tipo de referenciador

Ao rastrear e registrar os sites de referência dos visitantes para cada visita, você pode determinar como os visitantes descobriram o site em cada visita.

A lista abaixo define os diversos tipos de referenciadores:

**Outros sites da Web**: Referenciadores de outros sites são registrados quando os visitantes clicam em um link localizado em uma página em outro site (não definida como parte do seu site) e chegam ao seu site.

**Mecanismos de busca**: referenciadores de mecanismo de busca são registrados quando os visitantes usam um mecanismo de pesquisa para acessar site. O valor de referência deve ser considerado pela Adobe como um mecanismo de pesquisa, não podendo ser um subdomínio que não é considerado um mecanismo de pesquisa (por exemplo, [!DNL mail.yahoo.com] não é um mecanismo de pesquisa, visto que seu domínio é usado para email).

**[!UICONTROL Redes sociais]**: o valor de referência deve ser considerado pela Adobe como uma rede social. Ver a [Lista de redes sociais](https://helpx.adobe.com/br/analytics/kb/list-social-networks.html).

**Email**: Um domínio de referência é considerado um email quando os visitantes clicam em um link de mensagem por email com o protocolo [!DNL imap://] ou [!DNL mail://] e chegam ao seu site. Por exemplo, qualquer item vindo de [!DNL https://mail.yahoo.com] não é contado como um referenciador de email porque o protocolo é [!DNL https://]. Emails do Outlook são indicados na linha Digitado/Marcado, enquanto qualquer referenciador com um protocolo HTTP, onde o domínio é um mecanismo de pesquisa conhecido, é indicado na linha Mecanismo de pesquisa.

**Digitados/marcados**: os referenciadores são registrados quando os visitantes digitam o URL do seu site diretamente no navegador, ou se acessam seu site selecionando marcadores. Dispositivos móveis relatam um tipo de referenciador de *`typed/bookmarked`*, se não houver referenciador na primeira ocorrência da visita.

**[!UICONTROL No seu site]**: Estes itens são URLs marcadas pelos filtros internos do URL. Isso não é contado como *`referrer instances`*, mas pode ser visualizado quando relatado em outras métricas.

## Tipos de referenciadores por interface {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics de marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Análise ad hoc </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tipos de referenciador relatados </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">Outros sites da Web </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> Mecanismos de pesquisa </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Digitado/Marcado </li> 
    </ul> <p> Este relatório exibe apenas duas métricas predefinidas: Instâncias e Visitantes únicos. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Outros sites da Web </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Mecanismos de pesquisa </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Digitado/Marcado </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Outros sites da Web </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Mecanismos de pesquisa </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Digitado/Marcado </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> Por dentro de seu site </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Notas {#section_B83A3571D64E4E7792712FAF740D7955}

* O referenciados, tipo de referenciador e domínio do mesmo estão definidos na primeira ocorrência de uma visita, ou durante uma visita quando o referenciador for externo (por exemplo, se um visitante sair do seu site, usar o mecanismo de busca e retornar ao site antes que a primeira visita expire). Esses valores estão definidos ao mesmo tempo e persistem em toda a visita.
* Nem todos os tipos de referenciadores estão listados nesse relatório. Isso significa que as Visitas de todo o site não correspondem às visitas neste relatório.

## Histórico de relatórios  {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Data | Alterar |
|---|---|
| 1/16/2014 | Data warehouse foi atualizado para corresponder à lógica usada e Reports &amp; Analytics de marketing. Antes dessa data, o tipo de referenciador não persistiu durante a visita. |

