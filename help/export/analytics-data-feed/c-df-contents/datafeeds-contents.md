---
description: Esta seção descreve os arquivos encontrados na entrega do feed de dados.
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: Conteúdos do feed de dados - visão geral
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conteúdos do feed de dados - visão geral

Esta seção descreve os arquivos encontrados na entrega do feed de dados.

## Arquivo manifest

O arquivo de manifesto contém os detalhes a seguir sobre cada arquivo que faz parte do conjunto de dados carregado:

* Nome do arquivo
* Tamanho do arquivo
* hash MD5
* Número de registros contidos no arquivo

O arquivo de manifesto segue o mesmo formato de um arquivo de manifesto Java JAR.

O arquivo de manifesto é sempre fornecido por último como um arquivo `.txt` separado, de modo que sua existência indique que o conjunto de dados completo para o período de solicitação já foi fornecido. Os arquivos de manifesto são nomeados de acordo com os seguintes itens:

```text
[rsid]_[YYYY-mm-dd].txt
```

Um arquivo de manifesto comum contém dados como os seguintes:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Todo arquivo de manifesto contém um cabeçalho, que indica o número total de arquivos de pesquisa, arquivos de dados e o número total de registros em todos os arquivos de dados. Esse cabeçalho é seguido por várias seções com informações de cada arquivo incluído na entrega do feed de dados.

Alguns feeds são configurados para receber um arquivo `.fin` em vez de um manifesto `.txt`. O `.fin` indica que o carregamento foi concluído, mas não possui metadados sobre o carregamento.

## Arquivos de pesquisa

Algumas colunas de feed de dados produzem um número que corresponde ao seu valor real. Os arquivos de pesquisa são usados para corresponder um número de uma coluna de feed de dados e corresponder a um valor real. Por exemplo, um valor de &quot;497&quot; na coluna de dados de `browser` ocorrência indica que a ocorrência veio do &quot;Microsoft Internet Explorer 8&quot; se você procurar `browser.tsv`.

Observe que `column_headers.tsv` e `event_list.tsv` são específicos ao feed de dados e ao conjunto de relatórios. Outros arquivos, como `browser.tsv`, são genéricos.

Os arquivos de pesquisa são entregues em conjunto em um zip compactado, o qual é nomeado de acordo com os seguintes itens:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
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

## Arquivos de dados de hit

Os dados de hit são fornecidos em um arquivo [!DNL hit_data.tsv]. A quantidade de dados nesse arquivo é determinada pelo formato de entrega (por hora ou por dia e, ainda, em único arquivo ou vários arquivos). Esse arquivo contém somente os dados de hit. Os cabeçalhos da coluna são entregues separadamente com os arquivos de pesquisa. Cada linha desse arquivo contém uma única chamada de servidor.

Os arquivos entregues pela Adobe variam com base no tipo de feed de dados configurados. Todos os arquivos são codificados usando o ISO-8859-1.

* `[rsid]` refere-se à ID do conjunto de relatórios de onde o feed de dados é.
* `[index]` é usado somente em vários feeds de arquivo e se refere à ordem correta dos arquivos paginados.
* `[YYYY-mm-dd]` refere-se ao dia de início do feed de dados.
* `[HHMMSS]` é usado somente em feeds por hora e refere-se à hora inicial para a qual o feed de dados é usado.
* `[compression_suffix]` refere-se ao tipo de compactação usado. Normalmente, os feeds de dados são compactados em `tar.gz` ou `zip` arquivos.

### Por dia, único arquivo

Depois que os dados forem coletados por um dia, você receberá um único arquivo de dados compactado e um arquivo manifest. O nome do arquivo de dados é:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando extraído, o arquivo de dados contém um único `hit_data.tsv` arquivo com todos os dados do dia, bem como arquivos de pesquisa para quaisquer colunas necessárias.

### Diariamente, vários arquivos

Depois que os dados forem coletados por um dia, você receberá um ou mais arquivos de dados compactados e um arquivo manifest. O nome do arquivo de dados é:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando extraído, cada arquivo de dados contém um único `hit_data.tsv` que contém aproximadamente 2 GB de dados descompactados, bem como arquivos de pesquisa para qualquer coluna necessária.

### Por hora, único arquivo

Depois que os dados forem coletados por uma hora, você receberá um único arquivo de dados compactado e um arquivo manifest. O nome do arquivo de dados é:

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Quando extraído, o arquivo de dados contém um único `hit_data.tsv` arquivo com todos os dados daquela hora, bem como arquivos de pesquisa para quaisquer colunas necessárias.

### Por hora, vários arquivos

Depois que os dados forem coletados por uma hora, você receberá um ou mais arquivos de dados compactados e um arquivo manifest. O nome do arquivo de dados é:

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Quando extraído, cada arquivo de dados contém um único `hit_data.tsv` que contém aproximadamente 2 GB de dados descompactados, bem como arquivos de pesquisa para qualquer coluna necessária.

## Tamanho do arquivo de dados

O tamanho do arquivo de dados de hit varia muito dependendo do número de variáveis usadas ativamente e da quantidade de tráfego no conjunto de relatórios. Contudo, em média, uma linha de dados tem aproximadamente 500 B (compactada) ou 2 KB (descompactada). Multiplicar isso pelo número de chamadas de servidor pode fornecer uma estimativa aproximada do tamanho que um feed de dados terá. Assim que suas organizações começarem a receber arquivos de feed de dados, você poderá encontrar um número mais preciso dividindo o número de linhas `hit_data.tsv` pelo tamanho total do arquivo.
