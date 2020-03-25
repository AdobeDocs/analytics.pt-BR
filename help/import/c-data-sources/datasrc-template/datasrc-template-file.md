---
description: Informações sobre o modelo das Fontes de dados que fornece uma estrutura de dados adequada para enviar um conjunto específico de dados externos para as Fontes de dados.
subtopic: Data sources
title: Visão geral do Modelo das Fontes de dados
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visão geral do Modelo das Fontes de dados

Informações sobre o modelo das Fontes de dados que fornece uma estrutura de dados adequada para enviar um conjunto específico de dados externos para as Fontes de dados.

O arquivo modelo gerado por esse Assistente foi desenvolvido para você começar a importação. Não é preciso se limitar às colunas definidas no modelo. É possível inserir mais colunas, conforme necessário, desde que a métrica ou a definição seja suportada pelo tipo de processamento de dados selecionado.

É possível exibir as métricas e dimensões de cada tipo nas seguintes seções:

* [Log da Web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (não há mais suporte)
* [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [ID da transação](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [ID de visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Processamento completo](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

Por exemplo, para um tipo de dados de ID de visitante, é possível adicionar uma coluna para qualquer métrica ou dimensão descrita na [ID do visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

Após sua criação, é possível baixar o modelo, inserir seus dados nele, e então carregar os dados no local FTP das Fontes de Dados. Depois de serem processados pelo servidor das Fontes de dados, os dados importados são disponibilizados para uso nos relatórios de marketing.

O modelo da Fonte de Dados é um arquivo [!DNL .txt] que pode ser aberto em qualquer editor de texto. No entanto, é mais fácil trabalhar com o modelo no Microsoft Excel ou em outro aplicativo de planilha eletrônica. O conteúdo do modelo varia com base em suas seleções no [!UICONTROL Assistente de ativação da fonte de dados].

Consulte [Referência do arquivo de importação](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) para obter mais detalhes.
