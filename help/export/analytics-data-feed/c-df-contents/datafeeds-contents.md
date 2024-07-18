---
description: Esta seção descreve os arquivos encontrados na entrega do feed de dados.
keywords: Feed de dados;tarefa;conteúdo;manifesto;arquivo;pesquisa;dados de ocorrência;conteúdo de delivery
subtopic: data feeds
title: Conteúdos do feed de dados - visão geral
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 69%

---

# Conteúdos do feed de dados - visão geral

As seções a seguir descrevem como acessar e entender os arquivos encontrados na entrega de um feed de dados.

## Acessar conteúdo do feed de dados

Para acessar o conteúdo de um feed de dados:

1. Faça logon no site de destino do feed de dados.

   É o site de destino que você configura ao criar o feed de dados, como um bucket do Amazon S3 ou da Google Cloud Platform.

1. Baixe o arquivo de feed de dados compactado no computador local.

1. Descompacte o arquivo compactado usando um programa compatível com extensões de arquivo `.tar.gz`.

1. Abra o arquivo `hit_data.tsv` na planilha ou no aplicativo de banco de dados preferido para ver os dados brutos desse dia. —>

## Arquivo manifest {#feed-manifest}

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

Alguns feeds são configurados para receber um arquivo `.fin` em vez de um manifesto `.txt`. O `.fin` indica que o carregamento foi concluído, mas os metadados que ele contém estão em um formato antigo.

## Arquivos de pesquisa

Algumas colunas de feed de dados produzem um número que corresponde ao seu valor real. Os arquivos de pesquisa são usados para corresponder um número de uma coluna de feed de dados e corresponder a um valor real. Por exemplo, um valor de &quot;497&quot; na coluna de dados de `browser` ocorrência indica que a ocorrência veio do &quot;Microsoft Internet Explorer 8&quot; se você procurar `browser.tsv`.

Observe que `column_headers.tsv` e `event_list.tsv` são específicos ao feed de dados e ao conjunto de relatórios. Outros arquivos, como `browser.tsv`, são genéricos.

Os arquivos de pesquisa são entregues em conjunto em um zip compactado, o qual é nomeado de acordo com os seguintes itens:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**: Uma única linha contendo os cabeçalhos de coluna para `hit_data.tsv`.
* **`browser.tsv`**: Mapeia a ID do navegador (a coluna de feed `browser`) para o nome amigável do navegador.
* **`browser_type.tsv`**: Mapeia a ID do navegador (a coluna de feed `browser`) para o tipo de navegador.
* **`color_depth.tsv`**: Mapeia a ID de intensidade de cor (a coluna de feed `color`) para a intensidade de cor.
* **`connection_type.tsv`**: Mapeia a ID do tipo de conexão (a coluna de feed `connection_type`) para o tipo de conexão.
* **`country.tsv`**: Mapeia a ID do país (a coluna de feed `country`) para o nome do país.
* **`javascript_version.tsv`**: Mapeia a ID da versão do JavaScript (a coluna de feed `javascript`) para a versão do JavaScript.
* **`languages.tsv`**: Mapeia a ID do idioma (a coluna de feed `language`) para o idioma.
* **`operating_systems.tsv`**: Mapeia a ID do sistema operacional (a coluna de feed `os`) para o nome do sistema operacional.
* **`plugins.tsv`**: Mapeia as IDs do plug-in (a coluna de feed `plugin`) para cada nome de plug-in respectivo.
* **`resolution.tsv`**: Mapeia a ID de resolução (a coluna de feed `resolution`) para a resolução do monitor.
* **`referrer_type.tsv`**: Mapeia a ID de tipo de referenciador (a coluna de feed `ref_type`) para o tipo de referenciador.
* **`search_engines.tsv`**: Mapeia a ID do mecanismo de pesquisa (a coluna de feed `search_engine`) para o nome do mecanismo de pesquisa.
* **`event.tsv`**: Mapeia cada ID de evento (a coluna de feed `event_list`) para seu respectivo nome de evento.

## Arquivos de dados de hit

Os dados de hit são fornecidos em um arquivo `hit_data.tsv`. A quantidade de dados nesse arquivo é determinada pelo formato de entrega (por hora ou por dia e, ainda, em único arquivo ou vários arquivos). Esse arquivo contém somente os dados de hit. Os cabeçalhos da coluna são entregues separadamente com os arquivos de pesquisa. Cada linha desse arquivo contém uma única chamada de servidor.

Os arquivos entregues pela Adobe variam com base no tipo de feed de dados configurados. Todos os arquivos são codificados usando o ISO-8859-1.

* `[rsid]` refere-se à ID do conjunto de relatórios de onde o feed de dados é.
* `[index]` é usado somente em vários feeds de arquivo e se refere à ordem correta dos arquivos paginados.
* `[YYYY-mm-dd]` refere-se ao dia de início do feed de dados.
* `[HHMMSS]` é usado somente em feeds por hora e refere-se à hora inicial para a qual o feed de dados é usado.
* `[compression_suffix]` refere-se ao tipo de compactação usado. Normalmente, os feeds de dados são compactados em `tar.gz` ou `zip` arquivos.
* `[format_suffix]` refere-se ao tipo de formato de arquivo. Normalmente, o formato do arquivo de feed de dados é `.tsv`.

### Por dia, único arquivo

Depois que os dados forem coletados por um dia, você receberá um único arquivo de dados compactado e um arquivo manifest. O nome do arquivo de dados é:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando extraído, o arquivo de dados contém um único `hit_data.tsv` arquivo com todos os dados do dia, bem como arquivos de pesquisa para quaisquer colunas necessárias.

### Diariamente, vários arquivos

Depois que os dados forem coletados por um dia, você receberá um ou mais arquivos de dados compactados e um arquivo manifest. O nome do arquivo de dados é:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando extraído, cada arquivo de dados contém um único `[index]-[rsid]_[YYYY-mm-dd].[format_suffix]` que contém aproximadamente 2 GB de dados descompactados, bem como arquivos de pesquisa para qualquer coluna necessária.

### Por hora, único arquivo

Depois que os dados forem coletados por uma hora, você receberá um único arquivo de dados compactado e um arquivo manifest. O nome do arquivo de dados é:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Quando extraído, o arquivo de dados contém um único `hit_data.tsv` arquivo com todos os dados daquela hora, bem como arquivos de pesquisa para quaisquer colunas necessárias.

### Por hora, vários arquivos

Depois que os dados forem coletados por uma hora, você receberá um ou mais arquivos de dados compactados e um arquivo manifest. Os arquivos de dados são nomeados como:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix].[compression_suffix]`

Quando extraído, cada arquivo de dados contém um único arquivo `[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix]` que contém aproximadamente 2 GB de dados descompactados, bem como arquivos de pesquisa para quaisquer colunas necessárias.

## Tamanho do arquivo de dados

O tamanho do arquivo de dados de hit varia muito dependendo do número de variáveis usadas ativamente e da quantidade de tráfego no conjunto de relatórios. Contudo, em média, uma linha de dados tem aproximadamente 500 B (compactada) ou 2 KB (descompactada). Multiplicar isso pelo número de chamadas de servidor pode fornecer uma estimativa aproximada do tamanho que um feed de dados terá. Assim que suas organizações começarem a receber arquivos de feed de dados, você poderá encontrar um número mais preciso dividindo o número de linhas `hit_data.tsv` pelo tamanho total do arquivo.