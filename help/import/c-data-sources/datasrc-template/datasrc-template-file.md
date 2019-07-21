---
description: Informações sobre o modelo das Fontes de dados que fornece uma estrutura de dados adequada para enviar um conjunto específico de dados externos para as Fontes de dados.
seo-description: Informações sobre o modelo das Fontes de dados que fornece uma estrutura de dados adequada para enviar um conjunto específico de dados externos para as Fontes de dados.
seo-title: Visão geral do modelo das Fontes de Dados
solution: Analytics
subtopic: Fontes de dados
title: Visão geral do modelo das Fontes de Dados
topic: Desenvolvedor e implementação
uuid: e 768 bcff-a 996-44 c 7-a 7 f 2-9 a 2 c 651 ecad 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visão geral do modelo das Fontes de Dados

Informações sobre o modelo das Fontes de dados que fornece uma estrutura de dados adequada para enviar um conjunto específico de dados externos para as Fontes de dados.

O arquivo modelo gerado por esse Assistente foi desenvolvido para você começar a importação. Não é preciso se limitar às colunas definidas no modelo. É possível inserir mais colunas, conforme necessário, desde que a métrica ou a definição seja suportada pelo tipo de processamento de dados selecionado.

É possível exibir as métricas e dimensões de cada tipo nas seguintes seções:

* [Log da Web](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [Tráfego](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC) (não há mais suporte)
* [Conversão](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [ID da transação](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [Processamento completo](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

Após sua criação, é possível baixar o modelo, inserir seus dados nele, e então carregar os dados no local FTP das Fontes de Dados. Depois de serem processados pelo servidor das Fontes de dados, os dados importados são disponibilizados para uso nos relatórios de marketing.

The Data Source template is a [!DNL .txt] file that you can open with any text editor. No entanto, é mais fácil trabalhar com o modelo no Microsoft Excel ou em outro aplicativo de planilha eletrônica. O conteúdo do modelo varia com base em suas seleções no [!UICONTROL Assistente de ativação da fonte de dados].

Consulte [Referência do arquivo de importação](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) para obter mais detalhes.
