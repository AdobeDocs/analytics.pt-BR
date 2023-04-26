---
title: Pesquisas dinâmicas
description: Saiba mais sobre o que são pesquisas dinâmicas e como ativá-las. Inclui operadoras, atributos móveis e tipos de sistema operacional.
source-git-commit: b6084fc34165ea602fce616e13b3adfcd7bdfdbd
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Pesquisas dinâmicas

As pesquisas dinâmicas permitem que você receba arquivos de pesquisa adicionais no feed de dados caso contrário, não estarão disponíveis. Essa configuração permite que as seguintes tabelas de pesquisa sejam enviadas com cada arquivo de feed de dados:

* **Nome da operadora**: Fornece contexto adicional para a variável `carrier` coluna. O nome de arquivo incluído é `carrier.tsv`.
* **Atributos móveis**: Fornece contexto adicional para a variável `mobile_id` , incluindo todos os recursos rastreados para cada dispositivo móvel. O nome de arquivo incluído é `mobile_attributes.tsv`.
* **Tipo de sistema operacional**: Fornece um contexto alternativo para o `os` coluna. Ambos `operating_systems.tsv` e `operating_system_type.tsv` use o `os` como a chave, no entanto somente `operating_system_type.tsv` é uma pesquisa dinâmica.

## Ativar pesquisas dinâmicas

Se quiser receber os arquivos de pesquisa mencionados, você deverá atender a todos os pré-requisitos a seguir:

* A coluna chave deve ser incluída no feed de dados.
   * Para `carrier.tsv`, você deve incluir `carrier`.
   * Para `mobile_attributes.tsv`, você deve incluir `mobile_id`.
   * Para `operating_system_type.tsv`, você deve incluir `os`.
* As seguintes colunas devem ser **excluídos**. Se qualquer uma dessas colunas for incluída no feed de dados, as tabelas de pesquisa adicionais não serão incluídas.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Quando o feed de dados atender aos requisitos de inclusão e exclusão de coluna, entre em contato com o Atendimento ao cliente com a ID do feed de dados e solicite a ativação de pesquisas dinâmicas.

## Referência do cabeçalho da pesquisa

Os cabeçalhos de coluna para esses arquivos de pesquisa não são alterados ao longo do tempo, portanto, os cabeçalhos não são incluídos em cada arquivo de feed de dados. Use esses cabeçalhos de coluna como referência ou baixe seus respectivos `.tsv` arquivo.

+++**Nome da operadora**
Baixar [carrier_headers.tsv](assets/carrier_headers.tsv) ou referencie os cabeçalhos abaixo.

`carrier`
`Carrier Name`
+++

+++**Atributos móveis**
Baixar [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) ou referencie os cabeçalhos abaixo.

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
Baixar [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) ou referencie os cabeçalhos abaixo.

`os`
`Operating System Type`
+++