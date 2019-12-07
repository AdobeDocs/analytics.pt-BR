---
description: Informações sobre os requisitos do conjunto de relatórios antes de usar as Fontes de dados.
subtopic: Data sources
title: Requisitos e limites de upload
topic: Developer and implementation
uuid: d79fca77-fa0e-4171-b978-cdee5c67d9df
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Requisitos e limites de upload

Informações sobre os requisitos do conjunto de relatórios antes de usar as Fontes de dados.

As seções a seguir apresentam as limitações aplicáveis às Fontes de dados e aos dados importados nos relatórios e análises de marketing.

* [Limites de tamanho](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [Datas](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [Geral](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [Suporte para múltiplos bytes](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [Upload de arquivos de log da Web](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## Limites de tamanho {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* Cada conta FTP é limitada a 50 MB de dados totais para todos os arquivos. O processamento é interrompido se o tamanho exceder 50 MB, e não reinicia até que o total seja inferior a 50 MB.

## Datas {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* Por dia, é possível carregar dados referentes a 90 dias. Se você exceder o limite, o upload será cancelado com uma mensagem de erro informando sobre o excesso do número máximo de dias.
* É possível importar apenas dados com datas atuais ou passadas. Não tente usar datas futuras nos dados de Fontes de dados.
* Todas as linhas devem ter uma data especificada para habilitar os recursos gráficos do relatório. Se uma linha não tiver data, as Fontes de Dados gerarão um erro e rejeitarão o arquivo. O formato da data/hora varia de acordo com o tipo de fonte de dados:

   * **Fontes** de dados de processamento completo:Use o formato de data ISO 8601 de `YYYY-MM-DDThh:mm:ss±UTC_offset` (por exemplo, `2013-09-01T12:00:00-07:00`) ou Formato de hora Unix (o número de segundos decorridos desde 1° de janeiro de 1970).

   * **Fontes** de dados padrão e de integração: Use o seguinte formato de data: `MM/DD/YYYY/HH/mm/SS` (por exemplo, `01/01/2013/06/00/00`)

## Geral {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* Quando você carrega um arquivo de Fontes de dados, as fontes de dados executam uma validação básica de dados ter certeza de que o arquivo não apresenta erros de formatação. Caso seja identificado erro em um arquivo, um email de notificação é enviado e o processamento é interrompido.
* Os campos de dados não podem conter ponto e vírgula. As fontes de dados ignoram os registros que contêm ponto e vírgula. 
* Os dados de log da Web, de tráfego e de alguns grupos de fontes de dados genéricas não estão disponíveis em Data Warehouse ou Discover. Para obter mais informações, consulte [Tipos de dados e categorias](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md).
* As fontes de dados não comportam eventos serializados.

## Suporte de múltiplos bytes {#section_96C8D26B21184C3E839865DB6F23EA22}

As Fontes de Dados oferecem suporte para codificação de múltiplos bytes. As Fontes de Dados tentam identificar o formato do arquivo de Fontes de Dados recebido e, quando necessário, converte-o para um formato compatível. A tabela a seguir apresenta os formatos comuns de caracteres e seu status de suporte.

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato do caractere </th> 
   <th colname="col2" class="entry"> Suporte </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>Suportado. O conjunto de relatórios usado com as fontes de dados deve ter o suporte para caracteres de múltiplos bytes habilitado. </p> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/reference/new_report_suite.html"  >Novo conjunto de relatórios</a> em Ajuda </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 com Byte Order Mark (EF BB BF) </td> 
   <td colname="col2"> <p>Suportado. Embora muitos aplicativos do Windows salvem nesse formato, ele não é padrão. </p> <p>Por exemplo, o WordPad salva nesse formato se você selecionar "UTF-8". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (aka Latin-1 ou Windows-1252) </td> 
   <td colname="col2"> Suportado. O Microsoft Excel salva nesse formato quando você seleciona exportar "delimitado por tabulação". O conjunto de relatórios deve estar usando o formato local ISO-8859-1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian, com Byte Order Mark (FF FE) </td> 
   <td colname="col2"> Convertido para ISO-8859-1 ou UTF-8, conforme determinado pela configuração de seu report suite. O Microsoft Excel salva nesse formato quando você seleciona exportar "unicode". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian, com Byte Order Mark (EF FF) </td> 
   <td colname="col2"> Convertido para ISO-8859-1 ou UTF-8, conforme determinado pela configuração de seu report suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 sem Byte Order Mark </td> 
   <td colname="col2"> Não suportado. </td> 
  </tr> 
 </tbody> 
</table>

Se você enviar um arquivo UTF-8 ou ISO-8859-1 e seu report suite não estiver configurado para suportá-lo, uma das seguintes situações ocorrerá:

* O erro é identificado durante a conversão, e, nesse caso, você receberá a seguinte mensagem: "Caractere defeituoso identificado no arquivo na posição 18 durante a conversão de UTF-8 para ISO-8859-1".
* O arquivo é processado sem erros, mas você verá dados ilegíveis no relatório.

## Upload de arquivos de log da Web {#section_DD736FC971FE45C89AB310BEDC1FE707}

* Os relatórios mais úteis para exibir os dados de log da Web são os relatórios de tráfego, como exibições de página.
* Os nomes das páginas são exibidos como URL inteiro, incluindo a sequência de consulta.
* Cada solicitação de arquivo aparece como uma exibição separada da página, incluindo folhas de estilo e arquivos de imagem.
* Se você acrescentar informações no URL, os arquivos poderão ser gravados como páginas separadas. Por exemplo, os relatórios de marketing gravam os seguintes URLs como duas páginas separadas:

[!DNL /jokes/misc/snail_joke.html?userid=12345]

[!DNL /jokes/misc/snail_joke.html?userid=98765]
