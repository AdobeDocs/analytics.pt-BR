---
title: Pesquisas dinâmicas
description: Saiba mais sobre o que são pesquisas dinâmicas e como ativá-las. Inclui operadoras, atributos móveis e tipos de sistema operacional.
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Pesquisas dinâmicas

As pesquisas dinâmicas permitem que você receba arquivos de pesquisa adicionais no feed de dados que não estarão disponíveis. Essa configuração permite que as seguintes tabelas de pesquisa sejam enviadas com cada arquivo de feed de dados:

* **Nome da operadora**: fornece contexto adicional para o `carrier` coluna. O nome de arquivo incluído é `carrier.tsv`.
* **Atributos móveis**: fornece contexto adicional para o `mobile_id` incluindo todos os recursos rastreados para cada dispositivo móvel. O nome de arquivo incluído é `mobile_attributes.tsv`.
* **Tipo de sistema operacional**: fornece um contexto alternativo para o `os` coluna. Ambos `operating_systems.tsv` e `operating_system_type.tsv` use o `os` como a chave, no entanto, somente `operating_system_type.tsv` é uma pesquisa dinâmica.

## Ativar pesquisas dinâmicas

Para receber os arquivos de pesquisa mencionados, você deve atender a todos os seguintes pré-requisitos:

* A coluna principal deve ser incluída no feed de dados.
   * Para `carrier.tsv`, você deve incluir `carrier`.
   * Para `mobile_attributes.tsv`, você deve incluir `mobile_id`.
   * Para `operating_system_type.tsv`, você deve incluir `os`.
* As seguintes colunas devem ser **excluído**. Se qualquer uma dessas colunas estiver incluída no feed de dados, a variável `mobile_attributes.tsv` a pesquisa dinâmica não está incluída.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Assim que o feed de dados atender aos requisitos de inclusão e exclusão de colunas, entre em contato com o Atendimento ao cliente com a ID do feed de dados e solicite a ativação de pesquisas dinâmicas.

## Referência do cabeçalho de pesquisa

Os cabeçalhos de coluna para esses arquivos de pesquisa não mudam com o tempo, portanto, os cabeçalhos não são incluídos em cada arquivo de feed de dados. Use esses cabeçalhos de coluna como uma referência ou baixe os respectivos `.tsv` arquivo.

+++**Nome da operadora**
Baixar [carrier_headers.tsv](assets/carrier_headers.tsv) ou consulte os cabeçalhos abaixo.

`carrier`
`Carrier Name`
+++

+++**Atributos móveis**
Baixar [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) ou consulte os cabeçalhos abaixo.

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**Tipo de sistema operacional**
Baixar [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) ou consulte os cabeçalhos abaixo.

`os`
`Operating System Type`
+++
