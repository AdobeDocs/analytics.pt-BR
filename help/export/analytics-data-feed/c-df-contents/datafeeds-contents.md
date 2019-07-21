---
description: Esta seção descreve os arquivos encontrados na entrega do feed de dados.
keywords: Feed de dados; tarefa; conteúdo; manifest; arquivo; pesquisa; dados de ocorrência; conteúdo de entrega
seo-description: Esta seção descreve os arquivos encontrados na entrega do feed de dados.
seo-title: 'Conteúdo do feed de dados: visão geral'
solution: Analytics
subtopic: feed de dados
title: 'Conteúdo do feed de dados: visão geral'
topic: Reports and Analytics
uuid: 82 a 86314-4841-4133-a 0 dc -4 e 7 c 6 cd 14 fc 1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# Conteúdo do feed de dados: visão geral

Esta seção descreve os arquivos encontrados na entrega do feed de dados.

## Arquivo manifest {#section_044BBDE2906D49518F8264CD4832D429}

O arquivo manifest contém os detalhes a seguir sobre cada arquivo que faz parte do conjunto de dados carregado:

* nome do arquivo
* tamanho do arquivo
* hash MD5
* número de registros contidos no arquivo

O arquivo manifest segue o mesmo formato de um arquivo manifest Java JAR.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. Os arquivos manifest são nomeados de acordo com os seguintes itens:

```
<report_suite_id>_YYYY_MM_DD.txt
```

Um arquivo manifest comum contém dados como os seguintes:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Todo arquivo manifest contém um cabeçalho, que indica o número total de arquivos de pesquisa, arquivos de dados e o número total de registros em todos os arquivos de dados. Esse cabeçalho é seguido por várias seções com informações de cada arquivo incluído na entrega do feed de dados.

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Arquivos de pesquisa {#section_B5863537A48D47D78D0F7274838923C1}

Arquivos de pesquisa não possuem dados do hit, são arquivos complementares que fornecem os cabeçalhos das colunas para os dados do hit e arquivos de pesquisa para converter as IDs encontradas no feed de dados para valores reais. Por exemplo, um valor de "497" na coluna do navegador indica que o hit veio do "Microsoft Internet Explorer 8".

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. Outros arquivos, como `browser.tsv`, são genéricos.

Os arquivos de pesquisa são entregues em conjunto em um zip compactado, o qual é nomeado de acordo com os seguintes itens:

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
```

* [!DNL column_headers.tsv] (personalizado para este feed de dados)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (personalizado para este feed de dados)

## Arquivos de dados de hit {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. A quantidade de dados nesse arquivo é determinada pelo formato de entrega (por hora ou por dia e, ainda, em único arquivo ou vários arquivos). Esse arquivo contém somente os dados de hit. Os cabeçalhos da coluna são entregues separadamente com os arquivos de pesquisa. Cada linha desse arquivo contém uma única chamada de servidor.

## Conteúdo da entrega {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>Os arquivos são codificados usando o ISO -8859-1.

Os arquivos reais entregues pela Adobe variam com base no tipo de feed de dados configurados. Encontre a configuração que corresponde ao feed de dados na tabela a seguir para obter uma descrição dos arquivos entregues.

A hora (HHMMSS) indicada em um nome de arquivo sempre indica o início do intervalo de datas para os dados no arquivo, independentemente de quando o arquivo foi produzido ou carregado.

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato de entrega </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Por dia, único arquivo </td> 
   <td colname="col2"> <p>Depois que os dados do dia são coletados, você recebe uma entrega com os seguintes itens: </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">Um único arquivo de dados compactado. </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">Um arquivo manifest. </li> 
    </ul> <p>O arquivo de dados é entregue com o seguinte nome: </p> 
    <code>&lt; report_ suite &gt;_ &lt; YYYY-mm-dd &gt;.&lt;compression_suffix&gt;
    </code> <p> Em que <code>&lt;compression_suffix&gt;</code> é <code>tar.gz</code> ou <code>zip</code>. </p> <p>Quando extraído, o arquivo de dados contém um único arquivo <span class="filepath">hit_data.tsv</span> com todos os dados do dia, bem como os arquivos de pesquisa compactados descritos acima. </p> <p>O tamanho do arquivo de dados de hit varia muito dependendo do número de variáveis usadas ativamente e da quantidade de tráfego no conjunto de relatórios. Contudo, em média, uma linha de dados tem aproximadamente 500 B (compactada) ou 2 KB (descompactada). Multiplicar isso pelo número de chamadas de servidor pode fornecer uma estimativa aproximada do tamanho que um feed de dados terá. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Por dia, vários arquivos </td> 
   <td colname="col2"> <p>Depois que os dados do dia são coletados, você recebe uma entrega com os seguintes itens: </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">Um ou mais arquivos de dados compactados, divididos em partes de 2 GB. </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">Um arquivo manifest. </li> 
    </ul> <p>Cada arquivo de dados é entregue com o seguinte nome: </p> 
    <code>&lt; index &gt;-&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;.&lt;compression_suffix&gt;
    </code> <p> Em que <code>&lt;index&gt;</code> é um índice de arquivo incrementado de <i>1</i> a <i>n</i>, com <i>n</i> arquivos, e <code>&lt;compression_suffix&gt;</code> é <code>tar.gz</code> ou <code>zip</code>. </p> <p>Quando extraídos, cada arquivo de dados possui um único <span class="filepath">hit_data.tsv</span> que contém aproximadamente 2 GB de dados descompactados, bem como os arquivos de pesquisa compactados descritos acima. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Por hora, único arquivo </td> 
   <td colname="col2"> <p>Depois que os dados foram coletados por uma hora, você receberá uma entrega com os seguintes itens: </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">Um único arquivo de dados. </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">Um arquivo manifest. </li> 
    </ul> <p>O arquivo de dados é entregue com o seguinte nome: </p> 
    <code>&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;-&lt; HHMMSS &gt;.&lt;compression_suffix&gt;
    </code> <p> Em que <code>&lt;compression_suffix&gt;</code> é <code>tar.gz</code> ou <code>zip</code>. </p> <p>Quando extraído, o arquivo de dados contém um único arquivo <span class="filepath">hit_data.tsv</span> com todos os dados da hora. Os arquivos de pesquisa compactados descritos acima são entregues somente com os dados da primeira hora de cada dia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Por hora, vários arquivos </td> 
   <td colname="col2"> <p>Depois que os dados foram coletados por uma hora, você receberá uma entrega com os seguintes itens: </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">Um ou mais arquivos de dados compactados, divididos em partes de 2 GB. </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">Um arquivo manifest. </li> 
    </ul> <p>Cada arquivo de dados é entregue com o seguinte nome: </p> 
    <code>&lt; index &gt;-&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;-&lt; HHMMSS &gt;. tsv.&lt;compression_suffix&gt;
    </code> <p>Em que <code>&lt;index&gt;</code> é um índice de arquivo incrementado de <i>1</i> a <i>n</i>, com <i>n</i> arquivos, e <code>&lt;compression_suffix&gt;</code> é <code>gz</code> ou <code>zip</code> </p> <p>Quando extraídos, cada arquivo de dados possui um único <span class="filepath">hit_data.tsv</span> que contém aproximadamente 2 GB de dados descompactados. Os arquivos de pesquisa compactados descritos acima são entregues somente com os dados da primeira hora de cada dia. </p> </td> 
  </tr> 
 </tbody> 
</table>

